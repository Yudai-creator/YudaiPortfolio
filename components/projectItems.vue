<template name="ProjectItems">
    <div ref="project" class="container">
        
        <div class="project-box">
        </div>   
        <div class="text">
            <h3 class="project__text">{{projectTitle}}</h3>
            <p class="project__text">{{description}}</p><br>
            <a href="#">{{action}}</a>
        </div>
    </div>
        
    
        
</template>
<script>


import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/dist/ScrollTrigger";
gsap.registerPlugin(ScrollTrigger);

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
    width: 500px;
    height: 400px;
    
    border-radius: 10px;
    //border: 5px solid $secondary;

    //cursor: pointer;

    position: relative;
    

    transition: all .3s ease-in-out;

    //background-image: url("../assets/blog.png");

    &:hover{
        background-color: rgba(219, 219, 219, 0.89);
    }

    .project-box{
        position: relative;
        width: 490px;
        height: 400px;
        a{
            text-decoration: none;
            
            color: $secondary;
            
            
        }
        
    }
}

@media (max-width: $tablet-size){
    .container{
        width: 400px;
        height: 300px;
    }

    .project-box{
        transform: translateY(100px);
    }
}

@media (max-width: $phone-size){
    .container{
        width: 380px;
        height: 300px;

        .project-box{
            transform: translateY(280px);
        }
    }
}

@media (max-width: 375px){
    .container{
        width: 320px;
        height: 270px;
    }
}

</style>