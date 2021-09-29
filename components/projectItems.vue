<template name="projectItem">
    
        <div ref="project" class="project-box">
            <h3>{{projectTitle}}</h3>
            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptate inventore laborum corporis ex expedita, sit porro voluptas beatae libero voluptatibus!</p>
        </div>
    
        
</template>
<script>
import projectItems from './projectItems.vue'

import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/dist/ScrollTrigger";
gsap.registerPlugin(ScrollTrigger);

export default {
    components:{
        projectItems,
        
    },
    props: {
        projectTitle: String,
        imgUrl: String,
    },
    mounted(){
        const {project} = this.$refs

        const tl = new gsap.timeline();

        tl.to(project, {duration: .5, backgroundSize: 'cover', backgroundPosition: 'center'})

        
    }
}
</script>

<style lang="scss">
@use '~/assets/styles/global_variables/variables' as *;


.project-box{
    width: 420px;
    height: 350px;

    display: flex;

    background-size: cover;
    background-position: center;

    border-radius: 20px;
    border: 2px solid $secondary;

    //cursor: pointer;

    position: relative;
    

    transition: all .3s ease-in-out;

    //background-image: url("../assets/blog.png");

    //&:hover{
        //box-shadow: -10px 10px  $secondary;
        //transform: translateY(-10px);
    //}

    h3{
        position: absolute;
        top: 100%;

        margin-top: 20px;
    }

    p{
      position: absolute;
        top: 100%;  
        margin-top: 50px;
    }
}

@media (max-width: $phone-size){
    .project-box{
        width: 380px;
        height: 300px;
    }
}

@media (max-width: 375px){
    .project-box{
        width: 320px;
        height: 270px;
    }
}

</style>