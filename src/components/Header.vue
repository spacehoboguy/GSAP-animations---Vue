<script setup>
import gsap from 'gsap'
import { onMounted } from 'vue';
onMounted(() => {
    gsap.to('.title', {
        '--myEDPT': 100,
        duration: 2.5,
        ease: 'elastic',
    })
    gsap.to('.title', {
        '--myEHLT': 1,
        duration: 2,
        ease: 'elastic'
    })
})

function breatheAnimation() {
    gsap.to('.title', {
        '--myEDPT': 180,
        '--myEHLT': 10,
        duration: 1,
        ease: 'ease2.out'
    })
}
function breatheAnimationRevert() {
    gsap.to('.title', {
        '--myEDPT': 100,
        '--myEHLT': 0,
        duration: 1.5,
        ease: 'elastic'
    })
}
</script>

<template>
    <nav class="header">
        <h1 class="title" @mouseover="breatheAnimation()" @mouseleave="breatheAnimationRevert()">Rubikon Text
        </h1>
        <!-- <h2 class="marquee">Generate creativity with the support of Rubikon. Explore. Try. Try again. </h2> -->
    </nav>
</template>