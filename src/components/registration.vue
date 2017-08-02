<template>
<<<<<<< HEAD
           <div class = "container registration-body">
       
        <div class="registration_cont">
          
           <br>

            <div class="try">
            <h2>Registration</h2>
            </div>
            <br>
            <table>
                    <tr>
                       <div class="try">
                        <label class="lbl"><p>NickName:</p></label></div>
                   
                    </tr>
                    <tr>
                        <div class="login">
                            <input type="text" maxlength="16" name="NickName" v-model="newUser.name" placeholder="Login" > 
                         </div>
                    </tr>
                    <tr>
                       <span class="error error_control" v-show="isErrorName">{{ userMsg  }}
                        </span>
                        <br>
                    </tr>
                    <tr>
                        <div class="try">
                            <label class="lbl"><p>Email:</p></label>
                        </div>
                    </tr>    
                    <tr>
                           <div class="email">
                               <input type="email" name="Email" v-model="newUser.email" placeholder="Email"><br>
                               <span v-show="isErrorMail" >{{ emailMsg }}</span>
                           </div>
                    </tr>
                    <br>
              
                <tr>
                    <div class="try">
                        <label class="lbl"><p>City:</p></label>
                    </div>
                </tr>
                    <tr>
=======
    <div class = "container registration-body">
        <div class="registration">
        <div class="registration_cont">
          
           <br>
            <h2>Registration</h2>
            <br>
            <table>
                <tr>
                    <td class='left_col'>
                       <div class="try">
                        <label class="lbl"><p>NickName</p></label></div>
                    </td>
                    <td >
                        <div class="login">
                            <input type="text" maxlength="16" name="NickName" v-model="newUser.name" placeholder="Login" > 
                            <br>
                                <span class="error_control" v-show="error_msg">{{ user_msg }}
                                </span>
                        </div>
                    </td>
                </tr>
                <tr>
                    <td class='left_col'>
                        <label class="lbl"><p>Email</p></label>
                    </td>
                    <td>
                           <div class="email">
                               <input type="email" name="Email" v-model="newUser.email" placeholder="Email"><br>        <span v-if="newUser.email.length > 1">
                                      {{ email_msg }}
                                   </span>
                           </div>
                    </td>
                    
                </tr>
                <tr>
                    <td class='left_col'>
                        <label class="lbl"><p>City</p></label>
                    </td>
                    <td>
>>>>>>> 320cc0e4a3ea572bd0d901176b2f7dc90ba6aa51
                        <div class="select">
                            <select name="city" v-model="newUser.city">
                                <option value="" disabled selected hidden>Select city</option>
                                <option>Брест</option>
                                <option>Витебск</option>
                                <option>Гомель</option>
                                <option>Гродно</option>
                                <option>Минск</option>
                            </select>
<<<<<<< HEAD
                        </div>    
                </tr>
                <br>
                <tr>
                    <div class="try">
                        <label class="lbl"><p>Password:</p></label> 
                    </div>
                    <tr> 
                        <div class="password">
                            <input type="password" name="Password" v-model="newUser.password" placeholder="Password" maxlength="16" ><br> 
                        <span class="error_control" v-show="isErrorPswd">{{ passwordMsg }}</span>
                    </div>
                </tr>
                <tr>
                   <div class="try">
                       <br>
                        <label class="lbl"><p>Confirm password:</p></label> 
                    </div>
                </tr>
                    <tr>
                        <div class="password conf">
                            <input type="password" name="Password2" v-model="newUser.password2" placeholder="Repeat password" maxlength="16">
                            <br>
                            <span class="error_control" v-show="isErrorPswd">{{ passwordMsg2 }}</span>
                        </div>
                </tr>
                     
    
                <tr>
                   
                    <div class="checkbox">
                            <p>I want to receive newsletters about new vacancies
                                </p>
                        <input type="checkbox" class="chbox" id="chbox" v-model="newUser.mailing">
                        
                        
                      
                    </div>
                    
                </tr>
                <tr>
                    <div class="try">
                    <button :class="{active: disableBtn}" :disabled="disableBtn" @click.prevent="on_signup">
                        SIGN UP
                    </button> 
                        </div>
                </tr>
            </table>     
        
    </div>
    </div>

=======
                        </div>
                    </td>
                </tr>
                <tr>
                    <td class='left_col'>
                        <label class="lbl"><p>Password</p></label> 
                    </td>
                    <td>
                        <div class="password">
                            <input type="password" name="Password" v-model="newUser.password" placeholder="Password" maxlength="16" >
                        </div>
                            <br>
                        <span class="error_control" v-show="error_msg">
                            {{ password_msg }}
                        </span>
                    </td>
                </tr>
                <tr>
                   <td class='left_col'>
                        <label class="lbl"><p>Confirm password</p></label> 
                   </td>
                    <td>
                        <div class="password conf">
                            <input type="password" name="Password2" v-model="newUser.password2" placeholder="Repeat password" maxlength="16">
                            <br>
                            <span class="error_control" v-show="error_msg">
                                {{ password2_msg }}
                            </span>
                        </div>
                    </td>
                     
                </tr>
                <tr class="checkbox_tr">
                   <td>
                    <div class="checkbox">
                            <p>I want to receive newsletters about new vacancies</p>
                    </div>
                    </td>
                    <td>
                        <input type="checkbox" class = "chbox" id="chbox" v-model="newUser.mailing">
                    </td>
                </tr>
                <tr>
                    <button :class="{active: disable_btn}" :disabled="disable_btn" @click.prevent="on_signup">
                        Sign Up
                    </button>   
                </tr>
   
            </table>     
        </div>
    </div>
    </div>
    
>>>>>>> 320cc0e4a3ea572bd0d901176b2f7dc90ba6aa51
</template>

<script>
    export default {
<<<<<<< HEAD
=======
        //        components: {
        //            signup: {template: '#signup-form'}
        //        },
>>>>>>> 320cc0e4a3ea572bd0d901176b2f7dc90ba6aa51
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
<<<<<<< HEAD
                isErrorName: true,
                isErrorMail: true,
                isErrorPswd: true,
                userMsg: '',
                emailMsg: '',
                passwordMsg: '',
                passwordMsg2: '',
                disableBtn: true,
=======
                error_msg: true,
                user_msg: '',
                email_msg: '',
                password_msg: '',
                password2_msg: '',
                disable_btn: true,
>>>>>>> 320cc0e4a3ea572bd0d901176b2f7dc90ba6aa51
                isActive: true,
                hasError: false
            }
        },
<<<<<<< HEAD
        watch: {
            'newUser.email': function(value) {
                console.log(value);
                if(this.requiredField(value,'emailMsg')){
                    this.valid_email(value, 'emailMsg');
                }
            },
            'newUser.password': function (value) {
                console.log(value);
                if(this.requiredField(value, 'passwordMsg'))
                    if (this.check_password_length(value, 'passwordMsg', 16)) {
                        this.check_passwords_match();
                        console.log(this.disableBtn);
                    }
            },
            'newUser.password2': function (value) {
                console.log(value);
                if(this.requiredField(value, 'passwordMsg2'))
                    if (this.check_password_length(value, 'passwordMsg2', 16)) {
                        this.check_passwords_match();
                        console.log(this.disableBtn);
                        console.log(this.isErrorName);
                    }
            },
            'newUser.name': function (value) {
                this.requiredField(value,'userMsg');
            }
        },
        methods: {
            requiredField(value, msg){
                if(value !== ''){
                    this[msg] = '';
                    return true;
                }
                else{
                    this[msg]='Field is required';
                    return false;
                }
            },
=======



        watch: {
            'newUser.email': function(value) {
                console.log(value);
                this.valid_email(value, 'email_msg');
            },
            'newUser.password': function(value) {
                console.log(value);
                if (this.check_password_length(value, 'password_msg', 16)) {
                    this.check_passwords_match();
                    console.log(this.disable_btn);
                }
            },
            'newUser.password2': function(value) {
                console.log(value);
                if (this.check_password_length(value, 'password2_msg', 16)) {
                    this.check_passwords_match();
                    console.log(this.disable_btn);
                    console.log(this.error_msg);
                }

            },
        },

        methods: {
>>>>>>> 320cc0e4a3ea572bd0d901176b2f7dc90ba6aa51
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
<<<<<<< HEAD
=======

>>>>>>> 320cc0e4a3ea572bd0d901176b2f7dc90ba6aa51
            check_password_length(value, msg, total) {
                let length = value.length;
                let sum = 0;
                let display;
<<<<<<< HEAD
                sum = (total - length);
=======

                sum = (total - length);

>>>>>>> 320cc0e4a3ea572bd0d901176b2f7dc90ba6aa51
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
<<<<<<< HEAD
                //ukgjygkuyfkutfhtchkgcv
=======

>>>>>>> 320cc0e4a3ea572bd0d901176b2f7dc90ba6aa51
                if (length >= total) {
                    this[msg] = '';
                    return true;
                } else {
                    this[msg] = display;
                    return false;
                }
<<<<<<< HEAD
            },
=======

            },

>>>>>>> 320cc0e4a3ea572bd0d901176b2f7dc90ba6aa51
            check_passwords_match() {
                if (this.newUser.password.length > 15 && this.newUser.password2.length > 15) {
                    if (this.newUser.password2 !== this.newUser.password) {
                        console.log(this.newUser.password);
<<<<<<< HEAD
                        this.passwordMsg2  = 'Passwords do not match';
                        this.disableBtn = true;
                        return true;
                    } else {
                        this.password2_msg = '';
                        this.disableBtn = false;
=======
                        this.password2_msg = 'Passwords do not match';
                        this.disable_btn = true;
                        return true;
                    } else {
                        this.password2_msg = '';
                        this.disable_btn = false;
>>>>>>> 320cc0e4a3ea572bd0d901176b2f7dc90ba6aa51
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
<<<<<<< HEAD
            check_requered_fields() {
                this.disableBtn = this.newUser.name !== '' && this.newUser.email !== '' && this.newUser.city !== '' && this.newUser.password !== '' && this.newUser.password2 !== '';
            },
            on_signup(){
                if(this.newUser.name !== '' && this.newUser.email !== '' && this.newUser.city !== '' && this.newUser.password !== '' && this.newUser.password2 !== '') {
                    console.log(this.newUser.name);
                    console.log(this.newUser.email);
                    console.log(this.newUser.city);
                    console.log(this.newUser.password);
                    console.log(this.newUser.mailing);
                    axios.post('http://jsonplaceholder.typicode.com/posts', {
=======

            check_requered_fields() {
                this.disable_btn = this.newUser.name !== '' && this.newUser.email !== '' && this.newUser.city !== '' && this.newUser.password !== '' && this.newUser.password2 !== '';

            },
            on_signup() {
                console.log(this.newUser.name);
                console.log(this.newUser.email);
                console.log(this.newUser.city);
                console.log(this.newUser.password);
                console.log(this.newUser.mailing);
                axios.post('http://jsonplaceholder.typicode.com/posts', {
>>>>>>> 320cc0e4a3ea572bd0d901176b2f7dc90ba6aa51
                        name: this.newUser.name,
                        email: this.newUser.email,
                        city: this.newUser.city,
                        password: this.newUser.password,
                        mailing: this.newUser.mailing
<<<<<<< HEAD
                    }).then(function (response) {
                        console.log(response);
                    })
                        .catch(function (error) {
                            console.log(error);
                        });
                }
                else{
                    console.log('не все поля заполнены');
                }
            }
        }
    }
</script>

<style scoped>
     * {
        
        color: white;
         text-align: left;
         transition: 0.23s;
       
    }
    
    body {
                
    background-color: white;
            }
    table{
        table-layout: fixed;
        width: 54%;
        margin: auto;
        
        
=======
                    }).then(function(response) {
                        console.log(response);
                    })
                    .catch(function(error) {
                        console.log(error);
                    });

            }
        }
    }

</script>

<style scoped>
    * {
        background-color: #039BE5;
        color: white;
       
        margin: auto;
        
    }

    table{
        table-layout: fixed;
        width: 40%;
>>>>>>> 320cc0e4a3ea572bd0d901176b2f7dc90ba6aa51
    }
    p {
        color: black
    }
<<<<<<< HEAD

    .registration_cont {
        padding-top: 1px;
        background-color: #088ecc;
        background-image: url(/src/img/blue.jpg);
        background-position: center;
        background-attachment: fixed;
        padding-bottom: 40px;
        border-radius: 15px;
        
            }
    

    
    
    .container {
        width: 600px;
        height: 200px;
        margin: 30px auto;
        text-align: center;
        border-radius: 20px;
        color: red;
        background-color: #EF7F35;
        box-shadow: 1px 2px 4px 2px rgba(0,0,0,0.15);
        padding-left: 10px;
        
    }

=======
    
    tr{
        line-height: 0px;
        
        
        
    }
    
    td {
        border: 1px solid black;
        text-align: left;
        vertical-align: middle;
        
    }
    
    .container {
        background: #039BE5;
        width: 900px;
        height: 300px;
        margin: 200px auto;
        text-align: center;
        border-radius: 15px;
        color: red;
        box-shadow: 1px 2px 4px 2px rgba(0,0,0,0.15);
    }

    
    input {
        border-radius: 5px;
        width: 250px;
        margin-top: 0px;
    }
    
    
    
    select {
        width: 250px;
        text-align: center;
        border-radius: 5px;
        height: 26px;
    }
    
>>>>>>> 320cc0e4a3ea572bd0d901176b2f7dc90ba6aa51

    
    button {
        color: white;
<<<<<<< HEAD
        background-color: #EF7F35;
        width: 300px;
        border-radius: 5px;
        height: 40px;
        margin-left: 20px;
        border: none;
        box-shadow: 0px 0px 3px 2px rgba(0,0,0,0.15);
        cursor: pointer;
        text-align: center;
        
    }
    
    button:active {
        transform: rotateY(2px);
    }
    
    button:hover{
        box-shadow: 0px 0px 3px 2px rgba(0,0,0,0.5);
    }
    


        .try{
                text-align: left;
            }
    
    
    .checkbox{
        display: block;
        margin-bottom: 10px;
        width: 470px;
        padding-bottom: 10px;
        vertical-align: top;
        position: relative;
            
        
    }
    
            
            
    .try{
        margin: auto;
        max-width: 380px;
        padding-bottom: 0px;
        margin-bottom: -12px;
        font-size: 16px;
            }
            
        .login, .email, .select, .password{
              margin: auto;
        max-width: 350px;
            text-align: left;
            }   
            
            input, select {
                width: 350px;
                border: none; 
                padding-left: 5px;
                height: 35px;
                box-shadow: 1px 2px 4px 2px rgba(0,0,0,0.15);
                border-radius: 5px;
                color: black;
                background-color: #fff;
                outline: 0;
                
                
                
            }
            
           input:focus, select:focus, input:active, select:active{
                box-shadow: 0px 0px 3px 1.5px firebrick;
               
            }
            input:hover, select:hover {
                box-shadow: 0px 0px 4px 2px rgba(0,0,0,0.50);
            }
            
            .input:focus{
                border-color: inherit;
                -webkit-box-shadow: none;
                box-shadow: none;
            }
            
            select {
                width: 355px;
                display: inline-block;
                height: 35px;
                color: #D1D1D1;
                 padding-left: 2px;
                 padding-right: 2px;
                
            }
            select:checked, select:focus, select:active {
                color: black;
                 box-shadow: none;
        }
            
            .error_control {
                text-align: left;
            }
            
            .checkbox {
               max-width: 350px; 
                text-align: left;
                margin: auto;
                vertical-align: top;
                margin-top: 25px;
                
                
            }
            .checkbox input {
                width: 14px;
                vertical-align: bottom;
                margin-bottom: 15px;
                border-radius: 0;
                opacity: 1!important;
                position: absolute;
                left: 325px;
                top: 7px;
                background-color: none;
                box-shadow: none;
            
               
            }
    
         #chbox:focus, #chbox:focus, #chbox:active, #chbox:active{
                box-shadow: none;
               
            }
            
            .checkbox p {
                display: inline-block;
                padding-right: 20px;
                
            }
        
            option{
                
                color: black;
            }
            
            h2 {
                text-align: center;
                width: 350px;
            }
    p {
        color: white;
    }
    
    span {
        position: absolute;
        font-size: 12px;
        color: white;
        font-style: italic;
        opacity: 0.9;
    }
    input{
        margin-bottom: 0px;
        border: none!important; 

       
    }

    tr{
        padding-top: 12px;
    }
    br{
        display: block;
     margin: 9px 0;
        
        content: " ";
    }
=======
        background-color: indigo;
        width: 300px;
        border-radius: 5px;
        height: 35px;
    }
    
    
    select {
        display: inline-block;
    }

    td{
        width: 250px;
        border: none;
        
    }
    
    .left_col {
        width: 130px;
        border-bottom: 1px solid white;
    }
    

    .checkbox{
        display: block;
        margin-bottom: 10px;
        margin-top: 10px;
        width: 470px;
        padding-bottom: 10px;
        vertical-align: top;
            
        
    }

    

    /*попробовать стиль к валидации на ввод всех полей
    (нужна будет какая то булевская переменная которая будет смотреть за заполненностью и если все плохо поля подсвечиваются
     красным, иначе все нормас)
     вопрос может сделать при нажатии на кнопку???? или динамическое отображение)
     возможно динамическая нормализация полей??? */

>>>>>>> 320cc0e4a3ea572bd0d901176b2f7dc90ba6aa51
</style>
