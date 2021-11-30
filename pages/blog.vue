<template name="component-name">
    <div class="container">
        <NavBar/>
        <img src="/blog/undraw_under_construction_-46-pa.svg" alt="Under Construction">
        <h1>Under Construction 🚧</h1>
    </div>
</template>
<script>
// JS
import NavBar from '../components/NavBar.vue'
export default {
    components:{
    NavBar
  }
}
</script>
<style lang="scss" scoped>
@use '~/assets/styles/global_variables/variables' as *;
    *{
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }


  .container{
    font-family: $font;
    color: $secondary;
  }

  img{
      max-width: 750px;
      position: relative;
      left: 300px;
    }

    h1{
        position: relative;
        left: 450px;
    }

</style>