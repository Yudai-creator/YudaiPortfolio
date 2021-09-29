<template name="projects">
    <div>
        <navBar/>
        <main class="projects">
            <section class="projects-headline">
                <h1>
                    Projects<span>.</span>
                </h1>
                <ScrollMouse/>
            </section>
            <section class="projects-portfolio">
                <projectItems  style="background: url('/imgs/portfolio.png')"  projectTitle="My portfolio"/>
                <projectItems  style="background: url('/imgs/blog.png')"  projectTitle="Afrorraices Blog"/>
            </section>
            <section class="projects-portfolio">
                <projectItems  style="background: url('/imgs/codepen.png')"  projectTitle="My Codepen Profile"/>  
            </section>
            <footer>
                <PageFooter/>
            </footer>
        </main>
    </div>
</template>
<script>
// JS
import navBar from '../components/navBar.vue'
import projectItem from '../components/projectItems.vue'
import PageFooter from '../components/PageFooter.vue'
import ScrollMouse from '../components/ScrollMouse.vue'
export default {
    components:{
    navBar,
    projectItem,
    PageFooter,
    ScrollMouse
  },
  data() {
      return {
          
      }
  }, 
    head(){
        return{
            title: 'Projects'
        }
    },
    transition: 'projects'
}
</script>
<style lang="scss" >
@use '~/assets/styles/global_variables/variables' as *;

*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}


body{
    background: $primary;
    font-family: $font;
    color: $secondary;
}

.projects-headline{
    position: relative;
    display: flex;
    justify-content: space-between;
    align-items: center;

    margin-left: 122px;
    margin-right: 135px;
    margin-top: 50px;

    h1{
        font-size: 3.5em;
    }
}

.projects-portfolio{
    position: relative;
    display: flex;
    justify-content: space-between;
    align-items: center;

    height: 80vh;
    margin-left: 180px;
    margin-right: 200px;
    margin-top: 40px;
}




.projects-enter-active, .projects-leave-active{
    transition: opacity .5s ease-in-out;
}

.projects-enter, .projects-leave-active{
    opacity: 0;
}


@media (max-width: $phone-size){
    .projects-portfolio{
        flex-direction: column;
        justify-content: space-evenly;
    }

    .projects-headline{
        margin-left: 50px;
    }
}

</style>