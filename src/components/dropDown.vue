<template>
    <div>
        <div class="showButtonFlex">
            <button id="showProfileButton" @click="showProfile">Profile</button>
        </div>
        <div></div>
        <div class="profileBox">
            <transition name="fade">
                <div class="profileFlex" v-if="show">
                    <router-link to="/settings"><button>Settings</button></router-link>
                    <router-link to="/favoriteVacancies"><button>Vacancies</button></router-link>
                    <router-link to="/" @click="logOut"><button>Log out</button></router-link>
                </div>
            </transition>
        </div>
    </div>
</template>


<script>
    export default {
        name: "dropDown",
        data(){
            return {
                show: false
            }
        },
        methods: {
            logOut: function (){
                $window.localStorage.clear();
            },
            showProfile: function () {
                this.show = !this.show;
            }
        }
    }
</script>


<style>
    #showProfileButton {
        line-height: 20px;
        background-color: rgb(17, 93, 185);
        padding: .5em 1.3em;
        border: none;
        border-radius: 5px;
        color: snow;
        
        
        
    }


    .profileFlex {
        display: flex;
        flex-direction: column;
        position: absolute;
        padding: 10px 30px 10px 10px;
        margin: 10px;
        box-shadow:  0 1px 10px 0 #6389b9;
        z-index: 1;
        width: 200px;
        
    }
    .profileFlex button {
        background-color: white;
        border: none;
        width: 100%;
        margin: 10px;
        padding: 10px 0;
        border-radius: 10px;
    }
    .profileFlex button:hover { background: rgb(127, 207, 255); }
    .profileFlex button:active { background: rgb(94, 126, 152); }

    .fade-enter-active, .fade-leave-active {
        transition: opacity .5s
    }
    .fade-enter, .fade-leave-to {
        opacity: 0
    }
</style>