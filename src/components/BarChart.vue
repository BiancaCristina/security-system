<template>
    <v-card
            class="mt-4 mx-auto"
            max-width="800"
    >
        <v-sheet
                class="v-sheet--offset mx-auto"
                :color="backgroundColor"
                elevation="12"
                max-width="calc(100% - 32px)"
        >
            <apexchart type="bar" height="350" :options="chartOptions" :series="series"></apexchart>
        </v-sheet>

        <v-card-text class="pt-0">
            <div class="title font-weight-light mb-2">{{title}}</div>
            <div class="subheading font-weight-light grey--text">{{subheading}}</div>
            <v-divider class="my-2"></v-divider>
            <v-icon
                    class="mr-2"
                    small
            >
                mdi-clock
            </v-icon>
            <span class="caption grey--text font-weight-light">Última atualização {{lastUpdate}}</span>
        </v-card-text>
    </v-card>
</template>

<script>
    import VueApexCharts from 'vue-apexcharts'
    export default {
        name: 'BarChart',
        components: {apexchart: VueApexCharts},

        props: {
            backgroundColor: {type: String, default: 'white'},
            barColors: {type: Array, required: true},
            lastUpdate: {type: String, required: true},
            labels: Array,
            values: Array,
            title: String,
            subheading: String
        },

        data() {
            return {
                series: this.values,

                chartOptions: {
                    colors: this.barColors,
                    dataLabels: { enabled: false },
                    fill: { opacity: 1 },

                    chart: {
                        type: 'bar',
                        height: 350,
                        toolbar: {
                            show: false
                        },
                    },

                    plotOptions: {
                        bar: {
                            horizontal: false,
                            columnWidth: '85%'
                        },
                    },

                    stroke: {
                        show: true,
                        width: 5,
                        colors: ['transparent']
                    },
                    xaxis: { categories: this.labels },
                    yaxis: {
                        title: {
                            text: 'Quantidade de Ocorrências'
                        }
                    }
                },
            }
        }
    }
</script>

<style>
    .v-sheet--offset {
        top: -24px;
        position: relative;
    }
</style>