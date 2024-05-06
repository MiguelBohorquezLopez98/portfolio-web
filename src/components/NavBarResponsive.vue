<template>
    <div>
        <v-app-bar app color="#03476F" dark flat class="px-12">
            <v-icon color="yellow" left class="mr-2">fas fa-signature</v-icon>
            Miguel Bohórquez
            <v-spacer></v-spacer>
            <!-- Botón Hamburguesa -->
            <v-btn icon ref="menuButton" @click="menu = !menu">
                <v-icon>fa-solid fa-bars</v-icon>
            </v-btn>
            
            <!-- Menú desplegable alineado a la derecha -->
            <v-menu v-model="menu" :close-on-content-click="false"
                right
                :attach="menuButton ? $refs.menuButton : undefined">
                <v-list dense>
                    <v-list-item link @click="menu = false" to="/">
                        <v-list-item-icon>
                            <v-icon>fa-solid fa-house</v-icon>
                        </v-list-item-icon>
                        <v-list-item-title>Home</v-list-item-title>
                    </v-list-item>
                    <v-list-item link @click="menu = false" to="/about">
                        <v-list-item-icon>
                            <v-icon>fa-solid fa-info</v-icon>
                        </v-list-item-icon>
                        <v-list-item-title>About</v-list-item-title>
                    </v-list-item>
                    <v-list-item link @click="menu = false" to="/contact">
                        <v-list-item-icon>
                            <v-icon>fa-solid fa-address-book</v-icon>
                        </v-list-item-icon>
                        <v-list-item-title>Contact</v-list-item-title>
                    </v-list-item>
                </v-list>
            </v-menu>
        </v-app-bar>
    </div>
</template>



<script>
export default {
    data() {
        return {
            menu: false,
        };
    },
    mounted() {
        this.$nextTick(() => {
            // Asegúrate de que las referencias y el DOM estén listos
            console.log(this.$refs.menuButton);
        });
    },
    methods: {
        toggleMenu() {
            this.menu = !this.menu;
        }
    }
};
</script>

<style src="../assets/css/styles.css"></style>