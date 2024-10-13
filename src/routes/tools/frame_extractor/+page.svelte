<script>
    // @ts-nocheck
        import JSZip from 'jszip'; // Import JSZip if you want to download as .zip
        let videoFile = null;
        let extractionRate = 1; // Default frame extraction rate in fps
        let isExtracting = false;
        let message = 'Drag a video file here';
        let extractedFrames = [];
        let videoElement;
        let dragActive = false; // For handling drag styles
    
        // Handle file selection (manual or drag-and-drop)
        const handleFileChange = (files) => {
          if (files && files[0]) {
            videoFile = files[0];
            const url = URL.createObjectURL(videoFile);
            videoElement.src = url; // Load the video into the HTML5 <video> element
            message = `Video loaded: ${videoFile.name}`;
          } else {
            console.error("No video file selected");
          }
        };
    
        const extractFrames = async () => {
          if (!videoFile) {
            alert('Please upload a video file first.');
            return;
          }
    
          isExtracting = true;
          extractedFrames = [];
          message = 'Extracting frames...';
    
          // Wait for video metadata to be loaded
          await videoElement.play();
          videoElement.pause(); // Pause immediately after starting playback (we don't need to play the video)
    
          const duration = videoElement.duration; // Get the video duration
          const frameInterval = 1 / extractionRate; // Calculate frame interval based on FPS
    
          let currentTime = 0;
    
          // Create a canvas element to extract frames
          const canvas = document.createElement('canvas');
          const ctx = canvas.getContext('2d');
          canvas.width = videoElement.videoWidth;
          canvas.height = videoElement.videoHeight;
    
          // Loop through the video and capture frames
          while (currentTime < duration) {
            videoElement.currentTime = currentTime;
    
            // Wait for the video to seek to the current time
            await new Promise(resolve => videoElement.onseeked = resolve);
    
            // Draw the current video frame onto the canvas
            ctx.drawImage(videoElement, 0, 0, canvas.width, canvas.height);
    
            // Convert the canvas to an image and store the base64 URL
            const frameURL = canvas.toDataURL('image/png');
            extractedFrames.push(frameURL);
    
            // Move to the next frame time
            currentTime += frameInterval;
          }
    
          message = 'Frames extracted successfully!';
          isExtracting = false;
        };
    
        const downloadFrame = (frameURL, filename) => {
          const link = document.createElement('a');
          link.href = frameURL;
          link.download = filename;
          document.body.appendChild(link);
          link.click();
          document.body.removeChild(link);
        };
    
        const downloadAllFramesAsZip = async () => {
          if (!videoFile) return;
    
          const zip = new JSZip();
          extractedFrames.forEach((frame, index) => {
            const base64Data = frame.split(',')[1]; // Extract base64 data without the header
            zip.file(`frame_${index + 1}.png`, base64Data, { base64: true });
          });
    
          // Generate the zip file and trigger download
          const content = await zip.generateAsync({ type: 'blob' });
    
          // Get the original video file name (without extension)
          const videoFileName = videoFile.name.replace(/\.[^/.]+$/, "");
    
          // Create the download link with the custom file name
          const zipLink = document.createElement('a');
          zipLink.href = URL.createObjectURL(content);
          zipLink.download = `Avlana Frames - ${videoFileName}.zip`;
          zipLink.click();
        };
    
        // Drag-and-Drop Handlers
        const handleDragOver = (event) => {
          event.preventDefault();
          dragActive = true;
        };
    
        const handleDragLeave = () => {
          dragActive = false;
        };
    
        const handleDrop = (event) => {
          event.preventDefault();
          dragActive = false;
          const files = event.dataTransfer.files;
          handleFileChange(files);
        };
    
        const handleManualFileInput = (event) => {
          const files = event.target.files;
          handleFileChange(files);
        };
    </script>


<div class="w-full h-full flex flex-col justify-center items-center min-h-screen px-4 py-12 md:py-6">
    <!-- Title and drag and drop are -->
    <div class="w-full flex md:flex-row flex-col gap-6 justify-center items-center h-full">
        <div class="w-full md:w-3/5 h-full">
            <div
                role="button" 
                tabindex="0"
                class={`min-h-[80vh] justify-center items-center flex flex-col gap-4 rounded-xl border-2 border-main border-dashed h-full w-full ${dragActive ? 'bg-transparent border-opacity-100' : 'bg-transparent border-opacity-40'} transition-all duration-300 ease-in-out px-6 py-10 text-center cursor-pointer`}
                on:dragover={handleDragOver}
                on:dragleave={handleDragLeave}
                on:drop={handleDrop}
            >
                <p class="text-lg font-semibold">{message}</p>
                <p class="text-sm opacity-80">Or</p>
                <input 
                    id="video-upload"
                    type="file" 
                    accept="video/*" 
                    on:change={handleManualFileInput} 
                    class="text-sm border bg-transparent border-white border-opacity-20 rounded-md cursor-pointer"
                />
            </div>
        </div> 

        <div class="w-full md:w-2/5 h-full bg-main bg-opacity-0 flex flex-col justify-start items-center gap-4 rounded-xl min-h-[30vh] md:min-h-[80vh] relative">
          <h2 class="w-full justify-start items-center flex text-lg font-semibold">
            Extraction Rate (in fps)
          </h2>
          <input 
                id="extraction-rate"
                type="number" 
                bind:value={extractionRate} 
                min="1" 
                step="1" 
                class=" w-full p-2 border rounded-md bg-transparent" 
                placeholder="Default is 1 fps"/>


                {#if extractedFrames.length > 0}
                <button 
                    on:click={downloadAllFramesAsZip} 
                    class="border-sec border-2 hover:bg-sec hover:text-black rounded-md transition-all duration-300 ease-in-out text-white font-bold py-2 px-4 hover:sec w-full md:absolute md:bottom-16">
                    Download All Frames as ZIP
                </button>
              {/if}

              <button 
                on:click={extractFrames} 
                class="bg-main text-white font-bold py-2 px-4 rounded-md w-full hover:bg-main disabled:opacity-50 md:absolute md:bottom-0" 
                disabled={isExtracting || !videoFile}>
                {isExtracting ? 'Extracting...' : 'Extract Frames'}
            </button>
        </div>

    </div>

</div>
<!-- svelte-ignore a11y-media-has-caption -->
<video bind:this={videoElement} style="display:none;" class="hidden"></video>