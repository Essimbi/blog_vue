<script setup>
    // import router from '@/router' ;


    const links = [
        {
            name: "Home",
            url: "/"
        },
        {
            name: "Publier",
            url: "/publier"
        },
        {
            name: "About",
            url: "/about"
        },
    ]
</script>

<template>
    <nav class="navbar navbar-expand-lg navbar-light bg-light">

        <a class="navbar-brand container" href="#">Logo</a>

        <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav">
            <span class="navbar-toggler-icon"></span>
        </button>

        <div class="collapse navbar-collapse mr-auto" id="navbarNav">

            <ul class="navbar-nav mr-auto">
                <li class="nav-item active" v-for="(link, index) in links" v-bind:key="index">
                    <a class="nav-link"><router-link :to="link.url">{{ link.name }}</router-link> </a>
                </li>
            </ul>

        </div>

    </nav>
</template>

<style scoped>

.navbar {
  position: fixed;
  top: 0;
  width: 100%;
  z-index: 1;
}

@media (max-width: 992px) {
  .navbar {
    position: static; 
    z-index: 1;
  }
} 

</style>