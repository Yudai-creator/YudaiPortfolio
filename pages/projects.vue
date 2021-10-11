<template name="projects">
    <div>
        <navBar/>
        <main class="projects">
            <section class="projects-headline">
                <h1>
                    Latest Work<span>.</span>
                </h1>
                <ScrollMouse/>
            </section>
            <section class="projects-portfolio">
                <projectItems  style="background: url('/imgs/Thumbnail.png')"  projectTitle="My portfolio" action="Code ->" description="My portfolio of projects, to show my latest work. Made with Nuxt.js, Sass and GSAP for the animations."/>
                <projectItems  style="background: url('/imgs/Afrorraices.png')"  projectTitle="Afrorraices Blog" action="Go Live ->" description="A blog website made with blogger CMS, but with personal customization of HTML and CSS to make it more appealing."/>
            </section>
            <section class="projects-portfolio">
                <projectItems  style="background: url('/imgs/codepen.png')"  projectTitle="My Codepen Profile" action="Go Live ->" description="Thi is my Codepen profile where I store my work refering to animations and code snippets I share in Twitter."/>  
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
    justify-content: space-around;
    align-items: center;

    height: 80vh;
    margin-top: 40px;
}




.projects-enter-active, .projects-leave-active{
    transition: opacity .5s ease-in-out;
}

.projects-enter, .projects-leave-active{
    opacity: 0;
}

@media (max-width: $tablet-size){
    .projects-portfolio{
        height: 50vh;
    }
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