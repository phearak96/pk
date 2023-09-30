<script setup>
</script>
<template>
<div class="container position-relative">
<div class="col-6 position-absolute top-0 start-50 translate-middle-x">
<div class="a-section a-spacing-medium a-text-center">
</div>
 <img class="position-relative top-50 start-50 translate-middle mt-4" src="../assets/logo.png" style="width:100px" alt="">
    <div class="a-box rounded border">
        <form class="p-3">
            <div class="mb-3 ">
                <div class="fs-2">Create account</div>
                <label for="username" class="a-form-label fw-semibold">Your name</label>
                <input type="text"  v-model="name" placeholder="First and last name" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp">
                <label for="Email" class="a-form-label fw-semibold">Email</label>
                <input type="text"  v-model="email" class="form-control " id="exampleInputEmail1" placeholder="Email" aria-describedby="emailHelp">
                <label for="phone" class="a-form-label fw-semibold">Your phone number</label>
                <input type="text"  v-model="phone" placeholder="Phone" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp">
                <label for="password" class="a-form-label fw-semibold">Password</label>
                <input type="text" required v-model="password" 
                    placeholder="At least 6 characters" 
                    class="form-control" 
                    autocomplete="new-password" id="password">
                    
                <label for="confirm_password" class="fw-semibold a-form-label">Re-enter password</label>
                <input type="text" placeholder="Confirm password" required autocomplete="new-password" 
                    class="form-control " name="password_confirmation" id="confirm_password">
            </div>
            <div class="mb-3 ">
            <input type="submit" @click="signUp" class="btn btn-warning form-control" value="Continue">
                <!-- <button type="submit" @click="signUp" class="btn btn-warning form-control">Continue</button> -->
            </div>
            <p class="form-text">By continuing, you agree to Amazon's Conditions of Use and Privacy Notice.</p>
            <hr>
            <p>Buying for work?</p>
            <p>Shop on Amazon Business</p>
        </form>
    </div>
</div>
</div>
</template>
<script>
import axios from 'axios'
export default {
    data()
    {
        return{
            name:'',
            phone:'',
            email:'',
            password:''
        }
    },methods:{
         signUp()
        {
            console.log(
                "name =",this.name,
                "phone =",this.phone,
                "email =",this.email,
                "password =",this.password
            )
            axios.post('http://127.0.0.1:8000/api/auth/register',{
                name:this.name,
                phone:this.phone,
                email:this.email,
                password:this.password
        }).then(response=>console.log(response));
                this.$router.push({name:'login'}); 
        }
    }
}
</script>
