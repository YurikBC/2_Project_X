<template>
    <div>
    <div class="post">
        <div class="vacancy_name">
            <h4>{{posts.name}}</h4>
            <div class='date'>{{dateNew}}</div>
            
        </div>
            
        
        <div class="footer_info">
           <div class="company_name">
               <span>
               <i class="material-icons">work</i>Компания:
               <p>{{posts.name}}</p>
               </span>
               
                <div id="parallelogram"></div>
            </div>
    
            <div class="location">
                <span>
                    <i class="material-icons">location_on</i>Город:
                    <p>Минск</p>
                </span>
            </div>
            
                <div id="parallelogram_two"></div>
    
            <div class="mail">
                <span>
                    <i class="material-icons">query_builder</i>Тип занятости: <p>Полная занятость, полный день</p>
                </span>
            </div>
    
            <div class="img">
                <div class="img_wrapper">
                    <img src="http://bellagambaam.weebly.com/uploads/7/2/5/0/72504765/1424977_orig.jpg">   
                </div>
            </div>
        </div>

    
    <div class="discription">

      <div class="link" @click="link"><span><i class="material-icons">link</i>Ссылка на оригинал</span></div>
      
      
           <div class="b-vacancy-desc-wrapper" itemprop="description"><p>Компания <strong>ActiveCloud </strong>в связи с расширением команды ищет<strong> QA Engineer (Junior)</strong> для работы над собственными продуктами компании.</p> <p> </p> <p><strong>В нашей команде Вам предстоит:</strong></p> <ul> <li>Осуществлять процесс тестирования продуктов компании (облачной платформы ActivePlatform и панели управления инфраструктурой серверов Active IaaS Panel 2.0);</li> <li>Тестировать интеграции новых услуг в платформу и внедрение платформы на стороне заказчика;</li> <li>Взаимодействовать с проектной командой;</li> <li>Составлять отчеты о результатах тестирования.</li> </ul> <p> </p> <p><strong>Используем следующий стек технологий:</strong></p> <ul> <li>Languages - Ruby, JS;</li> <li>Database - PostgreSQL, Redis;</li> <li>Frameworks - Ruby on Rails, AngularJS;</li> <li>Automation testing - RSpec, Selenium Webdriver, Capybara;</li> <li>Others - XPath, html/css, jenkins ci, bash/shell, git, page object pattern, elastic search.</li> </ul> <p> </p> <p><strong>Ждем от Вас:</strong></p> <ul> <li>Опыта функционального тестирования, тестирования web-сервисов <strong>от 0,5 года</strong>;</li> <li>Понимания общих принципов разработки ПО, знание основных методик тестирования, web-технологий (HTML, CSS, JS);</li> <li>Способности выполнять анализ требований проектной документации на предмет лаконичности, полноты и однозначности;</li> <li>Владения английским языком на уровне Pre-Intermediate+;</li> <li>Активности, инициативности и самостоятельности в принятии решений.</li> </ul> <p> </p> <p><strong>Вас ждут:</strong></p> <ul> <li>Интересные и амбициозные задачи, которые несомненно повысят Ваш профессиональный уровень;</li> <li>\"Белая\" оплата труда со 100%-тным перечислением на банковскую карту;</li> <li>Регулярные корпоративные и командообразующие мероприятия;</li> <li>Уютный офис с оборудованной кухней.</li> </ul> <p> </p> <p><strong><em>Будем рады видеть Вас в нашей команде! Присоединяйтесь!</em></strong></p> <p> </p></div> 
        </div>
     </div>
   </div>

</template>


<script>
    export default {
       
        data() {
            return {
                
                
            }
        },
        computed: {
            linkTo(){
                return this.$store.state.link
            },

            posts() {
                var x = (this.$route.params.id - 1)
                var a = Math.floor((x / 10) + 1)
                this.page = a
                this.posts = this.$store.state.posts[x]
                return this.$store.state.posts[x]
            },

            totalPage: function() {
                return this.$store.state.totalPage
            },
            currentPage() {
                return this.$store.state.currentPage
            },
            dateNew() {
                return this.$store.state.dateNew
            }


        },

        methods: {
            link: function() {
               this.$store.dispatch('link')
            }


        },
        created: function() {
            this.$store.dispatch('allPosts', this.page)
            this.$store.dispatch('date')

        }

    }

</script>




<style scoped>
    .post {
        background-color: #f2f9fe;
        max-width: 800px;
        margin: auto;
        position: relative;
        height: 100%;
        overflow: hidden;
        clear: both;
        box-shadow: rgba(166, 190, 205, .2) 0px 3px 0px;
        border-left: 0px solid #039BE5;
        z-index: 1;
        display: flex;
        flex-direction: column;
        height: 100%;
    }
    
    .vacancy_name {
        width: 100%;
        border-left: 9px solid #60abcd;
        padding-left: 15px;
        text-transform: capitalize;
        position: relative;
    }
    
    .vacancy_name>h4 {
        font-size: 25px;
    }
    
    .footer_info {
        display: flex;
        border-left: 9px solid #90dafc;
        background-color: #b6e8ff;
        flex-flow: row nowrap;
        width: 100%;
        height: 68px;
        padding: 5px 0px 0px 0px;
    }
    
    .company_name {
        height: 100%;
        width: 33%;
        text-transform: capitalize;
        overflow: hidden;
        text-overflow: ellipsis;
    }
    
    .company_name i {
        margin-left: 4px;
    }
    
    .company_name p {
        padding-top: 7px;
    }
    
    .location p {
        padding-top: 7px;
    }
    
    .footer_info span {
        color: #8AB1C4;
        overflow: hidden;
        letter-spacing: -0.2px;
        font-size: 13px;
    }
    
    .footer_info i {
        color: #1B61B8;
        vertical-align: bottom;
        margin-right: 1px;
    }
    
    .footer_info p {
        color: black;
        text-align: center;
        line-height: 15px;
        padding-right: 8px;
        margin: 3px;
        letter-spacing: 0px;
        font-size: 15px;
    }
    

    
    .location {
        height: 100%;
        width: 22%;
        text-transform: capitalize;
        overflow: hidden;
        position: relative;
    }
    
    .mail {
        height: 100%;
        width: 25%;
    }
    
    .mail p {
        padding-left: 10px;
    }
    
    .img {
        height: 100%;
        width: 20%;
    }
    
    .img_wrapper {
        position: relative;
    }
    
    img {
        box-shadow: rgba(0, 0, 0, 0.4) 5px 5px 4px;
        box-shadow: inset (0, 0, 0, 0.4) 5px 5px 4px;
        position: absolute;
        top: 59px;
        bottom: 0px;
        left: 0;
        right: 0;
        margin: auto;
        min-width: 135px;
        max-width: 135px;
    }
    
    .discription {
        width: 85%;
        border-left: 9px solid #60abcd;
        line-height: 15px;
        padding: 15px 0px 15px 50px;
    }
    
    .date {
        padding-bottom: 5px;
    }    
    #parallelogram {
        margin-left: 10px;
        left: 240px;
        top: 83px;
        position: absolute;
        width: 10px;
        height: 68px;
        -webkit-transform: skew(42deg);
        -moz-transform: skew(20deg);
        -o-transform: skew(20deg);
        background: #F2F9FE;
        
    }
    
    #parallelogram_two {
        margin-left: 10px;
        left: 410px;
        top: 83px;
        position: absolute;
        width: 10px;
        height: 68px;
        -webkit-transform: skew(42deg);
        -moz-transform: skew(20deg);
        -o-transform: skew(20deg);
        background: #F2F9FE;
    }
    
    .link {
        cursor: pointer
    }
    
    .link>span {
        color: black;
        opacity: 0.4;
    }
    
    .link span i {
        vertical-align: bottom;
        margin-bottom: -4px;
        margin-right: 4px;
    }

</style>
