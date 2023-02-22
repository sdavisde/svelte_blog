<style lang="scss">
    .viewbox {
        width: 100vw;
        height: 100%;
        overflow-x: hidden;
        position: relative;
        display:flex;
        align-items: center;
    }

    .line-container {
        min-width: 200vw;
        display: inline-flex;
        align-items: center;
        justify-content: space-around;
        position: relative;
    }

    .line {
        z-index: 1;
        background-color: white;
        height: 3px;
        position: absolute;
        top: 40%;
        width: 100%;
    }

    .dot {
        z-index: 2;
        width: 20px;
        height: 20px;
        border-radius: 25px;
        background-color: white;
    }

    a {
        color: white;
    }
</style>
<script>
    import { browser } from '$app/environment'

    if (browser) {
        // @ts-ignore
        const jq = window.$;

        const viewbox = jq('.viewbox')[0];
        const line_container = jq('.line-container')[0]
        const true_width = line_container.clientWidth;
        const view_width = viewbox.clientWidth;
        const view_offset = viewbox.offsetLeft;
        console.log(true_width);
        console.log(view_width);

        // Scroll left/rigth based on mouse movement
        // left should be 0, right should be 1
        jq(".viewbox").on("mousemove", function(/** @type {{ clientX: number; }} */ e){
            var X = (e.clientX - view_offset) / view_width;
            // Scroll the div using the mouse position multiplyed by the ratio
            console.log(X)
            console.log(X * true_width)
            jq(".viewbox").scrollLeft(X*true_width/2);
        });
    }

</script>

<h1 class='title'>Welcome to Sean's Blog</h1>
<p>Visit <a href="https://sdavisde42.github.io/">my portfolio</a> to learn more about me</p>
<div class='viewbox'>
    <div class='line-container'>
        <div class='dot'></div>
        <div class='dot'></div>
        <div class='dot'></div>
        <div class='dot'></div>
        <div class='dot'></div>
        <div class='dot'></div>
        <div class='dot'></div>
        <div class='dot'></div>
        <div class='dot'></div>
        <div class='dot'></div>
        <div class='dot'></div>
        <div class='dot'></div>
        <div class='dot'></div>
        <div class='line'></div> 
    </div>
</div>
