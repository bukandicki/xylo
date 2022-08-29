<script setup>
import { A11y, Pagination, Navigation } from "swiper";
import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css"
import "swiper/css/pagination"
import "swiper/css/navigation"

import Navbar from "@/components/Navbar/Navbar.component.vue"
import Card from "@/components/Card/Card.component.vue"
import OfferCard from "@/components/OfferCard/OfferCard.component.vue"

import mainAvatar from "@/images/main-avatar.png"
import person1 from "@/images/person1.jpg"
import person2 from "@/images/person2.jpg"
import person3 from "@/images/person3.jpg"
import person4 from "@/images/person4.jpg"
import person5 from "@/images/person5.jpg"
import person6 from "@/images/person6.jpg"
import person7 from "@/images/person7.jpg"
import person8 from "@/images/person8.jpg"
import person9 from "@/images/person9.jpg"
import sample1 from "@/images/sample1.jpg"
import sample2 from "@/images/sample2.jpg"
import sample3 from "@/images/sample3.jpg"
import sample4 from "@/images/sample4.jpg"
import sample5 from "@/images/sample5.jpg"
import sample6 from "@/images/sample6.jpg"
import Billboard from "@/images/Billboard.vue"
import NyTimes from "@/images/NyTimes.vue"
import DanielLogo from "@/images/DanielLogo.vue"
import Bloomberg from "@/images/Bloomberg.vue"
import WashPost from "@/images/WashPost.vue"
import Sound from "@/images/Sound.vue"
import Espn from "@/images/Espn.vue"
import RightChevron from "@/images/RightChevron.vue"
import LeftChevron from "@/images/LeftChevron.vue"
import Fire from "@/images/Fire.svg"
import Clock from "@/images/Clock.svg"
import Archive from "@/images/Archive.svg"

const swiperModules = [A11y, Pagination, Navigation];

const episodes = [
    {
        id: 1,
        image: person1,
        title: "#127 Fount: Bringing the Performance Secrets of the U.S. Navy SEALs to Everyone | Andrew Herr, Founder & CEO",
        desc: "In Episode #127, we explore bringing performance secrets from Navy SEALs to the public. We’re joined by Andrew Herr, Fount’s Founder and CEO. We cover human performance, biotech strategy and the limitations of military power."
    },
    {
        id: 2,
        image: person2,
        title: "#128 Fount: Bringing the Performance Secrets of the U.S. Navy SEALs to Everyone | Andrew Herr, Founder & CEO",
        desc: "In Episode #128, we explore bringing performance secrets from Navy SEALs to the public. We’re joined by Andrew Herr, Fount’s Founder and CEO. We cover human performance, biotech strategy and the limitations of military power."
    },
    {
        id: 3,
        image: person3,
        title: "#129 Fount: Bringing the Performance Secrets of the U.S. Navy SEALs to Everyone | Andrew Herr, Founder & CEO",
        desc: "In Episode #129, we explore bringing performance secrets from Navy SEALs to the public. We’re joined by Andrew Herr, Fount’s Founder and CEO. We cover human performance, biotech strategy and the limitations of military power."
    },
    {
        id: 4,
        image: person3,
        title: "#130 Fount: Bringing the Performance Secrets of the U.S. Navy SEALs to Everyone | Andrew Herr, Founder & CEO",
        desc: "In Episode #130, we explore bringing performance secrets from Navy SEALs to the public. We’re joined by Andrew Herr, Fount’s Founder and CEO. We cover human performance, biotech strategy and the limitations of military power."
    },
    {
        id: 5,
        image: person1,
        title: "#131 Fount: Bringing the Performance Secrets of the U.S. Navy SEALs to Everyone | Andrew Herr, Founder & CEO",
        desc: "In Episode #131, we explore bringing performance secrets from Navy SEALs to the public. We’re joined by Andrew Herr, Fount’s Founder and CEO. We cover human performance, biotech strategy and the limitations of military power."
    },
    {
        id: 6,
        image: person2,
        title: "#132 Fount: Bringing the Performance Secrets of the U.S. Navy SEALs to Everyone | Andrew Herr, Founder & CEO",
        desc: "In Episode #132, we explore bringing performance secrets from Navy SEALs to the public. We’re joined by Andrew Herr, Fount’s Founder and CEO. We cover human performance, biotech strategy and the limitations of military power."
    },
    {
        id: 7,
        image: person1,
        title: "#133 Fount: Bringing the Performance Secrets of the U.S. Navy SEALs to Everyone | Andrew Herr, Founder & CEO",
        desc: "In Episode #133, we explore bringing performance secrets from Navy SEALs to the public. We’re joined by Andrew Herr, Fount’s Founder and CEO. We cover human performance, biotech strategy and the limitations of military power."
    },
    {
        id: 8,
        image: person3,
        title: "#134 Fount: Bringing the Performance Secrets of the U.S. Navy SEALs to Everyone | Andrew Herr, Founder & CEO",
        desc: "In Episode #134, we explore bringing performance secrets from Navy SEALs to the public. We’re joined by Andrew Herr, Fount’s Founder and CEO. We cover human performance, biotech strategy and the limitations of military power."
    },
    {
        id: 9,
        image: person2,
        title: "#135 Fount: Bringing the Performance Secrets of the U.S. Navy SEALs to Everyone | Andrew Herr, Founder & CEO",
        desc: "In Episode #135, we explore bringing performance secrets from Navy SEALs to the public. We’re joined by Andrew Herr, Fount’s Founder and CEO. We cover human performance, biotech strategy and the limitations of military power."
    }
];

const explores = [
    {
        id: 1,
        image: Fire,
        title: "trending now",
        desc: "Find the interviews and articles that are trending now."
    },
    {
        id: 2,
        image: Clock,
        title: "new release",
        desc: "Catch up on all of the latest interviews and articles."
    },
    {
        id: 3,
        image: Archive,
        title: "the archives",
        desc: "Explore the archives by browsing categories and tags."
    }
];

const offers = [
    {
        id: 1,
        legend: "listen now",
        title: "Outliers Podcast",
        desc: "Every week, I sit down with someone in the Top 1% of their field to decode what they've mastered and what they've learned along the way.",
        cta: { title: 'Explore Episodes', to: '#' },
        images: [person4, person6, person8, sample1, sample3, sample5],
    },
    {
        id: 2,
        legend: "subscribe now",
        title: "Friday 5 Email",
        desc: "Every Friday, I share five things I've been reading, using, and loving—including articles, biohacks, gadgets, and more.",
        cta: { title: 'Subscribe Now', to: '#' },
        images: [person5, person7, person9, sample2, sample4, sample6],
    }
];

const footerLinks = [
    {
        title: "Explore",
        links: [
            {
                title: "Most Popular",
                to: "#"
            },
            {
                title: "Most Recent",
                to: "#"
            },
            {
                title: "Topics & Tags",
                to: "#"
            },
            {
                title: "Friday Five",
                to: "#"
            }
        ]
    },
    {
        title: "Outliers",
        links: [
            {
                title: "Episodes",
                to: "#"
            },
            {
                title: "Subscribe Now",
                to: "#"
            },
            {
                title: "About the Show",
                to: "#"
            },
            {
                title: "Sponsors",
                to: "#"
            }
        ]
    },
    {
        title: "Articles",
        links: [
            {
                title: "Show Notes",
                to: "#"
            },
            {
                title: "Transcripts",
                to: "#"
            },
            {
                title: "Essays",
                to: "#"
            },
            {
                title: "Snippets",
                to: "#"
            }
        ]
    },
    {
        title: "More",
        links: [
            {
                title: "About Daniel",
                to: "#"
            },
            {
                title: "Business Card",
                to: "#"
            },
            {
                title: "Newsroom",
                to: "#"
            },
            {
                title: "Contact",
                to: "#"
            }
        ]
    }
];
</script>

<template lang="pug">
header
    Navbar
main
    section.hero-section
        .hero-section__wrapper
            .hero-section__left
                h1.hero-section__title Timeless insights for business and life.
                p.hero-section__subtitle Every week, I sit down with someone in the Top 1% of their field — from NYT bestselling authors to Oscar winners — to decode what they"ve mastered. Listen as I uncover the tactics, routines, and habits that will propel you to the top of your field.

                .hero-section__latest
                    .latest-card
                        img.latest-card__image(:src="person1")
                        .latest-card__detail
                            .latest-card__title latest episode
                            .latest-card__desc #127 Fount: Bringing the Performance Secrets of the U.S. Navy SEALs to Everyone | Andrew Herr, Founder & CEO
                    .latest-buttons
                        buttton.latest-buttons__button Start Here
                        buttton.latest-buttons__button Listen to the Podcast
            .hero-section__right
                img.hero-section__avatar(:src="mainAvatar")
    section.logos-section
        Billboard
        NyTimes
        Bloomberg
        WashPost
        Espn
    section.episodes-section
        Swiper(
            ref="swiper"
            :modules="swiperModules"
            :slides-per-view="1"
            :slides-per-group="1"
            :pagination="{ dynamicBullets: true, clickable: true, el: '.swiper-pagination' }"
            :space-between="30"
            :allow-touch-move="true"
            :breakpoints="{ 700: { slidesPerView: 3, slidesPerGroup: 3, allowTouchMove: false } }"
            :navigation="{ nextEl: '.swiper-button-next', prevEl: '.swiper-button-prev' }"
            loop
        )
            SwiperSlide(v-for="episode in episodes" :key="episode.id")
                .episode-card(role="button")
                    .episode-card__image-wrapper
                        .episode-card__image(:style="{ 'background-image': `url(${episode.image})`}")
                            .episode-card__legend New Episode
                            .episode-card__listen-button
                                Sound
                                span Listen Now

                    Card.episode-card__card-details
                        .episode-card__card-title {{ episode.title }}
                        .episode-card__card-desc {{ episode.desc }}
                        .episode-card__card-action
                            span Show notes
                            RightChevron

        .swiper-pagination

        .swiper-button-next
            RightChevron
        .swiper-button-prev
            LeftChevron

    section.explore-section
        Card(v-for="explore in explores" :key="explore.id")
            .explore-section__card-icon(:style="{ 'background-image': `url(${explore.image})`}")
            .explore-section__card-title {{ explore.title }}
            .explore-section__card-desc {{ explore.desc }}

    section.offer-section
        .offer-section__offer
            OfferCard(
                v-for="offer in offers"
                :key="offer.id"
                :legend="offer.legend"
                :title="offer.title"
                :desc="offer.desc"
                :cta="offer.cta"
                :images="offer.images"
            )
        .offer-section__summary
            h2.offer-section__summary-title GET THE WEEKLY SUMMARY
            p.offer-section__summary-desc Join 7,500+ including Fortune 500 CEOs, championship coaches, and bestselling authors who get my free weekly summary.
            .offer-section__summary-form
                input.offer-section__summary-input(placeholder="Enter your email...")
                button.offer-section__summary-button Try It
            .offer-section__summary-terms
                span By subscribing, you agree to our 
                a(href="#") privacy policy.
footer
    .footer__wrapper
        .footer__details
            .footer__title Daniel Scrivner is an entreprenuer and investor focused on building enduring companies and breakthrough products.
            .footer__subtitle
                span See what he’s working on now
                RightChevron
            DanielLogo.footer__logo
        .footer__links
            .footer__link(v-for="link in footerLinks" :key="link")
                .footer__link-title {{ link.title }}
                a.footer__sublink(v-for="sublink in link.links" :key="sublink" :href="sublink.to") {{ sublink.title }}

    .footer__bottom
        span Copyright © 2020 Daniel Scrivner. All rights reserved.
        .footer__bottom-links
            a.footer__bottom-link(href="#") Privacy & Terms
            a.footer__bottom-link(href="#") Disclosures
            a.footer__bottom-link(href="#") Sitemap
</template>

<style lang="sass">
*
    margin: 0
    padding: 0
    box-sizing: border-box
    transition: all ease .2s

* > ::after
    transition: all ease .2s

body
    background-color: #121212
    width: 100%

main
    background-color: #0d0d0d

.hero-section
    height: 590px
    background: #050505
    color: #fff
    font-family: "Lato", sans-serif
    padding: 0 60px
    overflow: hidden

    &__wrapper
        display: flex
        justify-content: space-between

    &__left
        padding: 70px 0
        width: 40%

    &__title
        margin-bottom: 18px
        font-weight: 900
        letter-spacing: .5px
        font-size: 32px

    &__subtitle
        margin-bottom: 18px
        font-size: 20px
        line-height: 30px
        font-weight: 500
        letter-spacing: .5px

    &__avatar
        height: 700px
        transform: translateY(-65px)

    &__latest
        display: flex
        flex-direction: column

.logos-section
    position: relative
    display: flex
    justify-content: space-between
    width: 100%
    padding: 8px 60px 6px
    border-top: 1px solid #1c1c1c
    border-bottom: 1px solid #1c1c1c
    background-color: #0d0d0d

    > svg
        fill: #8f8f8f
        transform: scale(.8)

.latest-card
    display: flex
    align-items: center
    width: 388px
    padding: 12px
    margin-bottom: 8px
    border-radius: 12px
    background-color: #141414
    border: 1px solid hsla(0,0%,100%,.06)
    transition: all ease .2s

    &:hover
        border-color: #474747
        background-color: #3d3d3d

    &__image
        width: 100px
        height: 80px
        object-fit: cover
        margin-right: 16px
        border-radius: 6px

    &__title
        font-size: 10px
        line-height: 14px
        font-weight: 800
        letter-spacing: 1.6px
        text-transform: uppercase
        color: #f90

    &__desc
        font-size: 14px
        line-height: 20px
        letter-spacing: 0.36px
        font-weight: 700

.latest-buttons
    width: 388px
    display: flex
    flex-wrap: wrap
    justify-content: space-between
    gap: 8px

    &__button
        flex: auto
        display: flex
        align-items: center
        justify-content: center
        flex-shrink: 4
        height: 44px
        padding: 0px 28px 2px
        border: 1px solid hsla(0,0%,100%,.08)
        border-radius: 6px
        background-color: hsla(0,0%,87.8%,.08)
        transition: all ease .2s

        &:hover
            border-color: #474747
            background-color: #3d3d3d

.episodes-section
    width: 84%
    margin: 0 auto
    padding: 50px 0 0
    position: relative

.episode-card
    background: #fff
    border-radius: 16px
    font-family: "Lato", sans-serif
    cursor: pointer

    &:hover
        .episode-card__card-title
            text-decoration: underline

        .episode-card__card-action
            & > svg
                margin-left: 15px

            &:after
                width: 20px

    &__image-wrapper
        position: relative

    &__image
        padding: 10px 0
        display: flex
        align-items: center
        flex-direction: column
        justify-content: space-between
        height: 24vh
        background-position: 50% 50%
        background-size: cover
        background-repeat: no-repeat
        background-attachment: scroll
        border-radius: 16px 16px 0 0

    &__card-title
        margin-bottom: 10px
        font-size: 20px
        line-height: 25px
        font-weight: 900
        letter-spacing: .24px

    &__card-desc
        line-height: 28px
        font-size: 18px
        margin-bottom: 20px

    &__card-action
        width: max-content
        color: #f90
        font-size: 20px
        font-weight: 700
        position: relative

        svg
            width: 17px
            height: 17px
            transition: all ease .2s
            stroke: #f90
            margin-left: 8px
            transform: translateY(3px)

        &:after
            content: ""
            display: block
            position: absolute
            right: 0
            width: 0px

            height: 2px
            background: #f90
            transform: translateY(-10.5px) translateX(-3.5px)


    &__legend,
    &__listen-button
        border: 1px solid rgba(0,0,0,.06)
        background-color: rgba(0,0,0,.44)
        color: #fff
        display: flex
        align-items: center
        justify-content: center
        font-weight: 900

    &__legend
        text-transform: uppercase
        font-size: 10px
        letter-spacing: 1px
        padding: 2px 8px
        border-radius: 4px

    &__listen-button
        fill: #fff
        font-weight: 700
        border-radius: 20px
        width: 126px
        height: 36px
        font-size: 14px
        letter-spacing: 1px

        & > svg
            width: 20px
            margin-right: 8px

.swiper
    border-radius: 16px

.swiper-pagination-bullet
    background-color: #c2c2c2 !important

.swiper-pagination-bullet-active
    background-color: #fff !important
    transform: unset !important

.swiper-pagination
    bottom: -30px !important

.swiper-button-prev,
.swiper-button-next
    width: 50px
    height: 50px
    border-radius: 50%
    border: 1px solid #333
    border-radius: 50%
    background-color: #212121
    transition: all ease .2s

    & > svg
        width: 15px
        height: 15px
    &:hover
        border-color: #474747
        background-color: #3d3d3d

    &::after
        display: none


.swiper-button-prev
    left: -70px
.swiper-button-next
    right: -70px


.explore-section
    width: 84%
    display: flex
    margin: 0 auto
    padding: 50px 0 50px
    position: relative
    font-family: "Lato", sans-serif

    &__card-icon
        width: 44px
        height: 44px
        border-radius: 50%
        background-size: 40%
        background-repeat: no-repeat
        background-position: 50% 50%
        background-color: #050505
        margin-bottom: 16px

    &__card-title
        font-size: 16px
        text-transform: uppercase
        text-align: center
        font-weight: 900
        margin-bottom: 10px
        letter-spacing: .4px

    &__card-desc
        width: 90%
        font-weight: 600
        font-size: 14px
        letter-spacing: .4px
        text-align: center
        line-height: 20px

    .card
        width: 100%
        background-color: #fff
        border-radius: 16px
        display: flex
        flex-direction: column
        justify-items: center
        align-items: center
        cursor: pointer

        &:not(:last-of-type)
            margin-right: 30px

        &:hover
            color: #f90

            .explore-section__card-icon
                background-color: #f90


.offer-section
    padding: 50px 0 50px
    border-top: 1px solid #1c1c1c
    display: flex
    flex-direction: column
    justify-content: center
    align-items: center

    &__offer
        display: flex
        justify-content: space-between
        padding: 0 50px

        .OfferCard
            width: 49%

    &__summary
        width: 560px
        display: flex
        flex-direction: column
        justify-content: center
        align-items: center
        color: #fff
        margin-top: 80px

        *
            font-family: 'Ubuntu Mono', monospace

    &__summary-title
        margin-bottom: 20px
        font-size: 24px
        line-height: 24px
        font-weight: 800
        text-align: center
        letter-spacing: 2px

    &__summary-desc
        margin-bottom: 30px
        font-size: 15px
        line-height: 27px
        text-align: center
        letter-spacing: 0.15px

    &__summary-form
        width: 80%
        display: flex
        margin-bottom: 30px

    &__summary-input
        display: block
        width: 100%
        padding: 20px 20px !important
        font-size: 16px
        color: #fff
        background-color: transparent
        border: 1px solid #fff
        border-radius: 8px 0 0 8px
        outline: none

    &__summary-button
        display: block
        width: 110px
        font-weight: 900
        font-size: 16px
        padding: 0 20px
        border-radius: 0 8px 8px 0
        outline: none
        border: none
        cursor: pointer

    &__summary-terms
        font-size: 12px

        *
            color: #7a7a7a

.footer
    &__wrapper
        border-top: 1px solid #171717
        border-bottom: 1px solid #171717
        background-color: #121212
        padding: 60px 60px 58px
        display: flex
        justify-content: space-between

    &__details
        font-size: 16px
        font-weight: 400
        color: #fff
        line-height: 26px
        letter-spacing: .30px
        font-family: 'Ubuntu Mono', monospace


    &__title
        width: 350px

    &__subtitle
        color: #b8b8b8
        position: relative
        width: max-content
        cursor: pointer

        svg
            width: 10px
            height: 10px
            transform: translate(5px, 1px)
            stroke-width: 1.8px
            stroke: rgba(255, 255, 255, .4)

        &:after
            content: ""
            display: block
            position: absolute
            right: 0
            width: 0px
            height: 2.8px
            background: #f90
            transform: translateY(-13px)

        &:hover
            color: #f90

            &::after
                width: 10px

            svg
                margin-left: 10px
                stroke: #f90

    &__logo
        width: 192px
        height: max-content
        margin-top: 70px
        fill: #fff
        cursor: pointer

        &:hover
            fill: #f90

    &__links
        display: flex
        width: 67%
        flex-wrap: wrap
        justify-content: space-evenly
        font-family: 'Ubuntu Mono', monospace

    &__link
        display: flex
        flex-direction: column

    &__sublink,
    &__link-title
        line-height: 20px
        font-weight: 400
        letter-spacing: .14px
        margin-bottom: 28px

    &__link-title
        font-weight: 900
        color: #fff

    &__sublink
        color: #b8b8b8
        text-decoration: none

    &__bottom
        height: 56px
        padding: 0 50px
        display: flex
        justify-content: space-between
        align-items: center

        *
            color: #525252
            font-size: 12px
            font-weight: 700
            font-family: "Lato", sans-serif

    &__bottom-link
        text-decoration: none

        &:not(:first-of-type)
            margin-left: 30px

        &:hover
            color: #fff

@media (max-width: 700px)
    .swiper-button-prev,
    .swiper-button-next
        display: none

    .hero-section
        height: unset
        padding: 0 30px
        &__wrapper
            flex-direction: column-reverse
        &__left
            width: unset
            padding: unset
            text-align: center
        &__right
            display: flex
            justify-content: center
            align-content: center
        &__avatar
            transform: translateY(-15px)
            height: 270px
        &__title
            text-align: center
            font-size: 24px
        &__subtitle
            font-size: 16px
            line-height: 20px
            font-weight: 600
    .latest-card
        align-items: center
        flex-direction: column
        width: 100%

        &__image
            margin: 0px

        &__title
            margin: 4px 0
            line-height: unset
            font-size: 11px
            font-weight: 900

    .logos-section
        display: none

    .latest-buttons
        width: unset
        margin-bottom: 30px

    .explore-section
        flex-direction: column

        .card
            &:not(:last-of-type)
                margin-right: unset
                margin-bottom: 30px

    .offer-section
        &__offer
            flex-wrap: wrap

            .OfferCard
                width: 100%
                margin-bottom: 20px

        &__summary
            width: 100%
            padding: 0 30px

    .footer
        &__wrapper
            flex-direction: column
            align-items: center

        &__details
            display: flex
            flex-direction: column
            align-items: center

        &__title
            width: 100%
            text-align: center

        &__logo
            margin-bottom: 80px

        &__link
            align-items: center
</style>