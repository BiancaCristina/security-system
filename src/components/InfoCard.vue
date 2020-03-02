<template>
    <v-card
            class="mt-4 mx-auto"
            max-width="300"
            max-height="300"
    >
        <v-row>
            <v-col>
                <v-sheet
                        class="v-sheet--offset ml-2"
                        :color="backgroundColor"
                        elevation="12"
                        max-width="120"
                        max-height="100"
                        height="80"
                >
                    <v-row class="pa-4" md="auto" justify="center" align="center">
                        <v-icon x-large color="white">{{icon}}</v-icon>
                    </v-row>
                </v-sheet>
            </v-col>

            <v-col>
                <v-card-text class="pt-0">
                    <div class="subheading font-weight-light grey--text">{{information}}</div>
                    <div class="title font-weight-light mb-2">{{value}}</div>
                </v-card-text>
            </v-col>
        </v-row>

        <v-divider class="my-0 mx-4 mt-n4" />
        <div class="mx-4 pt-1 pb-2">
            <v-icon
                    class="mr-2"
                    small
            >
                mdi-clock
            </v-icon>
            <span class="caption grey--text font-weight-light">Última atualização {{lastUpdate}}</span>
        </div>

    </v-card>
</template>

<script>
    export default {
        name: "InformationCard",

        props: {
            backgroundColor: {type: String, default: 'white'},
            information: String,
            value: String,
            lastUpdate: {type: String, required: true},
            icon: {type: String, required: true},
        },
    }
</script>

<style scoped>
    .v-sheet--offset {
        top: -24px;
        position: relative;
    }
</style>