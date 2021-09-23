<template name="ServiceDetails">
    <div ref="service">
        <figure>
            <img :src= "icon">
        </figure>
        <h3>{{headline}}</h3>
        <p>{{text}}</p>
    </div>
</template>
<script>
import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/dist/ScrollTrigger";
gsap.registerPlugin(ScrollTrigger);

import ServiceDetails from '../components/ServiceDetails.vue'
export default {
    components:{
        ServiceDetails
    },
    props: {
        icon: String,
        headline: String,
        text: String
    },
    mounted(){
        const {service} = this.$refs

        gsap.fromTo(service, {scale: 0.9}, 
        {scrollTrigger: {
            trigger: service,
            //start: "top center",
            markers: false,
            scrub: true,
            toggleActions: "restart pause reverse none"
        }, 
        duration: .5, scale: 1.1, y: -10, boxShadow: "2px 2px 2px #000, -2px -2px 2px #000"})

    }
}

//basic scroll trigger
//gsap.fromTo(service, {opacity: 0}, {scrollTrigger: service, duration: 2, opacity: 1})
</script>
<style lang="scss" scoped>
@use '~/assets/styles/global_variables/variables' as *;

div{
    width: 450px;
    height: 450px;

    border-radius: 30px;
    background-color: $secondary;
    //box-shadow: 3px 3px 5px black, -3px -3px 5px black;

    //border: 3px solid $highlight;

    padding: 40px;

    img{
        width: 50px;
        height: 50px;
        margin-top: 20px;
    }

    h3{
        font-size: 1.9em;
        margin-top: 20px;
    }

    p{
        font-size: 1.4em;
        margin-top: 20px;
    }
}
@media (max-width: $tablet-size){

    div{
        width: 350px;
        height: 350px;

        img{
            width: 40px;
            height: 40px;
        }

        h3{
            font-size: 1.4em;
        }

        p{
            font-size: 1.2em;
        }
    }   
}

@media (max-width: $phone-size){
    div{
        width: 300px;
        height: 300px;

        margin-left: 80px;
        margin-bottom: 80px;

        img{
            width: 40px;
            height: 40px;
        }

        h3{
            font-size: 1.2em;
        }

        p{
            font-size: 1em;
        }
    }
}

@media (max-width: 375px){
    div{
        margin-left: 32px;
    }
}
</style>