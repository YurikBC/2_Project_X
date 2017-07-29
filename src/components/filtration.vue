<template>
   <div class="filt">
   <div class="filt_title">
    <h5>Фильтрация</h5>
    </div>
    
    <div class="filt_by_city">
        <p>Город:</p>
    
<div class="bloc">
   <select type="text" name="city" class="select_by_city" size="6" v-model="city">        
        <option> Брест</option>
        <option>  Витебск</option>
        <option> Гомель</option>
        <option> Гродно</option>
        <option> Минск</option>
   </select>
</div>
    </div>
    <br>
    <hr>
    
<div class="filt_by_employment" >
    <p>Тип занятости:</p>
<div class="bloc">    

    <select type="text" name="employment" class="select_by_employment" size="6" v-model="employment">        
        <option> Полная занятость</option>
        <option> Частичная занятость</option>
        <option> Проектная работа</option>
        <option> Стажировка</option>
   </select>
    </div>
    </div>   
    <br>
    <br>
     <transition name="bounce">
    <button class="delete" v-if="this.city!=null || this.employment!=null"><i class="material-icons" @click="delete_select">delete</i></button>
    </transition>
    <transition name="bounce">
    <button v-if="this.city!=null || this.employment!=null" @click="query_filt">Отправить</button>
     </transition>
    </div>
    
</template>



<script>
import Vue from 'vue'
import axios from 'axios' 
    import VueAxios from 'vue-axios'
Vue.use(VueAxios, axios)
export default {
    name: 'filtration',
    data(){
        return{
            city: null,
            employment: null,
            id: null,
            
        }
    },
    methods: {
        query_filt(e){
            axios.post('https:/jsonplaceholder.typicode.com/comments',{
                city: this.city,
                employment: this.employment,
            }).then(function(response){
                 alert(JSON.stringify(response.data, null, '\t'))
            })
            .catch(function(error){
                alert(error)
            })
         e.preventDefault();  
        },
        delete_select(){
            this.city = null
            this.employment = null
        }
        
    }
}



</script>




<style scoped>

    .filt {
        background-color: #fffbf8;
        height: 500px;
        overflow: hidden;
        margin-left: 20px;
        margin-top: 10px;
        border-radius: 6px;
        width: 200px;
        vertical-align: middle;
        text-align: center;
        box-shadow: 1px 2px 4px 2px rgba(0,0,0,0.15);
        background-color: #FFFFFF;
   
       
    }
    
    .filt_title h5{
        padding: 7px;
        margin: 0px;
        font-size: 20px;
        font-weight: 300;
        color: white;
        background-color: #039BE5;
    }
    .filt_title {
        
        padding: 0px;
        margin: 0px;
        border-bottom: 2px solid #017cb7 ;
        background-color: #039BE5;
    }    
    select {
    display: inline-block;
        

 
        
    }
    .select_by_city  {
        height: 125px;
        
    }     
    select option:hover{ 
        background-color: #E55D03;
        color: white;
        border-color: #FF771E;
    }    
    select option:active{ 
        background-color: #E55D03;
        color: white;
        border-color: #FF771E;
    }
    
    
    select option:hover, 
select option:focus, 
select option:active, 
select option:checked
{
    color: white !important;
    background: linear-gradient(#039BE5,#039BE5);
    background-color: #039BE5 !important;
}
    
    .select_by_employment{
        height: 100px;
        
    }
     p {
          font-size: 17px;
        color: black;
        border-radius: 5px;
         padding: 0px;
         margin: 10px;
         font-weight: 400;
         
        
         
    }
    
    option{
        padding-left: 5px;
        
    }    
    option{
    
    padding: 2px 0px;
        
    }    
    
    option:hover{
    
    
        
    }
    
    
    .filt_by_employment p {
        font-size: 17px;
        color: black;


    }

     .bloc { 
         display:inline-block;
         overflow:hidden; 

    }

     .bloc select { 
         margin-right: 20px;
         padding-right: 50px; 
         margin:-5px 40px -5px -3px; 
         width: 300px;
         font-size: 16px;
         color: #039BE5;
         
        
         
         
    
    }
    option{
        background-color: white;
        margin-bottom: 2px;
        width: 90%;
        color: black;
        font-weight: 300;
        border-bottom: 4px solid #d7dde0;
    }
    p {
        color: black;
        
    }
    
    button {
        background-color: #039BE5;
        border: none;
        font-size: 18px;
        font-weight: 300;
        border-radius: 10px;
        padding: 6px 15px;
        color: white;
        box-shadow: inset 0px 0px 1px 1px rgba(0,0,0,0.1);
        vertical-align: bottom;
        float: left;
        margin-left: 10px;
    }
    
    .delete{
    padding: 0px;
        
        background-color: #ff771e;
        float: left;
        margin-left: 5px;
        
        }
        
    .delete>i{
    padding: 3px 3px 5px 3px;
        vertical-align: bottom;
        
        
        }
    
        @keyframes bounce {
      0% {
        transform: scale(0);
      }
      80% {
        transform: scale(1.1);
      }
      100% {
        transform: scale(1);
      }
    }
    .bounce-enter-active{
      animation: bounce .5s;
    }
    .bounce-leave-active {
      animation: bounce .5s reverse;
    }
    
    
    internal-list-box {
    
    }
</style>