<script setup>
   import Base from '../layouts/base.vue' 
   import { onMounted, ref } from 'vue'


   let form = ref({
    name: '',
    photo: '',
    email: '',
    phone: '',
    address: '',
    description: '',
    tagline: '',
    cv: ''
   })
</script>

<template>
    <Base />

    <main class="main">

        <div class="main__sideNav"></div>

        <div class="main__content">
            <section class="about section" id="about">
                <div class="about_container">
                    <div class="titlebar">
                        <div class="titlebar_item">
                            <h1>About Us</h1>
                        </div>
                        <div class="titlebar_item">
                            <div class="btn btn-secondary">
                                Save Changes
                            </div>
                        </div> 
                    </div>
                    <div class="card_wrapper">
                        <div class="wrapper_left">
                            <div class="card">
                                <p>Full Name</p>
                                <input type="text" class="input" />

                                <p>Email</p>
                                <input type="email" class="input" />

                                <p>Phone</p>
                                <input type="text" class="input" />

                                <p>Address</p>
                                <input type="text" class="input" />
        
                                <p>Description</p>
                                <textarea cols="10" rows="5"  ></textarea>
                                    
                            </div>
                            <div class="card">
                                <p>Tagline</p>
                                <input type="text" class="input" />     
                            </div>
                        </div>
                        
                        <div class="wrapper_right ">
                            <div class="card">
                                <div class="avatar_profile">
                                 <img src="/assets/img/avatar.jpg" alt="" class="avatar_profile_img">
                                </div>
                                <input type="file" id="fileimg" />   
                            </div>
                            <div class="card">
                                <p>CV</p>
                                <input type="file" id="filecv" />    
                            </div>     
                        </div>
                        
                    </div>
                    <div class="titlebar">
                        <div class="titlebar_item">
                            
                        </div>
                        <div class="titlebar_item">
                            <div class="btn btn-secondary">
                                Save Changes
                            </div>
                        </div> 
                    </div>
                </div>
            </section>
        </div>
    </main>

</template>