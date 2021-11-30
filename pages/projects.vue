<template name="projects">
    <div>
        <NavBar/>
        <main class="projects">
            <section class="projects-headline">
                <h1>
                    Latest Work<span>.</span>
                </h1>
                <ScrollMouse/>
            </section>
            <section class="projects-portfolio">
                <ProjectItems :imgUrl="'/imgs/Afrorraices.png'"  projectTitle="Afrorraices Blog" description="Blog build with Blogger CMS and customized with a unique skin, using HTML and CSS for a more appealing look."/>
                <ProjectItems :imgUrl="'/imgs/03.jpg'"  projectTitle="My personal website" description="A website build to showcase who am I and share what I'm working on, the main idea is to turn it into my center of operations, where everyone can see what Yudai Creator is all about. Build using Nuxt and SCSS, deployed on Netlify."/>
                <ProjectItems :imgUrl="'/imgs/codepen.png'"  projectTitle="CodePen Profile" description="Visit my codepen profile, there I share code snippets about the animations I make."/>
            </section>
           
            <footer>
                <PageFooter/>
            </footer>
        </main>
    </div>
</template>
<script>
// JS
import NavBar from '../components/NavBar.vue'
import ProjectItems from '../components/ProjectItems.vue'
import PageFooter from '../components/PageFooter.vue'
import ScrollMouse from '../components/ScrollMouse.vue'
export default {
    components:{
    NavBar,
    ProjectItems,
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
    padding: 20px;
}


.projects-enter-active, .projects-leave-active{
    transition: opacity .5s ease-in-out;
}

.projects-enter, .projects-leave-active{
    opacity: 0;
}

@media (max-width: $tablet-size){
    
}


@media (max-width: $phone-size){

    .projects-headline{
        margin-left: 50px;
    }

    footer{
        position: relative;
        bottom: 0;
    }
}

</style>