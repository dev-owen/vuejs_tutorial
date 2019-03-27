<template> <!-- div 두개 넣으면 에러 남 -->
    <div class="navbar">
        <div class="navbar-logo">
            Honeybee
        </div>
        <div class="navbar-button" :class="{ open: isOpen }">
            <navbarButton v-bind:linkTo="'https://www.google.co.kr'" v-bind:buttonText="'FrontEnd'"></navbarButton>
            <navbarButton v-bind:linkTo="'https://www.naver.com'" v-bind:buttonText="'BackEnd'"></navbarButton>
            <navbarButton v-bind:buttonText="'DeepLearning'"></navbarButton>
            <navbarButton v-bind:buttonText="'Android'"></navbarButton>
        </div>
        <div class="navbar-hamburger" @click="toggle()">
            <span id="hambg">
                <div class="wrap" :class="{ open: isOpen }">
                    <div class="item"></div>
                    <div class="item"></div>
                    <div class="item"></div>
                </div>
            </span>
        </div>
    </div>
</template>

<script>
    import navbarButton from './navbarButton.vue';
    export default {
        name: 'navbar',
        data: function () {
            return {
                isOpen: false
            };
        },
        methods: {
            toggle() {
                this.isOpen = !this.isOpen;
            }
        },
        components: {
            navbarButton
        }
    }
</script>

<style scoped>
    .navbar{
        box-shadow: 0 0 2px 0 rgba(0,0,0,0.15);
        background-color: #ffffff;
        height: 80px;
        display: flex;
        justify-content: space-between;
   }

   .navbar-logo,
   .navbar-button,
   .navbar-hamburger {
        display: flex;
        align-items: center;
        padding: 16px;
   }

   .navbar-logo {
        flex: 0;
        justify-content: flex-start;
   }

   .navbar-button,
   .navbar-hamburger {
        flex: 1;
        justify-content: flex-end;
   }
   
   .navbar-hamburger {
       display: none;
   }

   .navbar-button button {
        padding: 18px;
        border: none;
        background-color: #fff;
   }

   .navbar-button button:hover {
       background-color: lightgray;
   }

    .wrap {
        display: none;
        flex-direction: column;
        justify-content: space-between;
        width: 2em;
        height: 1.6em;
        transition: all 0.5s;
    }

    .wrap.open {
        transform: rotate(45deg);
    }

    .wrap.open .item {
        background-color: blue;
        transition: all 0.5s;
    }

    .wrap.open .item:nth-of-type(3) {
        opacity: 0;
    }

    .wrap.open .item:nth-of-type(1) {
        transform: rotate(90deg) translateX(35%);

    }

    .item {
        width: 100%;
        height: 0.2em;
        background-color: #000;
    }


    @media (max-width: 480px){
        .navbar-button {
            position: fixed;
            top: 80px;
            left: 0;
            bottom: 0;
            padding: 0;
            width: 100%;
            flex-direction: column;
            align-items: flex-start;
            justify-content: initial;
            transform: translateY(-100vh);
            transition: transform .7s ease-in-out;
        }

        .navbar-hamburger {
            display: block;
            flex: 0;
            padding: 30px;
        }

        .navbar-button.open {
            transform: translateY(0);
        }

        .navbar-button.open button {
            display: flex;
            width: 100%;
            background-color: #fff;
        }

        .navbar-button>button{

        }

        #hambg {
            float: right;
        }

        .wrap {
            display: flex;
        }
    }
</style>