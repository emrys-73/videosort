<script>
    const tools = [
        {
            "name": "Frame Extractor",
            "route": "/tools/frame_extractor",
            "active": true,
        },
        {
            "name": "video compressor",
            "route": "/tools/video_compressor",
            "active": false,
        },
    ]

</script>


<div class="w-full h-full justify-center items-center flex flex-col px-4 py-2 gap-4">
    {#each tools as t}
        {#if t.active}
            <a href={t.route} class="bg-main px-4 py-2 rounded-xl">
                {t.name}
            </a>
        {/if}
    {/each}
</div>