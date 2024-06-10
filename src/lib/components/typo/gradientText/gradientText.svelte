<script>
// @ts-nocheck


    const getSize = () => {
        switch (size) {
            case "xs":
                return "text-xl lg:text-2xl"
            case "sm":
                return "text-2xl lg:text-3xl"
            case "md":
                return "text-3xl lg:text-4xl"
            case "lg":
                return "text-4xl lg:text-5xl"
            case "xl":
                return "text-6xl lg:text-7xl"
            case "2xl":
                return "text-8xl lg:text-9xl"
            default:
                return "text-3xl lg:text-4xl"
    }
}

    export let size;
</script>


<h3 class="{getSize(size)} bg-gradient-to-r from-sec to-main text-transparent bg-clip-text font-semibold text-center">
    <slot/>
</h3>


