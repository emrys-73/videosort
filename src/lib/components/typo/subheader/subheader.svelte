<script>
    // @ts-nocheck
    
    
        const getSize = () => {
            switch (size) {
                case "xs":
                    return "text-sm lg:text-md"
                case "sm":
                    return "text-md lg:text-lg"
                case "md":
                    return "text-lg lg:text-xl"
                case "lg":
                    return "text-xl lg:text-2xl"
                default:
                    return "text-md lg:text-lg"
        }
    }
    
        export let size;
    </script>
    
    
    <h4 class="{getSize(size)} w-full text-center items-center dark:text-sec text-main font-semibold">
        <slot/>
    </h4>
    
    