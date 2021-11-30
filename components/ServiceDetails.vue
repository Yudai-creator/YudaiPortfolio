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


export default {
    props: {
        icon: String,
        headline: String,
        text: String
    },
    mounted(){
        const {service} = this.$refs

        gsap.fromTo(service, { y: 50, opacity: 0}, 
        {scrollTrigger: {trigger: service, start: 'top 80%'}, 
        duration: 1, y: 0, opacity: 1})

    }
}

//basic scroll trigger
//gsap.fromTo(service, {opacity: 0}, {scrollTrigger: service, duration: 2, opacity: 1})
</script>
<style lang="scss" scoped>
@use '~/assets/styles/global_variables/variables' as *;

div{
    width: 250px;
    height: 300px;
    color: $secondary;
    border-radius: 15px;
    //border: 1px solid $secondary;
    background-color: #d6d5d5;

    opacity: 0;
    //box-shadow: 3px 3px 5px black, -3px -3px 5px black;

    //border: 3px solid $highlight;

    padding: 30px;

    img{
        width: 30px;
        height: 30px;
        margin-top: 5px;
    }

    h3{
        font-size: 1.3em;
        margin-top: 10px;
    }

    p{
        font-size: 1em;
        margin-top: 20px;
    }
}

@media (min-width: $extra-large-screen){
    div{
        width: 300px;
        height: 350px;

        img{
            width: 40px;
            height: 40px;
        }

        h3{
            font-size: 1.8em;
        }

        p{
            font-size: 1.2em;
        }
    }
}

@media (max-width: $tablet-size){

    div{
        width: 170px;
        height: 350px;

        img{
            width: 30px;
            height: 30px;
        }

        h3{
            font-size: 1.1em;
        }

        p{
            font-size: 0.9em;
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