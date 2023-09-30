<template>
    <nav class="navbar navbar-expand-lg navbar-light bg-white py-4 fixed-top">
        <div class="container">
            <a class="navbar-brand d-flex justify-content-between align-items-center order-lg-0" href="">
                <i class="bi bi-bag-heart"></i>
                <span class="text-uppercase fw-lighter ms-2">pk-market</span>
            </a>

            <div class="order-lg-2 nav-btns">
        

                <button type="button" class="btn position-relative">
                    <i class="bi bi-cart-fill"></i>
                    <span class="position-absolute top-0 start-100 translate-middle badge bg-primary">+99</span>
                </button>
                <button type="button" class="btn position-relative">
                    <i class="bi bi-suit-heart-fill"></i>
                    <span class="position-absolute top-0 start-100 translate-middle badge bg-primary">12</span>
                </button>
                <button type="button" class="btn position-relative">
                    <i class="bi bi-search"></i>
                </button>
            </div>
            <div class="dropdown order-lg-2 nav-btns dropdown">
                <a class="btn dropdown-toggle " href="#" role="button" data-bs-toggle="dropdown" aria-expanded="false">
                    <i class="bi bi-person-circle"></i> Profile
                </a>
              
                <ul class="dropdown-menu">
                    <li>
                        <router-link to="/info" class="dropdown-item">
                            <i class="bi bi-info-circle"></i> Info
                        </router-link>
                    </li>
                    <li>
                        <router-link to="/login" class="dropdown-item">
                            <i class="bi bi-box-arrow-in-right"></i> Sign in
                        </router-link>
                    </li>
                    <li>
                        <router-link to="/" class="dropdown-item" @click="logout">
                            <i class="bi bi-box-arrow-right"></i> Sign out
                        </router-link>
                    </li>
                </ul>
              </div>


            <button class="navbar-toggler border-0" type="button" data-bs-toggle="collapse" data-bs-target="#navMenu">
                <span class="navbar-toggler-icon"></span>
            </button>

            <div class="collapse navbar-collapse order-lg-1" id="navMenu">
                <ul class="navbar-nav mx-auto text-center">
                    <li class="nav-item px-2 py-2">
                        <a class="nav-link text-uppercase text-dark" href="#header">home</a>
                    </li>
                    <li class="nav-item px-2 py-2">
                        <a class="nav-link text-uppercase text-dark" href="#collection">collection</a>
                    </li>
                    <li class="nav-item px-2 py-2">
                        <a class="nav-link text-uppercase text-dark" href="#special">specials</a>
                    </li>
                    <li class="nav-item px-2 py-2">
                        <a class="nav-link text-uppercase text-dark" href="#blogs">blogs</a>
                    </li>
                    <li class="nav-item px-2 py-2">
                        <a class="nav-link text-uppercase text-dark" href="#about">about us</a>
                    </li>
                    <li class="nav-item px-2 py-2 border-0">
                        <a class="nav-link text-uppercase text-dark" href="#popular">popular</a>
                    </li>
                </ul>
            </div>
        </div>
    </nav>
</template>
<script>  
export default {
    name:'header',
    methods:{
        logout(){
            localStorage.clear();
            this.$router.push({name:'login'});
        }
    }
}
</script>