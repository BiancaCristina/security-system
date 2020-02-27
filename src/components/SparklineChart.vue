<template>
    <v-card
            class="mt-4 mx-auto"
            max-width="600"

    >
        <v-sheet
                class="v-sheet--offset mx-auto"
                :color="backgroundColor"
                elevation="12"
                max-width="calc(100% - 32px)"
        >
            <v-sparkline
                    :labels="labels"
                    :value="values"
                    :color="lineColor"
                    line-width="2"
                    padding="16"
            ></v-sparkline>
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
    export default {
        name: "Sparkline",
        props: {
            lineColor: {type: String, default: 'white'},
            backgroundColor: {type: String, default: 'cyan'},
            lastUpdate: {type: String, required: true},
            labels: Array,
            values: Array,
            title: String,
            subheading: String
        }
    }
</script>

<style>
    .v-sheet--offset {
        top: -24px;
        position: relative;
    }
</style>