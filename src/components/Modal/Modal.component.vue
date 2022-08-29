<script setup>
import { ref, watch } from "vue"

import Fire from "@/images/Fire.svg"
import Clock from "@/images/Clock.svg"
import Archive from "@/images/Archive.svg"

import "./Modal.modules.sass"

const prop = defineProps({ show: Boolean })
const emit = defineEmits(["onCLose"])

const showModal = ref(false)
const query = ref("")

watch(
    () => prop.show,
    show => {
        showModal.value = show
    }
)

const handleHideModal = (e) => {
    console.log(e);
    emit("onCLose")
}

const explores = [
    {
        id: 1,
        image: Fire,
        title: "Popular"
    },
    {
        id: 2,
        image: Clock,
        title: "Recent"
    },
    {
        id: 3,
        image: Archive,
        title: "Browse All"
    }
];
</script>

<template lang="pug">
teleport(to="body")
    transition(name="modal-fade")
        .modal(v-if="showModal" role="dialog" ref="modal" aria-modal="true")
            .modal__wrapper(v-click-outside="handleHideModal")
                .modal__body
                    span.modal__title Quickly find episodes, articles, and pages across the website.
                    .modal__search-bar
                        input.modal__search-input(v-model="query" type="search" autocomplete="off" placeholder="Search..." autofocus="true" )
                        button.modal__search-button Search
                        button.modal__search-clear(
                            @click="query = ''"
                            :style="{ 'display': `${query ? 'flex' : 'none'}` }"
                        )
                .modal__footer
                    .modal__explore
                        .modal__explore-item(v-for="explore in explores" :key="explore.id")
                            .modal__explore-icon(:style="{ 'background-image': `url(${explore.image})` }")
                            span.modal__explore-title {{ explore.title }}
</template>
