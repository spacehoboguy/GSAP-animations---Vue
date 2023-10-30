<script setup>
import { onMounted, ref } from 'vue';
import gsap from 'gsap';
import { ScrollTrigger } from 'gsap/ScrollTrigger';

const myMORF = ref(0);

onMounted(() => {
    gsap.registerPlugin(ScrollTrigger);

    let tl = gsap.timeline();

    tl.to(myMORF, {
        value: 60,
        scrollTrigger: {
            trigger: '.content-box-left-1',
            start: 'top bottom',
            end: 'bottom center',
            scrub: true,
            onUpdate: () => {
                gsap.to('.subtitle-1', {
                    '--myMORF': myMORF.value,
                    yoyo: true,
                    repeat: -1
                });
            },
        },
    });

    //  gsap.to('content-box-img', {
    //      left: 600,
    //      ease:'ease.in',
    //      scrollTrigger: {
    //          trigger: '.content-box-left-1',
    //          start: 'top center',
    //          end: 'bottom center',
    //          scrub: true,
    //          onUpdate: () => {
    //              gsap.to('.content-box-img', {
    //                  left:100
    //              })
    //          }
    //      }
    //  })

    gsap.to('.content-box-img', {
        left: 100,
        ease: 'ease',
        scrollTrigger: {
            trigger: '.content-box1-container',
            start: 'top center',
            end: 'bottom bottom',
            scrub: true,
        }
    });
})
</script>

<template>
    <section class="horizontal-section-1">
        <div class="content-box-left-1">
            <h2 class="subtitle-1">Kablammo</h2>
        </div>
        <div class="content-box-right-1">
            <div class="content-box1-container">
                <img class="content-box-img" src="src\img\rhino-with-ai-generated-free-png.png" alt="Rhino image">
            </div>
        </div>
    </section>
</template>