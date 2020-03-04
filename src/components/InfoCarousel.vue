<template>
    <v-carousel
            cycle
            show-arrows-on-hover
            hide-delimiters
            height="430"
    >
        <v-carousel-item
                v-for="item in data"
                :key="item"
        >
            <v-sheet color='#2980B9'>
                <div class="display-1 font-weight-thin pl-6 pt-6">{{item.title}}</div>
                <v-sparkline
                        :labels="item.label"
                        :value="item.value"
                        color="rgba(255, 255, 255, .7)"
                        line-width="2"
                        padding="16"
                        stroke-linecap="round"
                        smooth
                ></v-sparkline>

                <v-divider class="my-0 mx-6" />
                <div class="mx-6 pt-1 pb-2">
                    <v-icon
                            class="mr-2"
                            small
                    >
                        mdi-clock
                    </v-icon>
                    <span class="caption font-weight-light">Última atualização {{lastUpdate}}</span>
                </div>
            </v-sheet>
        </v-carousel-item>
    </v-carousel>

</template>

<script>
    //import SparklineChart from "../components/SparklineChart";
    const gradients = [
        ['#222'],
        ['#42b3f4'],
        ['red', 'orange', 'yellow'],
        ['purple', 'violet'],
        ['#00c6ff', '#F0F', '#FF0'],
        ['#f72047', '#ffd200', '#1feaea'],
    ]

    export default {
        //components: {SparklineChart},


        data () {
            return {
                data: [
                    {
                        title: 'Diário',
                        label: ['09:00', '15:00', '21:00', '03:00'],
                        value: [4, 1, 10, 3],
                    },
                    {
                        title: 'Semanal',
                        label: ['Seg', 'Ter', 'Qua', 'Qui', 'Sex', 'Sáb', 'Dom'],
                        value: [20, 40, 10, 100, 2, 45, 60],
                    },
                    {
                        title: 'Anual',
                        label: [
                            'Jan.', 'Fev.', 'Mar.', 'Abr.', 'Mai.', 'Jun.',
                            'Jul.', 'Ago.', 'Set.', 'Out.', 'Nov.', 'Dez.'
                        ],
                        value: [
                            300, 450, 200, 500, 600, 452,
                            121, 876, 1000, 154, 400, 300
                        ],
                    }
                ],

                value: [
                    423,
                    446,
                    675,
                    510,
                    590,
                    610,
                    760,
                ],

                showLabels: false,
                lineWidth: 2,
                labelSize: 7,
                radius: 10,
                padding: 8,
                lineCap: 'round',
                gradient: gradients[5],
                //value: [0, 2, 5, 9, 5, 10, 3, 5, -4, -10, 1, 8, 2, 9, 0],
                gradientDirection: 'top',
                gradients,
                fill: false,
                type: 'trend',
                autoLineWidth: false,


                colors: [
                    'green',
                    'secondary',
                    'yellow darken-4',
                    'red lighten-2',
                    'orange darken-1',
                ],
                cycle: false,
                slides: [
                    'First',
                    'Second',
                    'Third',
                    'Fourth',
                    'Fifth',
                ],
            }
        },
    }
</script>