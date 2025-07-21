<script>
    import * as Highcharts from "highcharts";
    import "highcharts/modules/exporting";
    import { Chart } from "@highcharts/svelte";
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";
    

    let options = {
        chart: {
            type: "column",
            backgroundColor: '#f6d9bd'
        },
        title: {
            text: "National College Enrollment Rates 2021-2023",
           style: {
        color: '#3F292B',
        fontFamily: 'Copperplate, Copperplate Gothic Light, Cinzel, serif',
        fontSize: '20px'
  }
        },
        subtitle: { 
            text: "National college enrollment rates across races for the years 2021, 2022, and 2023",
            style: {
        color: '#3F292B',
        fontFamily: 'Verdana, Geneva, Tahoma, sans-serif',
        fontSize: '14px'
        
    }

        },
        xAxis: {
            categories: ["White","Asian","Hispanic","Black"],
            style: {
        color: '#3F292B',
        fontFamily: 'Verdana, Geneva, Tahoma, sans-serif'}

        },
        yAxis: {
            min: 0,
            title: {
                text: "Percentage of graduates enrolled (%)",
                style: {
        color: '#3F292B',
        fontFamily: 'Verdana, Geneva, Tahoma, sans-serif',
        fontSize: '12px' }
            }
            },
        tooltip: {
        valueSuffix: "(%)"
    },
        plotOptions: {
            column: {
                pointPadding: 0.2,
                borderWidth: 0
            }
        },
        series: [
            {
             name: "2021", 
             data: [5.1, 7.3, 6.2, 6.4],
             style: {
            color: '#3F292B',
            fontFamily: 'Verdana, Geneva, Tahoma, sans-serif'}
            },
            {
                name:"2022",
                data: [5,7.2,6.2,6.4],
                style: {
             color: '#3F292B',
            fontFamily: 'Verdana, Geneva, Tahoma, sans-serif'}
            },
             {
                name:"2023",
                data: [4.8,6.9,5.9,6.1],
                style: {
            color: '#3F292B',
            fontFamily: 'Verdana, Geneva, Tahoma, sans-serif'}
            }
        ]
    }
        
        
</script>

<div>
    <Scroller layout="right">
        {#snippet sticky()}
            <div class="chart">
                <Chart {options} highcharts={Highcharts} />
            </div>
            <p>
                 The following is a bar graph constructed with BWDC website data that displays the <strong> enrollment rates at post-secondary education institutions </strong> for students in 2021, 2022, and 2023, belonging to different race groups. 
            </p>
            <p> The data suggests that for the last few years the percentage of enrolled students per race group has been higher for minority groups.</p>
        {/snippet}

        {#snippet scrolly()}
            <ArticleText>
                <strong>Both black and hispanic populations have been enrolling at post-secondary institutions at higher rates than their white counterparts.</strong
                >
            </ArticleText>

            <ArticleText>
                On this data alone, we can observe an <strong> strong interest </strong> in higher education among minority groups, which is a positive move towards social mobility and more opportunities.
            </ArticleText>

            <ArticleText>
                However, enrollment rates alone don't tell the <strong> whole </strong> story.
            </ArticleText>

            <ArticleText>
                <strong>
                   Despite strong enrollment rates, data also suggests that students belonging to certain minority groups might struggle with being succesful once admitted.
                </strong>
            </ArticleText>
        {/snippet}
    </Scroller>
</div>

<style>
    .chart {
        width: 100%;
        margin: 0px auto;
    }
    p {
       font-family:Verdana, Geneva, Tahoma, sans-serif;
       color:#3F292B; 
    }
    
</style>
