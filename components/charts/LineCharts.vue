<template>
    <div>
        <highchart
            :options="chartOptions"
            :update="['options.title', 'options.series']"
        />
    </div>
</template>

<script>
export default {
    name: 'LineCharts',
    data () {
        return {
            chartOptions: {
                legend: {
                    layout: 'vertical',
                    align: 'right',
                    verticalAlign: 'middle'
                },
                plotOptions: {
                    series: {
                        label: {
                            connectorAllowed: false
                        },
                        pointStart: 2010
                    }
                },
                series: [
                    {
                        name: '방문자',
                        data: [43934, 52503, 57177, 69658, 97031, 119931, 137133, 154175]
                    },
                    {
                        name: '페이지뷰',
                        data: [24916, 24064, 29742, 29851, 32490, 30282, 38121, 40434]
                    },
                    {
                        name: '방송 조회수',
                        data: [11744, 17722, 16005, 19771, 20185, 24377, 32147, 39387]
                    },
                    {
                        name: '07월 트래픽',
                        data: [null, null, 7988, 12169, 15112, 22452, 34400, 34227]
                    },
                ],
                responsive: {
                    rules: [
                        {
                            condition: {
                                // maxWidth: 500
                            },
                            chartOptions: {
                                legend: {
                                    layout: 'horizontal',
                                    align: 'center',
                                    verticalAlign: 'bottom'
                                }
                            }
                        }
                    ]
                }
            }
        }
    },

}
</script>

<style scoped>

</style>
