<script>
import Home from './Home.vue'
import Posts from './Posts.vue'
import Archieved from './Archieved.vue'
export default {
    props: ['title'],
    components: {
        Home,
        Posts,
        Archieved
    },
    data() {
        return {
            tabs: ['Home', 'Posts', 'Archieved'],
            currentTab: 'Home'
        }
    },
    methods: {
        changeTab(tab) {
            this.currentTab = tab
        }
    }
}
</script>
<template>
    <div>
        <header>{{title}}</header>
        <button v-for="tab in tabs" :key="tab" @click="changeTab(tab)">
            {{ tab }}
        </button>
        <component :is="currentTab"></component>
    </div>
</template>