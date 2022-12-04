<template>
    <header :class="{'scrolled-nav': scrollPosition}">
        <nav>
            <div class="branding">
                <img src="@/assets/Motor.png">
            </div>
            <ul v-show="!mobile" class="navigation"> <!--show only if the mobile device doesnt have enough space-->
                <li @click="$emit('clicked', 0)">Startseite</li>
                <li @click="$emit('clicked', 1)">Hersteller</li>
                <li @click="$emit('clicked', 2)">Kontakt</li>
                <li @click="$emit('clicked', 3)">Login</li>
            </ul>
            <div class="nav-icon">
                <i @click="toggleMobileNav" v-show="mobile" class="fas fa-bars" :class="{'icon-active': mobileNav}"></i>
            </div>
            <transition name="mobile-nav">
                <ul v-show="mobileNav" class="dropdown-nav"> <!--sets new navigation bar if mobile device doesnt has enough space-->
                    <li @click="$emit('clicked', 0)">Startseite</li>
                    <li @click="$emit('clicked', 1)">Hersteller</li>
                    <li @click="$emit('clicked', 2)">Kontakt</li>
                    <li @click="$emit('clicked', 3)">Login</li>
                </ul>
            </transition>
        </nav>
    </header>
</template>

<script>
    export default {
        name: 'MyNavigation',
        props: {
            msg: String
        },
        data() {
            return {
                scrollPosition: null,
                mobile: null,
                mobileNav: null,
                windowWidth: null
            };
        },
        created() {
            window.addEventListener("resize", this.checkScreen);
            this.checkScreen();
        },
        mounted() {
            window.addEventListener("scroll", this.updateScroll);
        },
        methods: {
            toggleMobileNav(){
                this.mobileNav = !this.mobileNav; //just negates the value
            },

            updateScroll(){
                const scrollPosition = window.scrollY;
                if (scrollPosition > 50) {
                    this.scrollNav = true;
                    return;
                }
                this.scrollNav = false;
            },

            checkScreen() {
                this.windowWidth = window.innerWidth;
                if(this.windowWidth <= 750) {
                    this.mobile = true;
                    return;
                }
                this.mobile = false;
                this.mobileNav = false;
                return;
            }
        }
    };
</script>

<style lang="scss" scoped>

header {
    background-color: rgba(30, 32, 34, 0.9);
    z-index: 99;
    width: 100%;
    position: fixed;
    transition: 0.5s ease all;
    color: #fff;
    
    nav {
        position: relative;
        display: flex;
        flex-direction: row;
        padding: 12px 0;
        transition: 0.5s ease all;
        width: 90%;
        margin: 0 auto;
        @media (min-width: 1140px) {
            max-width: 1140px;
        }

        ul,
        .link{
            font-weight: 500;
            list-style: none;
            color: #fff;
            text-decoration: none;
        }

        li {
            text-transform: uppercase;
            font-size: 14px;
            padding: 16px;
            padding-bottom: 4px;
            margin-left: 16px;
            transition: .5s ease all;
            border-bottom: 1px solid transparent;
            
            &:hover {
                cursor: pointer;
                color: #B2F9FC;
                border-color: #B2F9FC;
            }
        }

        .branding {
            display: flex;
            align-items: center;

            img {
                width: 50px;
                transition: 0.5s ease all;
            }
        }

        .navigation {
            display: flex;
            align-items: center;
            flex: 1;
            justify-content: flex-end;
        }

        .nav-icon{
           display: flex;
           position: absolute;
           top: 0;
           align-items: center;
           right: 24px;
           height: 100%; 

           i {
                cursor: pointer;
                font-size: 24px;
                transition: 0.8s ease all;
           }
        }

        .icon-active {
            transform: rotate(180deg);
        }

        .dropdown-nav {
            display: flex;
            flex-direction: column;
            position: fixed;
            width: 100%;
            max-width: 250px;
            color: #000;
            height: 100%;
            background-color: #F0F5F9;
            top: 0;
            left: 0;

            li {
                margin-left: 0;
                .link {
                    color: #000;
                }
            }
        }

        .mobile-nav-enter-active,
        .mobile-nav-leave-active {
            transition: 1s ease all;
        }

        .mobile-nav-enter-from,
        .mobile-nav-leave-to {
            transform: translateX(-250px);
        }

        .mobile-nav-enter-to {
            transform: translateX(0);
        }
    }
}

.scrolled-nav {
    background-color: #000;
    box-shadow: 0 4px 6px -1px rgba(0,0,0,0.1), 0 2px 4px -1px rgba(0,0,0,0.06);

    nav {
        padding: 8px  0;

        .branding {
            img {
                width: 40px;
                box-shadow: 0 4px 6px -1px rgba(0,0,0,0.1), 0 2px 4px -1px rgba(0,0,0,0.06);
            }
        }
    }
}

</style>