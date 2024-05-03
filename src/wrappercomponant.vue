<template>
  <div class="container my-2">
    <headercomponant/>
    
  <div class="row justify-content-between">
    <linksescomponant/>
    <bodycomponant/>
  </div>
  <postcomponant/>
  <footerescomponant/>
  </div>
</template>

<script>
import headercomponant from './components/headercomponant.vue';
import bodycomponant from './components/bodycomponant.vue';
import footerescomponant from './components/footerescomponant.vue';
import linksescomponant from  './components/linksescomponant.vue';
import postcomponant from './components/postcomponant.vue'

export default {
    data:()=>({}),
    methodes:{},
    components:{
        bodycomponant,footerescomponant,linksescomponant,headercomponant,postcomponant
    }
}
</script>

<style>

</style>