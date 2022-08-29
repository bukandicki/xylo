<script setup>
import { ref } from "vue"

import Modal from "@/components/Modal/Modal.component.vue"

import DanielLogo from "@/images/DanielLogo.vue"

import "./Navbar.modules.sass"

const links = [
    {
        id: 1,
        title: "Podcast",
        route: "#"
    },
    {
        id: 2,
        title: "Newsletter",
        route: "#"
    },
    {
        id: 3,
        title: "Topics & Tags",
        route: "#"
    },
    {
        id: 4,
        title: "More",
        route: "#",
        subMenu: [
            {
                id: 1,
                title: "About",
                route: "#",
            },
            {
                id: 2,
                title: "Newsroom",
                route: "#",
            },
            {
                id: 3,
                title: "Contact",
                route: "#"
            }
        ]
    }
]

const isShow = ref(null);
const isShowModal = ref(false);
const miniNavIsOpen = ref(false);

const handleShowDropdown = (id) => {
    isShow.value = id
};
const handleHideDropdown = (id) => {
    isShow.value = null
};
</script>

<template lang="pug">
nav.navbar
    .navbar__top
        .navbar-top
            .navbar-top__search-button(@click="isShowModal = true")
            Modal(:show="isShowModal" @onCLose="isShowModal = false")
            DanielLogo.navbar-top__logo
            button.navbar-top__subscribe-button Subscribe
            .navbar-top__hamburgers(@click="miniNavIsOpen = !miniNavIsOpen" :class="{ 'navbar-top__hamburgers--transformation': miniNavIsOpen }")
                .navbar-top__hamburger
                .navbar-top__hamburger
                .navbar-top__hamburger
    .navbar__bottom(
        :style="{ 'height': miniNavIsOpen ? '230px' : '0px', 'transform': miniNavIsOpen ? 'translateY(0px)' : 'translateY(-500px)' }"
    )
        .navbar-bottom__links
            template(v-for="link in links" :key="link.id")
                a.navbar-bottom__link(v-if="!link.subMenu" :href="link.route") {{ link.title }}
                a.navbar-bottom__link(v-else href="#" @mouseenter="handleShowDropdown(link.id)" @mouseleave="handleHideDropdown")
                    span {{ link.title }}
                    .navbar-bottom__link-dropdown(:class="{ 'navbar-bottom__link-dropdown--show': isShow === link.id }")
                        .link-dropdown__items
                            .link-dropdown__item(v-for="subMenu in link.subMenu" :key="subMenu.id") {{ subMenu.title }}

</template>
