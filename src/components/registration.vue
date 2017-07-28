<template>
    <div class = "container registration-body">
        <div class="row">
            <div class="col-sm-12"><h2>Log In</h2></div>
            <div class="col-sm-3 col-xs-3"><label class="lbl">NickName</label></div>
            <div class="col-sm-9 col-xs-9"><input type="text" maxlength="16" name="NickName" v-model="newUser.name" placeholder="Login" > <br><span class="error_control" v-show="error_msg">{{ user_msg }}</span></div>
            <div class="col-sm-3 col-xs-3"><label class="lbl">Email</label></div>
            <div class="col-sm-9 col-xs-9"><input type="email" name="Email" v-model="newUser.email" placeholder="Email"><br><span v-if="newUser.email.length > 1">{{ email_msg }}</span></div>
            <div class="col-sm-3 col-xs-3"><label class="lbl">City</label></div>
            <div class="col-sm-9 col-xs-9">
                <select name="city" v-model="newUser.city">
                    <option value="" disabled selected hidden>Select city</option>
                    <option>Брест</option>
                    <option>Витебск</option>
                    <option>Гомель</option>
                    <option>Гродно</option>
                    <option>Минск</option>
                </select>
            </div>
            <div class="col-sm-3 col-xs-3"><label class="lbl">Password</label></div>
            <div class="col-sm-9 col-xs-9"><input type="password" name="Password" v-model="newUser.password" placeholder="Password" maxlength="16" ></div>
            <br><span class="error_control" v-show="error_msg">{{ password_msg }}</span>
            <div class="col-sm-3 col-xs-3"><label class="lbl" >Confirm password</label></div>
            <div class="col-sm-9 col-xs-9"><input type="password" name="Password2" v-model="newUser.password2" placeholder="Repeat password" maxlength="16">
                <br><span class="error_control" v-show="error_msg">{{ password2_msg }}</span>
            </div>
            <div class="col-sm-12"><input type="checkbox" class = "chbox" id="chbox" v-model="newUser.mailing"><label class="lblchk ">I want to receive newsletters about new vacancies</label></div>
            <div class="col-sm-12"><button :class="{active: disable_btn}" :disabled="disable_btn" @click.prevent="on_signup">Sign Up</button> </div>
        </div>
    </div>
    
</template>

<script>

    export default {
//        components: {
//            signup: {template: '#signup-form'}
//        },
        name: "registration",
        data() {
            return {
                newUser: {
                    name: '',
                    email: '',
                    city: '',
                    password: '',
                    password2: '',
                    mailing: false,
                },
                // style: {
                //     active: true,
                //     'text-danger': false
                // },
                error_msg: true,
                user_msg: '',
                email_msg: '',
                password_msg: '',
                password2_msg: '',
                disable_btn: true,
                isActive: true,
                hasError: false
            }
        },



        watch: {
            'newUser.email': function(value) {
                console.log(value);
                this.valid_email(value, 'email_msg');
            },
            'newUser.password': function (value) {
                console.log(value);
                if (this.check_password_length(value, 'password_msg', 16)) {
                    this.check_passwords_match();
                    console.log(this.disable_btn);
                }
            },
            'newUser.password2': function (value) {
                console.log(value);
                if (this.check_password_length(value, 'password2_msg', 16)) {
                    this.check_passwords_match();
                    console.log(this.disable_btn);
                    console.log(this.error_msg);
                }

            },
        },

        methods: {
            valid_email(email, msg) {
                let emailRE = /^(([^<>()[\]\\.,;:\s@\"]+(\.[^<>()[\]\\.,;:\s@\"]+)*)|(\".+\"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
                if (emailRE.test(this.newUser.email)) {
                    this[msg] = '';
                    return true;
                } else {
                    this[msg] = 'Keep typing...waiting for a valid email';
                    return false;
                }
            },

            check_password_length(value, msg, total) {
                let length = value.length;
                let sum = 0;
                let display;

                sum = (total - length);

                switch (sum) {
                    case 0:
                        display = '';
                        break;
                    case 1:
                        display = 'Keep going - just need ' + sum + ' more character.';
                        break;
                    default:
                        display = 'Keep going - just need ' + sum + ' more characters';
                }

                if (length >= total) {
                    this[msg] = '';
                    return true;
                } else {
                    this[msg] = display;
                    return false;
                }

            },

            check_passwords_match() {
                if (this.newUser.password.length > 15 && this.newUser.password2.length > 15)
                {
                    if (this.newUser.password2 !== this.newUser.password) {
                        console.log(this.newUser.password);
                        this.password2_msg = 'Passwords do not match';
                        this.disable_btn = true;
                        return true;
                    } else {
                        this.password2_msg = '';
                        this.disable_btn = false;
                        return false;
                    }
                }
            },
//            isValid(){
//                if(this.newUser.name !== '' && this.newUser.email !== '' && this.newUser.city !== '' && this.newUser.password !== '' && this.newUser.password2 !== '')
//                {
//                    this.error_msg = true;
//                    this.user_msg = 'NOO';
//                }
//                else {
//                    this.error_msg = false;
//                    this.user_msg = '';
//                }
//            },

            check_requered_fields(){
              this.disable_btn = this.newUser.name !== '' && this.newUser.email !== '' && this.newUser.city !== '' && this.newUser.password !== '' && this.newUser.password2 !== '';

            },
            on_signup(){
                console.log(this.newUser.name);
                console.log(this.newUser.email);
                console.log(this.newUser.city);
                console.log(this.newUser.password);
                console.log(this.newUser.mailing);
                axios.post('http://jsonplaceholder.typicode.com/posts', {
                    name: this.newUser.name,
                    email:this.newUser.email,
                    city: this.newUser.city,
                    password: this.newUser.password,
                    mailing: this.newUser.mailing}).then(function (response) {
                    console.log(response);
                })
                    .catch(function (error) {
                        console.log(error);
                    });

            }
        }
    }
</script>

<style scoped>
    *{
        background-color: antiquewhite;
    }
    body
    {
        
        background-color: cornflowerblue;
    }
    .registration-body
    {
        background: #FFF;
        width: 1000px;
        height: 400px;
        margin: 200px auto;
        text-align: center;
        border-radius: 10px;
    }
    input
    {
        border-radius: 5px;
        width: 250px;
        margin-top: 10px;
        /*border-color: red;*/
    }
    .row
    {
        text-align: center;
        background-position: center;
    }
    .col-sm-3
    {
        height: 46px;
        text-align: left;
    }

    .col-sm-9
    {
        height: 46px;
    }

    select
    {
        margin-top: 10px;
        width: 250px;
        text-align: center;
        border-radius: 5px;
        height: 26px;
        
    }

    label
    {
        margin-top: 13px;
        margin-left: 25px;
    }

    button{
        color: white ;
        background-color: indigo;
        width: 300px;
        border-radius: 5px;
        height: 35px;

    }
    span
    {
        color: red;
    }

    .chbox{
        height: 15px;
        margin-left:20px ;
        margin-top:15px ;
        width: 20px;
    }
    .lblchk{
        margin-top: 15px;
    }

    /*попробовать стиль к валидации на ввод всех полей
    (нужна будет какая то булевская переменная которая будет смотреть за заполненностью и если все плохо поля подсвечиваются
     красным, иначе все нормас)
     вопрос может сделать при нажатии на кнопку???? или динамическое отображение)
     возможно динамическая нормализация полей??? */


</style>