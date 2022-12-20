<script setup>
    import { reactive, ref } from 'vue'
    import { useRouter } from 'vue-router'

    const router = useRouter()

    let form = reactive({
        email: '',
        password: '',
    })

    let error = ref('')

    const login = async() =>{
        await axios.post('/api/login', form)
            .then(response =>{
                if (response.data.success){
                    localStorage.setItem('token', response.data.data.token)
                    router.push('/admin/home')
                } else {
                    error.value = response.data.message
                }               
            })
    }

</script>

<template>
    <div class="login">
        <div class="formLogin">
            <p class="text-danger" v-if="error">{{ error }}</p>
            <form @submit.prevent="login">
                <input class="input_auth" type="email" placeholder="Enter your Email" v-model="form.email" />
                <br>
                <input class="input_auth" type="password" placeholder="Enter your Password" v-model="form.password" />
                <br>
                <input class="input_auth_submit" type="submit" value="Login" />   
            </form>
        </div>
    </div>
</template>

<style>
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Fira sans', sans-serif;
    font-size: 16px;
}
    .login{
        background: #6c5ce7;
        padding: 0;
        margin: 0;
        width: 100%;
        height: 100vh;
        overflow: hidden;
        
    }
    .formLogin{
        display: flex;
        align-items: center;
        width: 21.8em;
        height: 45em;
        margin: 0 auto 0 auto;
       
    }
    .input_auth{
        background: rgba(228, 232,243, 0.8);
        background-position: 0.5em 0.6em;
        align-items: center;
        border: none;
        color: rgba(80, 80 , 80, 1);
        padding: 0 0 0 4rem;
        margin: 0 0 1em 0;
        width: 20em;
        height: 2.8em;
        outline: none;
        transition: background-color 0.4s;
    }
    .input_auth:hover{
        background-color: rgba(255, 255 , 255 , 255);
    }
    .input_auth:focus{
        background-color: rgba(255, 255 , 255 , 255);
    }
    .input_auth_submit{
        
        width: 10em;
        height: 2.5em;
    }

    .input_auth_submit:hover{
        background: #43467f;
        color: #ffffff;
    }
    .input_auth_submit:focus{
        background: #43467f;
        color: #ffffff;
    }
    .text-danger{
        color:red;
    }

</style>