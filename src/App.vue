<template>
    <v-app>
        <NavBar />
        <router-view></router-view>
    </v-app>
</template>

<script>
    import NavBar from "./components/NavBar";

    export default {
        name: 'App',
        components: {NavBar},

        data () {
            return {
                items: [
                    { title: 'Home', icon: 'mdi-home-city' },
                    { title: 'My Account', icon: 'mdi-account' },
                    { title: 'Users', icon: 'mdi-account-group-outline' },
                ],
            }
        },
    };
</script>

<style scoped>
</style>