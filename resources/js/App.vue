<template>
    <div class="flex flex-col">
        <Navbar></Navbar>
        <div class="container mx-auto">
            <router-view/>
        </div>
        <div>
            <h1>Ant design integrate</h1>
            <date-picker />
        </div>
    </div>
</template>

<script>
import Navbar from './components/Navbar';
import {DatePicker} from 'ant-design-vue';

export default {
    name: 'App',
    components: {
        Navbar,
        DatePicker,
    },
    watch: {
        $route(to, from) {
            this.$store.dispatch('titles/setPageTitle', to.meta.title);
        },
    },
};
</script>

<style lang="scss" scoped>
@import "../sass/app";
</style>
