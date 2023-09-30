<script setup>
import headerviewVue from '../components/headerview.vue';
import navbar from '../components/navbar.vue';
import collection from '../components/collection.vue';
import spacialPro from '../components/spacialPro.vue';
import blogs from '../components/blogs.vue';
import AboutViewVue from './AboutView.vue';
import popular from '../components/popular.vue';
import newsletter from '../components/newsletter.vue';
import footerview from '../components/footer.vue';
</script>

<template>
  <main>
    <navbar/>
    <headerviewVue/>
    <collection/>
    <spacialPro/>
    <blogs/>
    <AboutViewVue/>
    <popular/>
    <newsletter/>
    <footerview/>
  </main>
</template>
<script>
export default {
    mounted(){
        let user = localStorage.getItem('user_info');
        if(!user){
            this.$router.push({name:'login'})
        }
    }
}
</script>