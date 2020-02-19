<template>
    <nav>
         <v-toolbar  app class="text-uppercase grey--text">
             <v-app-bar-nav-icon flat color="grey" @click="drawer = !drawer"></v-app-bar-nav-icon>
             <v-toolbar-title>
            <span class="font-weight-light">todo</span>
            <span>obada</span>
           </v-toolbar-title>
            <v-spacer></v-spacer>
        <v-btn flat color="grey">
            <span>sign out</span>
            <v-icon right="">exit_to_app</v-icon>
        </v-btn>
        </v-toolbar>

        <v-navigation-drawer app class="primary" v-model="drawer">
            <v-list >
                <v-list-item class="white--text" v-bind:key="link.text" v-for="link in links" router :to="link.route" >
                   <v-list-tile-action>
                       <v-icon left class="white--text">{{link.icon}}</v-icon>
                   </v-list-tile-action>
                    <v-list-tile-content>
                        <v-list-tile-title class="white--text">
                            {{link.text}}
                        </v-list-tile-title>
                    </v-list-tile-content>
                </v-list-item>
                 </v-list>

        </v-navigation-drawer>
    </nav>
</template>

<script>
    export default {
        name: "navBar",
        data(){
            return {
                drawer : false,
                links :[
                    { icon: "dashboard", text: "Dashboard", route: "/" },
                    { icon: "folder", text: "My Projects", route: "/projects" },
                    { icon: "person", text: "Team", route: "/team" }
                ]
            }
        }
    }
</script>

<style scoped>

</style>