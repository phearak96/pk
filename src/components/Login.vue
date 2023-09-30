<script setup>
</script>
<template>
<div class="container bg-warning position-relative">
<div class="col-6 position-absolute top-0 start-50 translate-middle-x">
<div class="a-section a-spacing-medium a-text-center">
</div>
<img class="position-relative top-50 start-50 translate-middle mt-4" src="../assets/logo.png" style="width:100px" alt="">
    <div class="rounded border">
        <div class="p-5">
            <form action="">
            <div class="mb-3 "> 
                <div class="fs-2">Sign in</div>
                <label for="exampleInputEmail1" class="a-form-label">Email or mobile phone number</label>
                <input type="text" required v-model="email" class="form-control border-info" id="" aria-describedby="">
                <div id="emailHelp" class="form-text">We'll never share your email with anyone else.</div>
                <label for="exampleInputPassword" class="a-form-label">Enter your password</label>
                <input type="password" required v-model="password" class="form-control border-info" id="" aria-describedby="">
            </div>
            <div class="mb-3 ">
                <input type="submit" @click="login" class="btn btn-warning form-control" value="Sign In">
            </div>
            </form>
            <p class="form-text">By continuing, you agree to Amazon's Conditions of Use and Privacy Notice.</p>
            <hr>
            <p>Don't have account ? <a href="/signup">sign up here</a></p>
            <p>Shop on Amazon Business</p>
        </div>
    </div>
</div>
</div>
</template>
<script>
import axios from 'axios';
export default {
    data(){
        return {
            email:'',
            password:''
        }
    },
    methods:{
         login() {
            // let user;
            // axios.get('http://localhost:3000/user?emailorphone='+this.emailorphone,)
            // .then((response) => {
            //     user = response.data[0]
            //     localStorage.setItem("user_info",JSON.stringify(user));
            //     if(user){
            //         this.$router.push({name:'home'});
            //     }
            // });
            // console.log(
            //     "phone_or_email =",this.email,
            //     "password =",this.password);

        axios.post('http://127.0.0.1:8000/api/auth/login',{
            email:this.email,
            password:this.password
        }).then(response=>console.log(response));
            // this.$router.push({name:'login'}); 
        }
    
    //     ,
    // mounted(){
    //     let user = localStorage.getItem('user_info');
    //     if(user){
    //         this.$router.push({name:'/'});
    //     }
   }
}
</script>