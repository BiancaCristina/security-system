<template>
    <v-container class="grey lighten-5" flat>
        <v-row>
            <v-col>
                <Sparkline
                        v-bind:labels="hourLabels"
                        v-bind:values="hourValues"
                        lastUpdate="terça-feira 12:33"
                        title="Registro de Ocorrências (Diário)"
                />
            </v-col>

            <v-col>
                <Sparkline
                        v-bind:labels="dayLabels"
                        v-bind:values="dayValues"
                        lastUpdate="terça-feira 12:33"
                        title="Registro de Ocorrências (Semanal)"
                        backgroundColor="#E74C3C"
                />
            </v-col>

            <v-col>
                <Sparkline
                        v-bind:labels="monthLabels"
                        v-bind:values="monthValues"
                        lastUpdate="terça-feira 12:33"
                        title="Registro de Ocorrências (Anual)"
                        backgroundColor="#27AE60"
                />
            </v-col>

        </v-row>
    </v-container>
</template>

<script>
    import Sparkline from "../components/Sparkline";

    export default {
        name: 'Dashboard',
        components: {Sparkline},
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

            }
        },

        methods: {
            alerta() {
                alert('ks')
            }
        }
    }
</script>