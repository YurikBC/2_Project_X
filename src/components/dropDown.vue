<template>
    <div>
        <div class="showButtonFlex">
<<<<<<< HEAD
            <button id="showProfileButton" @click="showProfile">Профиль</button>
=======
            <button id="showProfileButton" @click="showProfile">Profile</button>
>>>>>>> 320cc0e4a3ea572bd0d901176b2f7dc90ba6aa51
        </div>
        <div></div>
        <div class="profileBox">
            <transition name="fade">
                <div class="profileFlex" v-if="show">
<<<<<<< HEAD
                    <router-link to="/settings"><button>Настройки</button>
                    </router-link>
                    <router-link to="/favoriteVacancies"><button>Вакансии</button></router-link>
                    <router-link to="/" @click="logOut"><button>Выйти</button></router-link>
=======
                    <router-link to="/settings"><button>Settings</button></router-link>
                    <router-link to="/favoriteVacancies"><button>Vacancies</button></router-link>
                    <router-link to="/" @click="logOut"><button>Log out</button></router-link>
>>>>>>> 320cc0e4a3ea572bd0d901176b2f7dc90ba6aa51
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
        background-color: #ef7f35;
        padding: .5em 1.3em;
        border: none;
        border-radius: 5px;
        color: snow;
<<<<<<< HEAD
        position: relative;
=======
>>>>>>> 320cc0e4a3ea572bd0d901176b2f7dc90ba6aa51
        
        
        
    }


    .profileFlex {
        display: flex;
        flex-direction: column;
        position: absolute;
<<<<<<< HEAD
        margin-top: 10px;
        box-shadow:  0 1px 10px 0 #6389b9;
        z-index: 1;
        width: 200px;
        background-color: white;
        border-radius: 5px;
        
    }
    .profileFlex button {
        background-color: #039BE5;
        color: white;
        border: none;
        width: 100%;
        margin-bottom: 1px;
        padding: 10px 5px;
        
=======
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
>>>>>>> 320cc0e4a3ea572bd0d901176b2f7dc90ba6aa51
    }
    .profileFlex button:hover { background: rgb(127, 207, 255); }
    .profileFlex button:active { background: rgb(94, 126, 152); }

    .fade-enter-active, .fade-leave-active {
        transition: opacity .5s
    }
    .fade-enter, .fade-leave-to {
        opacity: 0
    }
<<<<<<< HEAD
    

    
=======
>>>>>>> 320cc0e4a3ea572bd0d901176b2f7dc90ba6aa51
</style>