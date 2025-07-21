<script>
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";
</script>

<div>
    <Scroller layout="left">
        {#snippet sticky()}
            <img class="duck-img" src="teacher.png" alt="Teacher and student relationship" />
        {/snippet}

        {#snippet scrolly()}
            <ArticleText>
                <strong>
                    Disparities in college completion rates can be examined through the intersection between race, class, and sociocultural contexts.
                </strong>
            </ArticleText>
            <ArticleText>Oppressive redlining practices, force ethnic minority groups to stay in under-resourced neighborhoods, with a lack of education resources.
            </ArticleText>
            <ArticleText> <strong> Insufficient student-staff relationships</strong> pose one of the key barriers in college success for minorities.</ArticleText>
            <ArticleText> Lack of access to proper school guidance counseling for many low-income students decrease their ability to become college ready from the get go. </ArticleText>
            <ArticleText> Many diverse schools have a White teacher majority, which can further create a barrier in relationship-building. </ArticleText>
        {/snippet}
    </Scroller>
</div>

<style>
    .duck-img {
        width: 100%;
        margin: 0px auto;
    }
</style>
