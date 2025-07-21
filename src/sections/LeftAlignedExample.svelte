<script>
    import * as Highcharts from "highcharts";
    import "highcharts/modules/exporting";
    import { Chart } from "@highcharts/svelte";
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";

    const series = [
        {
            name: "White",
            data: [
                [2019, 67.7] ,
                [2020, 68],
                [2021, 68.1],
                [2022, 68.6],
            ],
            color: "#8427c9",
        },
        {
            name: "Asian",
            data: [
                [2019, 71.9],
                [2020, 73.6],
                [2021, 74],
                [2022, 75.2],
            ],
            color: "#DB7F67",
        },
            {
            name: "Hispanic",
            data: [
                [2019, 49.1],
                [2020, 49.5],
                [2021, 49,5],
                [2022, 50.4],
            ],
            color: "#D34F73",
            },
            
        {
            name: "Black",
            data: [
                [2019, 42.5],
                [2020, 43],
                [2021, 42.8],
                [2022, 43.8],
            ],
            color: "#4096fa",
        },
    ];

    let chart;
    let thirdSeriesVisible = false;

    let options = {
        chart: {
            type: "spline",
          backgroundColor: "#f6d9bd",
        },
        title: {
            text: "Completion Rates for Students Across Races",
            style: {
        color: '#3F292B',
         fontFamily: 'Copperplate, Copperplate Gothic Light, Cinzel, serif',
        fontSize: '20px' }
        },
        
        subtitle: {
            text: "Completion rates for students enrolled in post-secondary education institutions graduating from 2019-2022",
             style: {
        color: '#3F292B',
        fontFamily: 'Verdana, Geneva, Tahoma, sans-serif',
        fontSize: '14px'
        
    }
        },
        series: [series[0], series[1],series[2]],

         yAxis: {
        title: {
        text: "Graduation rate (%)",
         color: '#3F292B',
        fontFamily: 'Verdana, Geneva, Tahoma, sans-serif',
        fontSize: '12px'
    }, 
    }
    };


    function toggleThirdSeries() {
        const raceSeries = chart.series.find((s) => s.name === "Black");

        if (raceSeries) {
            raceSeries.remove();
            thirdSeriesVisible = false;
        } else {
            chart.addSeries(series[3]);
            thirdSeriesVisible = true;
        }
    }
</script>

<div>
    <Scroller layout="left">
        {#snippet sticky()}
            <div class="chart">
                <Chart bind:chart {options} highcharts={Highcharts} />
            </div>
            <button on:click={toggleThirdSeries} class="toggle-button">
                {thirdSeriesVisible ? "Remove Black Grad Rates" : "Add Black Grad Rates"}
            </button>
            <div>
                <p>
                    The following graph depicts graduation rates for White, Asian, Hispanic, and Black students enrolled in post-secondary education institutions graduating from 2019-2022.
                </p>

                <p>
                    The data, obtained from the National Student Clearinghouse Research Center, suggests that black and hispanic students graduate from higher education institutions at much lower rates than their White and Asian peers.
                </p>
                
            </div>
        {/snippet}

        {#snippet scrolly()}
            <ArticleText>

            Students of color graduate at alarmingly lower rates than their peers. 
                
            </ArticleText>

            <ArticleText>
                The following data suggests that there may be various <strong> racially centered barriers to college access and readiness </strong> once students have being accepted and enrolled into a higher education institution.
            </ArticleText>

            <ArticleText>
                <strong>
                   The college experience poses many challenges, specifically for students belonging to certain minority groups.  
                </strong>
            </ArticleText>

             <ArticleText>

                These unfair challenges persist in spite of their merit and preparation. 
            
            </ArticleText>

        {/snippet}
    </Scroller>
</div>

<style>
    .chart {
        width: 100%;
        margin: 0px auto;
    }

    .toggle-button {
        margin: 20px;
        padding: 20px;
        color: #3F292B;
        background-color: #ef4d78;
        border: solid 2px #902542;
        border-radius: 16px;
        font-size: large;
        font-family: "Copperplate", "Copperplate Gothic Light", sans-serif;
        cursor: pointer;
        transition: all 0.2s ease;
        box-shadow: 0 4px 0 #902542;
    }

    .toggle-button:active {
        transform: translateY(2px);
        box-shadow: 0 2px 0 #007052;
        font-family: "Copperplate", "Copperplate Gothic Light", sans-serif;
    }
     p {
       font-family:Verdana, Geneva, Tahoma, sans-serif;
       color:#3F292B; 
    }
</style>
