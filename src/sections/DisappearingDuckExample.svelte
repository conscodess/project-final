<script>
    import { fade, fly } from "svelte/transition";
    import Scroller from "../lib/Scroller.svelte";
    import ObservedArticleText from "../lib/ObservedArticleText.svelte";

    let duckIsVisible = $state(false);

    const options = {
        threshold: [0.85, 0.95],
    };

    const simpleCallback = (entries, observer) => {
        entries.forEach((entry) => {
            const elem = entry.target;

            if (entry.intersectionRatio >= 0.9) {
                // "active" state
                elem.style.backgroundColor = "#A37B73";
            } else if (entry.intersectionRatio < 0.9) {
                // "inactive" state
                elem.style.backgroundColor = "#A37B73";
            }
        });
    };

    const showDuckCallback = (entries, observer) => {
        entries.forEach((entry) => {
            const elem = entry.target;

            if (entry.intersectionRatio >= 0.9) {
                elem.style.backgroundColor = "#A37B73";
                duckIsVisible = true;
            } else if (entry.intersectionRatio < 0.9) {
                elem.style.backgroundColor = "#A37B73";
            }
        });
    };

    const removeDuckCallback = (entries, observer) => {
        entries.forEach((entry) => {
            const elem = entry.target;

            if (entry.intersectionRatio >= 0.9) {
                elem.style.backgroundColor = "#A37B73";
                duckIsVisible = false;
            } else if (entry.intersectionRatio < 0.9) {
                elem.style.backgroundColor = "#A37B73";
            }
        });
    };
</script>

<div>
    <Scroller layout="left">
        {#snippet sticky()}
            <div>
                {#if duckIsVisible}
                    <img
                        class="duck-img"
                        src="certificate.png"
                        alt="KWK rubber duck!"
                        in:fly={{ y: 200, duration: 2000 }}
                        out:fade
                    />
                {/if}
                <br />
            </div>
        {/snippet}

        {#snippet scrolly()}
        
            <ObservedArticleText callback={showDuckCallback} {options}>
               While enrollment gets students one foot into the higher education door. 
            </ObservedArticleText>

            <ObservedArticleText callback={removeDuckCallback} {options}>
               For many minority students, the racial and economic barriers can cause the dream of the coveted diploma to fade away.
            </ObservedArticleText>

        {/snippet}
    </Scroller>
</div>

<style>
    .duck-img {
        width: 150%;
        margin: 0px auto;
    }
</style>
