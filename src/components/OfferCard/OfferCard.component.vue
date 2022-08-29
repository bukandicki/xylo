<script setup>
import { onMounted } from "vue"

import "./OfferCard.modules.sass"

const props = defineProps({
    legend: String,
    title: String,
    desc: String,
    cta: Object,
    images: Array
});

onMounted(() => {
    const items = document.getElementsByClassName("OfferCard__image-item")
    let scrollPosition = 0

    for (const [index, value] of props.images.entries()) {
        if (items[index].childElementCount < 2) {
            const imageEl = document.createElement("img")
            imageEl.setAttribute("class", "OfferCard__image")
            imageEl.setAttribute("src", value)

            items[index].appendChild(imageEl)
        }
    }

    const updatePosition = (index, scroll) => {
        scroll = document.documentElement.scrollTop || window.pageYOffset

        if (scroll > scrollPosition) items[index].style.transform = `translateY(${(scroll - scroll) - 15}px)`
        else items[index].style.transform = `translateY(${-(scroll - scroll) + 15}px)`

        scrollPosition = scroll
    }

    document.addEventListener("scroll", () => {
        updatePosition(1)
        updatePosition(4)
    })
});

</script>

<template lang="pug">
.OfferCard
    span.OfferCard__legend {{ props.legend }}
    h1.OfferCard__title {{ props.title }}
    p.OfferCard__desc {{ props.desc }}
    a.OfferCard__cta(:href="cta.to") {{ cta.title }}

    .OfferCard__images-container
        .OfferCard__image-item
        .OfferCard__image-item
        .OfferCard__image-item
</template>
