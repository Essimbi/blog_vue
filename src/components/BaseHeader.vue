<script setup>

const slides = [
    {
        id: 1,
        image: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSbT2Z7E97zsKdRwDu3Y_1L7qNnMPkeS3_hrLJt2os7Z4bdyBfLmYaVNmnvBJlW1y0mZVk&usqp=CAU",
        alt: "Image 1"
    },
    {
        id: 2,
        image: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQD2vSNgI2x7YK77aJ6hpgFfQdkOaq1TrmjALVVI-yrIYI0FQn10bfsQCJ0m0bkdcyzKow&usqp=CAU',
        alt: "Image 2"
    },
    {
        id: 3,
        image: "https://citation-proverbe.org/wp-content/uploads/2017/07/citations-sur-lamour.jpg",
        alt: "Image 3"
    },

]

</script>

<template>
    <section id="header-content" class="container mb-4 mt-4">
        <div id="carouselExampleDark" class="carousel carousel-dark slide" data-bs-ride="carousel">
            <div class="carousel-indicators">
                <button type="button" data-bs-target="#carouselExampleDark" data-bs-slide-to="0" class="active"
                    aria-current="true" aria-label="Slide 1"></button>
                <button type="button" data-bs-target="#carouselExampleDark" data-bs-slide-to="1"
                    aria-label="Slide 2"></button>
                <button type="button" data-bs-target="#carouselExampleDark" data-bs-slide-to="2"
                    aria-label="Slide 3"></button>
            </div>
            <div class="carousel-inner">
                <div class="carousel-item active" data-bs-interval="10000" v-for="slide in slides" :key="slide.id">
                    <img v-bind:src="slide.image" class="d-block w-100" :alt="slide.alt">
                    <div class="carousel-caption d-none d-md-block">
                        <h5>First slide label</h5>
                        <p>Some representative placeholder content for the first slide.</p>
                    </div>
                </div>
            </div>
            <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleDark" data-bs-slide="prev">
                <span class="carousel-control-prev-icon" aria-hidden="true"></span>
                <span class="visually-hidden">Previous</span>
            </button>
            <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleDark" data-bs-slide="next">
                <span class="carousel-control-next-icon" aria-hidden="true"></span>
                <span class="visually-hidden">Next</span>
            </button>
        </div>
    </section>
</template>

<style scoped>
.carousel-item img {
    height: 60vh;
}</style>