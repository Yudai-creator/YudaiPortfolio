<template name="about">
    <div>
        <navBar/>
        <header class="about-header">
            <h1>{{title}}<span>.</span>
            </h1>
            <ScrollMouse/>  
        </header>
        <main class="about-content">
            <section class="about-presentation">
                <div class="about-text">
                    <p>I am currently working as a Front-End Developer.<br> 
                    I have experience as a UI/UX designer and<br> 
                    building beautiful websites its my gig.<br>
                    <br> 
                    Along with deep undestanding of<br> 
                    Javascript, Vue, HTML and CSS my mission<br>
                    is to bring users a pleasent experience when<br>
                    visiting one of my websites.
                    <br>

                    </p>
                </div>
                <ProfileInfo/> 
            </section>
            <section class="about-experience">
                    <ExperienceSvg/>
                    
                    <div class="about-experience-text">
                        <h2>Experience<span>.</span></h2>
                        <p>
                        I started working as a Web developer since 2020, doing freelance jobs 
                        for businesses in my homeland, now I my intentions are to go abroad and
                        expand my services to everyone.
                        </p>
                        <a class="CV" href="https://drive.google.com/file/d/1xfLunaGF-vwHQhJiXdO_FNMY3kGBuyeB/view?usp=sharing">Download CV -></a>
                    </div> 
            </section>

            <section class="about-techstack">
                <div class="about-techstack-text">
                    <h2>My Tech Stack<span>.</span></h2>
                    <p>
                        I got five years of programming experience.<br>
                        <br>
                        I build my projects using HTML, CSS and Javascript mainly,
                        but I also have abilities working with Vue.js and Nuxt.js
                        to create strong websites. Along with knowledge about powerful
                        libraries and frameworks like GSAP, Tailwind CSS, SASS.<br>
                        <br>
                    </p> 
                </div>
                <TechstackSvg/>   
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
import RichText from '../components/RichText.vue'
import PageFooter from '../components/PageFooter.vue'
import ProfileInfo from '../components/ProfileInfo.vue'
import ExperienceSvg from '../components/ExperienceSvg.vue'
import TechstackSvg from '../components/TechstackSvg.vue'
import ScrollMouse from '../components/ScrollMouse.vue'
export default {
    components:{
    navBar,
    PageFooter,
    RichText,
    ProfileInfo,
    ExperienceSvg,
    TechstackSvg,
    ScrollMouse
  },
  data (){
      return {
          title: "About me"
      }
  },
  head(){
        return{
            title: 'About me',

        }
    },
    transition: 'about'
}
</script>
<style lang="scss">
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

.about-header{
    display: flex;
    justify-content: space-between;
    align-items: center;

    position: relative;

    margin-left: 122px;
    margin-right: 140px;
    margin-top: 50px;

    h1{
        font-size: 3.5em;
    }
}

.about-presentation{
    display: flex;
    justify-content: space-between;

    margin-left: 120px;
    margin-right: 280px;

    height: 70vh;

    position: relative;
    p{
      color: $secondary;
      font-size: 1.5em;
      margin-top: 50px;

      font-weight: 600;
    }
}
    


.about-experience{
    display: flex;
    justify-content: space-between;
    align-items: center;

    margin-left: 100px;
    margin-right: 70px;

    p{
        font-size: 1.5em;
        font-weight: 600;
    }

    h2{
        font-size: 2.5em;
        margin-bottom: 10px;
    }

    a{  
        font-size: 1.2em;
        text-decoration: none;

        color: $secondary;
    }
}



.about-techstack{
    display: flex;
    justify-content: space-between;
    align-items: center;

    position: relative;

    margin-right: 80px;
    margin-left: 80px;

    p{
        font-size: 1.5em;
        font-weight: 600;
    }
    h2{
        font-size: 2.5em;
        margin-bottom: 10px;
    }
}


.CV{
    background-color: $accent;
    padding: 5px;
    border-radius: 5px;
    font-family: $font;
    font-weight: 600;

    position: relative;
    top: 15px;
}

.about-enter-active, .about-leave-active{
    transition: opacity .5s ease-in-out;
}

.about-enter, .about-leave-active{
    opacity: 0;
}

@media (max-width: $tablet-size){
    .about-header{
        margin: 30px;
        margin-left: 50px;
        h1{
            font-size: 2.5em;
        }
    }

    .about-text{
        p{
            font-size: 1.2em;
        }
    }
    
    .mouse-shadow{
        display: none;
    }

    .about-presentation{
        display: inline;
        text-align: center;
        .about-text{
            position: relative;
            width: 100%;
        }
    }


}

@media (max-width: $phone-size){
    
    .about-header{
        margin-left: 45px;
        h1{
            font-size: 2.5em;
        }
    }
    
    .mouse-shadow{
        display: none;
    }

    .about-presentation{
        display: inline;
        .about-text{
            position: relative;
            top: 200px;
            width: 100%;
            padding: 30px;
            p{
                font-size: 1em;
            }
        }
    }

    .about-credentials{
        top: -180px;
        left: 30px;
    }

    .about-profile-pic{ 
    img{
        position: relative;
        left: 50px;
        width: 200px;
        height: 200px;
        animation: none;
        }
    }

    .about-experience{
        display: inline;
        .about-experience-text{
            padding: 30px;
            p{
                font-size: 1em;
                font-weight: 600;
            }

            h2{
                font-size: 1.5em;
            }
        }  
        
        #remote{
            position: relative;
            left: 30px;
            width: 300px;
            height: 300px;
        }
        #about-blob{
            display: none;
        }
    }

    .about-techstack{
        display: inline;
        .about-techstack-text{
            padding: 30px;
            p{
                font-size: 1em;
                font-weight: 600;
            }

            h2{
                font-size: 1.5em;
            }
        }
        .about-techstack-graphics{
            #blob{
                display: none;
            }
            #knowledge-svg{
                position: relative;
                width: 300px;
                height: 300px;
            }
        }
    }

}

</style>