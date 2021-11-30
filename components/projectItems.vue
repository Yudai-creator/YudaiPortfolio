<template name="ProjectItems">
    <div ref="project" class="container">
        <div class="project-description">
            <h2>{{projectTitle}}</h2>
            <p>{{description}}</p>
            <a href="#">Go live</a>
            
        </div>
        
        <figure class="img-container">
            <img :src="imgUrl">
        </figure>
        
    </div>
        
    
        
</template>
<script>


import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/dist/ScrollTrigger";
gsap.registerPlugin(ScrollTrigger);

//style="background: url('/imgs/Thumbnail.png')"
//<ProjectItems  style="background: url('/imgs/Thumbnail.png')"  projectTitle="My portfolio" action="Code ->" description="My portfolio of projects, to show my latest work. Made with Nuxt.js, Sass and GSAP for the animations."/>

export default {
    props: {
        projectTitle: String,
        imgUrl: String,
        description: String,
        action: String
    },
    mounted(){
        const {project} = this.$refs

        const tl = new gsap.timeline();

        tl.to(project, {duration: .5, backgroundSize: 'cover', backgroundPosition: 'center'})

        
    }
}
</script>

<style lang="scss" scoped>
@use '~/assets/styles/global_variables/variables' as *;


.container{
    display: flex;
    justify-content: space-evenly;
    padding: 30px;

    .img-container{
        img{
            max-width: 400px;
            max-height: 400px;
            box-shadow: 3px 3px 5px rgb(196, 195, 195), -3px -3px 5px rgb(196, 195, 195);
        }
    }

    .project-description{
        p{
            max-width: 400px;
            font-weight: 500;
            margin-top: 5px;
        }

        a{
            text-decoration: none;
            position: relative;
            top: 30px;

            background-color: $accent;
            padding: 10px;
            border-radius: 5px;
            font-family: $font;
            font-weight: 600;
            color: $secondary;
        }
    }
}



@media (max-width: $phone-size){
    
    .container{
        display: block;
        
        .img-container{
            img{
                width: 250px;
                height: 200px;
            }
        }
    }
    
    
}

@media (max-width: 375px){
    
}

</style>