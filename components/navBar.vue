<template name="NavBar">
    <div class="nav-wrapper">

        <nuxt-link class="logo" to="/"><img src="/logo/VER_VERTICAL_FULL.png"></nuxt-link>
        
        <a ref="toggle" id="toggle-menu" @click="isActive = !isActive" href="#">
            <svg  xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
                <path d="M4 6h16v2H4zm0 5h16v2H4zm0 5h16v2H4z" fill="#02112E"/>
            </svg>
        </a>

        <nav class="navbar">
            <ul :class="{'show' : isActive, 'hide' : !isActive}" ref="navLinks" class="nav-links">
                <li id="nav-item-1">
                    <nuxt-link to='/'>Home</nuxt-link>
                </li>
                <li id="nav-item-2">
                    <nuxt-link to='/about'>About</nuxt-link>
                </li>    
                <li id="nav-item-3">
                    <nuxt-link to='/projects'>Projects</nuxt-link>
                </li>
                <li id="nav-item-5">
                    <nuxt-link to='/blog'>Blog</nuxt-link>
                </li>
                <li id="nav-item-4">
                    <nuxt-link to='/services'>Services</nuxt-link>
                </li>          
            </ul>
        </nav>
        <!--
        <figure>
            <img src="../static/imgs/favicon4-01.png">
        </figure>
        -->
        <!--
        <div class="lang">
            <nuxt-link to="/es">ES</nuxt-link>
            <nuxt-link to="/en">EN</nuxt-link>
        </div>
        -->
    </div>
    
</template>
<script>

//import NavBar from '../components/NavBar.vue'
import { gsap } from "gsap";

import { CSSRulePlugin } from "gsap/dist/CSSRulePlugin";
gsap.registerPlugin(CSSRulePlugin );
export default {
    data() {
        return{
            isActive: false,
        }
        
    },
    mounted() {
        const {toggle, navLinks} = this.$refs

        toggle.addEventListener("click", () => {
            gsap.fromTo(toggle, {x: -5, rotate: 20}, {duration: .8, x: 0, rotate: 0, ease: "bounce.out"})
        })

    }

}

</script>

<style lang="scss" scoped>
@use '~/assets/styles/global_variables/variables' as *;

@mixin tranistion-hover{
    transition: all .3s ease-in-out;
}

    #toggle-menu{
        display: none;
    }

    .nav-wrapper{
        display: flex;
        align-items: center;
        justify-content: space-between;
        position: relative;
        padding: 10px;

        img{
            width: 80px;
            height: 80px;
            margin-left: 110px;
        }
    }

    .navbar{
        margin: 30px;
        background: $primary;
        position: relative;
        margin-right: 120px;
    }

    ul{
        list-style: none;
        display: flex;
        align-items: center;
        position: relative;
    }

    li{
        margin-left: 100px;
        border-bottom: 1px transparent;
        position: relative;
        @include tranistion-hover();
        
        a{
            text-decoration: none;
            color: $secondary;
            font-family: $font;
            font-weight: bold;

            position: relative;
        }
    }

    #nav-item-1::after{
        content: '';
        position: absolute;
        transform-origin: center;
        
        width: 0px;
        height: 2px;
        background-color: $terciary;

        top: 100%;
        left: 0%;
        
        @include tranistion-hover();
        
    }
    #nav-item-1:hover::after{
            width: 50px;
    }

    #nav-item-2::after{
        content: '';
        position: absolute;
        transform-origin: center;
       
        width: 0px;
        height: 2px;
        background-color: $terciary;

        top: 100%;
        left: 0%;
        
        @include tranistion-hover();
    }

    #nav-item-2:hover::after{
        width: 52px;
    }

    #nav-item-3::after{
        content: '';
        position: absolute;
        transform-origin: center;

        width: 0px;
        height: 2px;
        background-color: $terciary;
       
        top: 100%;
        left: 0%;
       
        @include tranistion-hover();
    }

    #nav-item-3:hover::after{
        width: 57px;
    }

    #nav-item-4::after{
        content: '';
        position: absolute;
        transform-origin: center;

        width: 0px;
        height: 2px;
        background-color: $terciary;
        
        top: 100%;
        left: 0%;
        
        @include tranistion-hover();
    } 
    
    #nav-item-4:hover::after{
        width: 59px
    }

    #nav-item-5::after{
        content: '';
        position: absolute;
        transform-origin: center;

        width: 0px;
        height: 2px;
        background-color: $terciary;
        
        top: 100%;
        left: 0%;
        
        @include tranistion-hover();
    } 
    
    #nav-item-5:hover::after{
        width: 39px
    }

@media (min-width: $extra-large-screen){
    .nav-wrapper{
        a{
            font-size: 1.75em;
        }

        img{
            width: 150px;
            height: 150px;
        }
    }

    #nav-item-1:hover::after{
            width: 80px;
    }

    #nav-item-2:hover::after{
            width: 80px;
    }

    #nav-item-3:hover::after{
            width: 98px;
    }

    #nav-item-4:hover::after{
            width: 100px;
    }

    #nav-item-5:hover::after{
            width: 70px;
    }
    
    
}



//table-landscape-size
@media (max-width: $tablet-landscape-size){
    *::after{
        display: none;
    }
}


@media (max-width: $tablet-size){
    *::after{
        display: none;
    }

    .nav-wrapper{
        left: -70px;
    }


}    

//phone-landscape-size
@media (max-width: $phone-landscape-size){
    .nav-wrapper{
        display: inline;
        overflow: hidden;
    }

    #toggle-menu{
        display: block;
        
        background-color: $secondary;
        width: 50px;
        border-radius: 50%;
        &:hover{
            cursor: pointer;
        }
    }

    

    .nav-links{
        flex-direction: column;
        
        background-color: $primary;
        z-index: 2;
        
        overflow: hidden;
        transition: all .5s ease-in-out;

        li{
            margin-bottom: 15px;
            text-align: center;
            right: 50px;
        }
    }

    .show{
        //display: block;
        height: 140px;
        transition: all .5s ease-in-out;
        opacity: 1;
    }

    .hide{
        height: 0;
        transition: all .5s ease-in-out;
        opacity: 0;
    }
    

}    

@media (max-width: $phone-size){
    *::after{
        display: none;
    }

    .nav-wrapper{
        display: inline;
        overflow: hidden;
    }

    #toggle-menu{
        display: block;
        margin-left: 45px;
        position: relative;
        left: 300px;
        &:hover{
            cursor: pointer;
        }
    }

    .nav-links{
        flex-direction: column;
        position: relative;
        left: 100px;  
        background-color: $primary;
        z-index: 2;
        
        overflow: hidden;
        transition: all .5s ease-in-out;

        li{
            margin-bottom: 15px;
            text-align: center;
            right: 50px;
        }
    }

    .logo{
        position: relative;
        top: 50px;
        right: 20px;
    }

    .show{
        //display: block;
        height: 180px;
        transition: all .5s ease-in-out;
        opacity: 1;
    }

    .hide{
        height: 0;
        transition: all .5s ease-in-out;
        opacity: 0;
    }
    
}

    
</style> 
