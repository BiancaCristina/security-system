<template>
    <v-container class="grey lighten-5" flat>
        <v-row>
            <v-col>
                <SparklineChart
                        v-bind:labels="hourLabels"
                        v-bind:values="hourValues"
                        lastUpdate="terça-feira 12:33"
                        title="Registro de Ocorrências (Diário)"
                />
            </v-col>

            <v-col>
                <SparklineChart
                        v-bind:labels="dayLabels"
                        v-bind:values="dayValues"
                        lastUpdate="terça-feira 12:33"
                        title="Registro de Ocorrências (Semanal)"
                        backgroundColor="#E74C3C"
                />
            </v-col>

            <v-col>
                <SparklineChart
                        v-bind:labels="monthLabels"
                        v-bind:values="monthValues"
                        lastUpdate="terça-feira 12:33"
                        title="Registro de Ocorrências (Anual)"
                        backgroundColor="#27AE60"
                />
            </v-col>

        </v-row>

        <v-row
                class="mb-6"
                justify="center"
                no-gutters
        >
            <v-col lg="3">
                <InformationCard
                        backgroundColor='#E74C3C'
                        information="Não atendidas"
                        value="100"
                        lastUpdate="terça-feira 12:33"
                        icon="mdi-alert-circle-outline"
                />
            </v-col>
            <v-col md="auto">
                <InformationCard
                        backgroundColor='#27AE60'
                        information="Concluídas"
                        value="450"
                        lastUpdate="terça-feira 12:33"
                        icon="mdi-check-all"
                />
            </v-col>
            <v-col lg="3">
                <InformationCard
                        backgroundColor='#2980B9'
                        information="Em andamento"
                        value="120"
                        lastUpdate="terça-feira 12:33"
                        icon="mdi-account-clock-outline"
                />
            </v-col>
        </v-row>

        <v-row>
            <v-col>
                <BarChart
                        v-bind:labels="monthLabels"
                        v-bind:values="barChartValues"
                        v-bind:barColors="['#2980B9', '#27AE60', '#E74C3C']"
                        lastUpdate="terça-feira 12:33"
                        title="Resumo das Ocorrências"
                        backgroundColor="#FBFCFC"
                >

                </BarChart>
            </v-col>
        </v-row>
    </v-container>
</template>

<script>
    import SparklineChart from "../components/SparklineChart";
    import BarChart from "../components/BarChart";
    import InformationCard from "../components/InformationCard";

    export default {
        name: 'Dashboard',
        components: {SparklineChart, BarChart, InformationCard},
        data () {
            return {
                hourLabels: ['09:00', '15:00', '21:00', '03:00'],
                hourValues: [4, 1, 10, 3],
                dayLabels: ['Seg', 'Ter', 'Qua', 'Qui', 'Sex', 'Sáb', 'Dom'],
                dayValues: [20, 40, 10, 100, 2, 45, 60],
                monthLabels: [
                    'Jan.', 'Fev.', 'Mar.', 'Abr.', 'Mai.', 'Jun.',
                    'Jul.', 'Ago.', 'Set.', 'Out.', 'Nov.', 'Dez.'
                ],
                monthValues: [
                    300, 450, 200, 500, 600, 452,
                    121, 876, 1000, 154, 400, 300
                ],
                barChartValues: [
                    {
                        name: 'Em andamento',
                        data: [44, 55, 57, 56, 61, 58, 63, 60, 66]
                    },
                    {
                        name: 'Concluídas',
                        data: [76, 85, 101, 98, 87, 105, 91, 114, 94]
                    },
                    {
                        name: 'Não atendidas',
                        data: [35, 41, 36, 26, 45, 48, 52, 53, 41]
                    },
                ],
            }
        }
    }
</script>