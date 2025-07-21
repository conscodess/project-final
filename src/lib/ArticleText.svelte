<script>
    let { children } = $props();
</script>

<div class="article-text">
    <p>
        {@render children()}
    </p>
</div>

<style>
    .article-text {
        margin: 50vh auto;
        width: 50%;
        background-color: #A37B73;
        color:#3F292B ;
        border: solid #DB7F673 3px;
        border: solid  3px;
        border-radius: 20px;
        padding: 20px;
        box-shadow: 8px 8px #3b3536;
         font-family:Verdana, Geneva, Tahoma, sans-serif;
    }
</style>
