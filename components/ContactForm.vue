<template name="ContactForm">
    <div class="container">
        <div class="contact-form">
            <div class="contact__text">
                <h2>Are you ready?</h2>
                <p>Let's connect and share some ideas.</p>
            </div>
            
            <form>
                <div class="form__field">
                    <label for="name">Your name</label><br>
                    <input class="form__control" type="text" name="name" required><br>  
                </div>
                
                
                <div class="form__field">
                    <label for="mail">Your email</label><br>
                    <input class="form__control" type="email" name="email" required><br>    
                </div>

                <div class="form__field">
                    <label for="message">Your message</label><br>
                    <textarea class="form__control" name="message" cols="10" required></textarea>
                </div>
 
                <input class="form__submit" type="submit" value="Send">
                
            </form>
        </div>
    </div>
</template>
<script>



export default  {
    
}
</script>

<style lang="scss" scoped>
@use '~/assets/styles/global_variables/variables' as *;

.container{
    //background-color: #cac8c8;
    display: flex;
    justify-content: center;

    label{
        font-weight: 600;
        margin-bottom: 5px;
    }

    .contact__text{
        display: flex;
        align-items: center;
        flex-direction: column;

        p{
            margin-top: 20px;
            margin-bottom: 20px;
        }
    }

    .form__control{
        width: 500px;
        height: 30px;
        background: #dddddd;
        border: none;
        outline: none;
        border-bottom: 1px solid $secondary;
        border-radius: 5px;
        color: $secondary;
        margin-bottom: 30px;

        transition: all .5s ease-in-out;

        &:focus{
            border: 1px solid $secondary;
            background: #c2bfdd;
        }
    }

    .form__submit{
        width: 500px;
        height: 30px;
        font-size: 15px;
        font-weight: bold;
        outline: none;
        border: none;
        border-radius: 5px;
        background-color: $accent;
        transition: all .5s ease-in-out;

        &:hover{
            background-color: #e7a90c;
            transform: translateY(-2px);
            cursor: pointer;
        }
    }
}



@media (max-width: $phone-size){
    .container{

        position: relative;
        top: 150px;

        .form__control{
            width: 300px;
        }

        .form__submit{
            width: 300px;
        }
    } 
}




</style>