<template>
    <div class="navigation full-width flex" :class="{'hidden-navbar': !showNavbar, colour: !transparent, scrolled: !scrolledNav}">
        <div class="container flex">
            <nuxt-link to="#home" class="logo">
                <div>
                    <img src="@/assets/images/czechcon/logo-white.svg" alt="">
                </div>
            </nuxt-link>
            <ul class="flex center links">
                <li
                    v-for="item in items" 
                    :key="item.link"
                >
                    <nuxt-link 
                        :to="{path: '/', hash:item.link}">
                        {{item.title}}
                        <div class="underline"></div>
                    </nuxt-link>
                </li>
            </ul>
            <!-- <sideBar /> -->
        </div>
    </div>
</template>

<script>
import items from '@/assets/data/navigation.js'
const OFFSET = 60
    export default {
        name: 'Navigation',
        data () {
            return {
                items: items,
                showNavbar: true,
                scrolledNav: true,
                lastScrollPosition: 0,
                scrollValue: 0,
                transparent: false
            }
        },
        mounted () {
            this.lastScrollPosition = window.pageYOffset
            window.addEventListener('scroll', this.onScroll)
            // const viewportMeta = document.createElement('meta')
            // viewportMeta.name = 'viewport'
            // viewportMeta.content = 'width=device-width, initial-scale=1'
            // document.head.appendChild(viewportMeta)
        },

        beforeDestroy () {
            window.removeEventListener('scroll', this.onScroll)
        },
        methods: {
            onScroll () {
                if (window.pageYOffset < 0) {
                    return
                }
                if (Math.abs(window.pageYOffset - this.lastScrollPosition) < OFFSET) {
                    return 
                }
                this.showNavbar = window.pageYOffset < this.lastScrollPosition
                this.scrolledNav = window.pageYOffset < this.lastScrollPosition
                this.transparent = window.pageYOffset > 400
                this.lastScrollPosition = window.pageYOffset
            },
        }
    }
</script>

<style lang="scss" scoped>

.navigation {
    position: sticky;
    height: 80px;
    z-index: 100;
    top: 0;
    margin-top: 40px;
    background-color: black;
    transition: .4s ease-in-out;
    .container {
        height: 100%;
        justify-content: space-between;
        align-items: center;
        .logo {
            img {
                height: 56px;
            }
        }
        ul {
            // height: 100%;
            padding-left: 0;
            list-style: none;
            a {
                list-style: none;
                margin: 0 24px;
                color: white;
                position: relative;
                .underline {
                    transition: .3s ease-in-out;
                    height: 4px;
                    width: 0%;
                    background-color: $main-orange;
                    position: absolute;
                    left: 0;
                    margin-top: 4px;
                    border-radius: 4px;
                }
                &:hover {
                    .underline {
                        width: 100%;
                    }
                }
            }
        }
    }
    @media only screen and (max-width: 960px) {
        display: none;
    }
}

.colour {
    background-color: transparent;
}

.navigation.hidden-navbar {
  transform: translate3d(0, -140px, 0);
}

</style>