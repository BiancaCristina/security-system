<template>
    <v-navigation-drawer
        permanent
        expand-on-hover
        dark
        absolute
    >
        <v-list>
            <v-list-item
                link
                class="px-2"
            >
                <v-list-item-avatar>
                    <v-img src="https://randomuser.me/api/portraits/women/3.jpg"></v-img>
                </v-list-item-avatar>

                <v-list-item-title>Random Person</v-list-item-title>
            </v-list-item>
        </v-list>

        <v-divider></v-divider>

        <v-list
                nav
                dense
                v-for="option in options"
                :key="option.title"
        >
            <router-link :to="option.route" v-if="option.icon == 'fas fa-bell'">
                <v-list-item link @click="clearNotifications">
                    <v-list-item-icon>
                        <v-badge
                            color="red"
                            :value="notifications"
                            :content="notifications"
                            dot
                        >
                            <v-icon>{{option.icon}}</v-icon>
                        </v-badge>
                    </v-list-item-icon>

                    <v-list-item-title>
                        {{option.title}}
                    </v-list-item-title>
                </v-list-item>
            </router-link>

            <router-link :to="option.route" v-else>
                <v-list-item link>
                    <v-list-item-icon>
                        <v-icon>{{option.icon}}</v-icon>
                    </v-list-item-icon>
                    <v-list-item-title>{{option.title}}</v-list-item-title>
                </v-list-item>
            </router-link>

        </v-list>
    </v-navigation-drawer>
</template>

<script>
    export default {
        name: "NavBar",

        data() {
            return {
                notifications: 1,

                options: [
                    { title: 'Notificações', icon: 'fas fa-bell', route: '/'},
                    { title: 'Dashboard', icon: 'fas fa-chart-line', route: '/dashboard' },
                    { title: 'Ocorrências', icon: 'fas fa-list-alt', route: '/' },
                ]
            }
        },

        methods: {
            clearNotifications() {
                // Still beta
                if (this.notifications != 0) this.notifications = 0;
                else this.notifications = 1;
            }
        }
    }
</script>

<style scoped>
    a {
        text-decoration: none;
    }
</style>