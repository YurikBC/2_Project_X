<template>
           <header>
            <div class="header">
                <ul>
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
                      
                        <div class="header_right">              
                       <li>
                       
                       <router-link to="/registration">
                          <div class="reg">
                           <p >Регистрация</p>
                           </div>
                        </router-link>
                    </li>  
                     </div>                      
                      <li >
                       <div class="dropdown">
       
                           <p><dropDown></dropDown></p>
               
                       </div>
                    </li>
                       
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
    padding-left: 50px;
    margin-top: 0px;
    min-height: 80px;

    
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
        background-color: rgb(17, 93, 185);
        padding: .5em 1.3em;
        border-radius: 5px;
       

    }
    
    .header_right{
        display: inline-block;
        margin-left: 1000px;
        
    }


</style>