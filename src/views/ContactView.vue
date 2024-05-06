<template>
    <NavBar />
    <div class="contact">
        <h1>This is a contact page</h1>
    </div>
</template>

<script>
import { defineComponent } from 'vue';

// Components
import NavBar from '../components/NavBar.vue';

export default defineComponent({
    name: 'ContactView',

    components: {
        NavBar,
    },
});
</script>