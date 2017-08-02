<template>
    <div>

        <section class="divSettings">
<<<<<<< HEAD
            <h2>Settings</h2>
            <br>
=======
            <h1>SETTINGS</h1>
>>>>>>> 320cc0e4a3ea572bd0d901176b2f7dc90ba6aa51
            <div class="boxOfInputs">
                <div class="inputs" @keyup.enter="updateUser(user)">
                    Name<div><input class="inputsInSettings" type="text" v-model="user.userName" placeholder="Name"></div>
                    Number<div><input class="inputsInSettings" type="text" v-model="user.number" placeholder="Number"></div>
                    City<div><input class="inputsInSettings" type="text" v-model="user.city" placeholder="City"></div>
                    Password<div><input class="inputsInSettings" type="password" v-model="user.password" placeholder="Password" ></div>
                </div>
                <div></div>
            </div>
            <div id="confirm">
                <button @click="updateUser(user)" id="buttonConfirm">Confirm settings</button>
            </div>
        </section>
    </div>
</template>

<script>
    import myheader from './myheader.vue'
    export default {
        name: 'settings',
        data() {
            return {
                user: {
                    userName: "",
                    number: "",
                    city: "",
                    password: "****"
                }
            }
        },
        components:{myheader},
        methods: {
            updateUser(){
                //this.$store.dispatch('UpdateUser', this.user);
            }
        }
    }
</script>

<style>
    .divSettings {
<<<<<<< HEAD
        background: white;
        height: 60vh;
        width: 400px;
        margin: auto;
        background-color: red;
        margin-top: 30px;
    }
    h2{
=======
        background: #58a3a3;
        height: 60vh;
    }
    h1{
>>>>>>> 320cc0e4a3ea572bd0d901176b2f7dc90ba6aa51
        display: flex;
        justify-content: center;
        margin: 0;
    }
    .boxOfInputs {
        display: flex;
        justify-content: space-around;
        height: 40vh;
        align-items: flex-end;
        margin: 0 100px 0 100px;
    }
<<<<<<< HEAD
    input {
        flex-direction: column;
        align-items: flex-end;
            width: 350px;
                padding-left: 5px;
                height: 35px;
                box-shadow: 1px 2px 4px 2px rgba(0,0,0,0.15);
                border-radius: 5px;
                color: black;
                background-color: #fff;
                outline: 0;
        border: none!important; 
=======
    .inputs {
        flex-direction: column;
        align-items: flex-end;
>>>>>>> 320cc0e4a3ea572bd0d901176b2f7dc90ba6aa51
    }
    .inputs input {
        width: 400px;
        border: 2px forestgreen solid;
    }
    #confirm {
        display: flex;
        justify-content: flex-end;
        margin: 30px 70vh 0 510px
    }
    #buttonConfirm {
        background-color: rgb(17, 93, 185);
        padding: .5em 1.3em;
        border: none;
        border-radius: 5px;
        color: snow;
    }
<<<<<<< HEAD

input[type="text"]:focus, input[type="password"]:focus {    
       outline: none;
                              
}

=======
    #buttonConfirm:hover { background: rgb(127, 207, 255); }
    #buttonConfirm:active { background: rgb(94, 126, 152); }
>>>>>>> 320cc0e4a3ea572bd0d901176b2f7dc90ba6aa51
</style>