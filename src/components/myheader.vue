<template>
           <header>
            <div class="header">
                <ul>
                   
                   <li>
                      <router-link to="/">
                       <img src="/src/img/exposit3.png" alt="">
                       </router-link>
                   </li>
                    <li>
                        <router-link to="/">
                            <p>Главная</p>
                        </router-link>
                    </li>
                    <li>
                        <router-link to="/contacts">
                            <p>Контакты</p>
                        </router-link>
                    </li>                 
                <div class="right_container">
<<<<<<< HEAD
                   
                                         <li >
                       <div class="dropdown">
       
                           <p><dropDown></dropDown></p>
               
                       </div>
                    </li>
                             <li>
                       <router-link to="/singIn">
                          <div class="reg">
                               <p>Войти</p>
                           </div>
                        </router-link>
                    </li>  
=======
>>>>>>> 320cc0e4a3ea572bd0d901176b2f7dc90ba6aa51
                    <li>
                       <router-link to="/registration">
                          <div class="reg">
                               <p >Регистрация</p>
                           </div>
                        </router-link>
                    </li>  
<<<<<<< HEAD
                      <div id="parallelogram"></div>                     

=======
                                          
                      <li >
                       <div class="dropdown">
       
                           <p><dropDown></dropDown></p>
               
                       </div>
                    </li>
>>>>>>> 320cc0e4a3ea572bd0d901176b2f7dc90ba6aa51
                </div>    
                </ul>
            </div>



        </header>
</template>




<script>
import dropDown from './dropDown.vue'
export default {
    name: 'myheader',
    data(){
            return{
                show: false
            };
        },
    components: { 
        dropDown
    }
}



</script>

<style scoped>
header {
    background-color: #039BE5 !important;
    font-size: 20px;
    font-weight: 300;
    padding-left: 15px;
    margin-top: 0px;
    min-height: 80px;
<<<<<<< HEAD
    
=======
>>>>>>> 320cc0e4a3ea572bd0d901176b2f7dc90ba6aa51

    
}

header p{
    color: white;
}

header li {
    display: inline-block;
    margin-left: 15px;
}

header ul {
    padding: 0px;
    margin: 0px;
}
    
    .reg > p {
        font-size: 20px;
<<<<<<< HEAD
        background-color: #EF7F35;
=======
        background-color: #ef7f35;
>>>>>>> 320cc0e4a3ea572bd0d901176b2f7dc90ba6aa51
        padding: .5em 1.3em;
        border-radius: 5px;
       

    }
    
<<<<<<< HEAD
=======
    .dropdown {
       
        
    }
>>>>>>> 320cc0e4a3ea572bd0d901176b2f7dc90ba6aa51
    
    .right_container{
        display: inline-block;
        float: right;
        margin-right: 20px;
       
        
    }
    
    img {
        height: 50px;
        margin-right: 30px;
    }

<<<<<<< HEAD
        a:hover {
        text-decoration: none !important;
        
    }
    

        
    
=======
>>>>>>> 320cc0e4a3ea572bd0d901176b2f7dc90ba6aa51

</style>