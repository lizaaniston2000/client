<template>
<div>
    <!--<div id="app">
        <router-view>-->
    <header class="header">
        <div class="navbar">
            <div class="container">
                <div class="navbar-wrap">
                    <div class="menu_burger">
                        <a href=""><i class="fas fa-bars"></i></a>
                    </div>
                    <img src="../assets/img/logo2.png">
                    <nav class="menu">
                        <ul class="menu__items">
                            <li><a href="#about_us">Про нас</a></li>
                            <li><a href="#camp_news">Новини</a></li>
                            <li><a href="#camp_team">Педагогічний склад</a></li>
                            <li><a href="#plan">Розклад дня</a></li>
                            <li><a href="#kalendar_plan">Календар зміни</a></li>
                            <li><a href="#contact">Контакти</a></li>
                        </ul>
                    </nav>
                </div>
            </div>
            <nav class="mobile_menu">
                <ul class="mobile_menu__items">
                    <li><a href="#about_us">Про нас</a></li>
                    <li><a href="#camp_news">Новини</a></li>
                    <li><a href="#camp_team">Педагогічний склад</a></li>
                    <li><a href="#plan">Розклад дня</a></li>
                    <li><a href="#kalendar_plan">Календар зміни</a></li>
                    <li><a href="#contact">Контакти</a></li>
                </ul>
            </nav>
        </div>
        <div class="hero">
            <div class="hero-wrap"> 
                <div class="hero_text">
                    <img src="../assets/img/ship.png">
                    <h1><span class="blue">Море</span><br>незабутніх вражень...</h1>
                </div>
            </div>
        </div>
    </header>
    <main>
        <section class="about_us" id="about_us">
            <article class="about_article">
                <header class="about_article-text">
                    <span class="blue pre_title">табір "Ювілейний"</span>
                    <h1 class="title">Про нас</h1>
                </header>
                <div class="container">
                    <div class="about_article-wrap">
                        <div class="group about_group">
                            <img src="../assets/img/sun.png">
                            <h1 class="group_text">Яскраве сонце</h1>
                        </div>
                        <div class="group about_group">
                            <img src="../assets/img/multi_sea.png">
                            <h1 class="group_text">Тепле море</h1>
                        </div>
                        <div class="group about_group">
                            <img src="../assets/img/friend.png">
                            <h1 class="group_text">Багато друзів</h1>
                        </div>
                        <div class="group about_group">
                            <img src="../assets/img/quest.png">
                            <h1 class="group_text">Ігри та квести</h1>
                        </div>
                        <div class="group about_group">
                            <img src="../assets/img/disko.png">
                            <h1 class="group_text">Запальні дискотеки</h1>
                        </div>
                    </div>
                </div>    
            </article>
            <article class="about_camp">
                <div class="container">
                    <div class="about_camp-wrap">
                        <img src="../assets/img/camp_leader.jpg">
                        <article>
                            <header class="camp_text">
                                <span class="blue pre_title">табір "Ювілейний"</span>
                                <h1 class="title">Про нас</h1>
                            </header>
                            <div class="words camp_words">
                                <p class="words_paragraph">
                                    <span class="blue">"Ювілейний"</span> - це велика дружня родина!<br>
                                    Ми даруємо тобі незабутні спогади, щасливу посмішку та щирі емоції.<br>
                                    Талановиті, креативні та найкращі вожаті не дадуть тобі сумувати.<br>
                                    Тож, не зволікай <br>
                                    У "Юбік" поспішай!
                                </p>
                            </div>
                        </article>
                    </div>
                </div>
            </article>
        </section>
        <section class="capm_news" id="camp_news">
            <article class="news_article">
                <header class="news_article_text">
                    <span class="blue pre_title">табір "Ювілейний"</span>
                    <h1 class="title">Новини</h1>
                </header>
                <div class="container">
                    <div class="news_article-wrap">
                        <div class="news_article-date date">
                            <div><img src="../assets/img/pirozhkov.jpg"></div>
                            <p class="date_text"><span class="blue">У "Ювілейний" завітали справжні зірки!</span><br>
                                Приголомшивими номерами від Дзідзьо, Артура Пірожкова, Світлани Лободи та інших <br>
                                був здивован кожен! <br>
                            </p>
                        </div>
                        <div class="news_article-date date" v-for="mynew in news" :key="mynew.id">
                            <div><img :src="mynew.src"></div>
                            <p class="date_text"><span class="blue">{{ mynew.news_name }}</span><br>
                                    {{ mynew.news_item }}
                                 <br>
                            </p>
                        </div>
                    </div>
                </div>
            </article>
        </section>
        <section class="camp_team" id="camp_team">
            <article class="team_list">
                <header class="team_list-text">
                    <span class="blue pre_title">табір "Ювілейний"</span>
                    <h1 class="title">Педагогічний склад</h1>
                </header>
                <div class="container">
                    <carousel class="team_list-wrap" :navigation-next-label="navigationNext" 
                    :navigation-prev-label="navigationPrev" :navigationEnabled="true" 
                    :perPage="3" :perPageCustom="[[300,1],[340,1],[480,1],[768,2],[991,3]]"  
                    paginationActiveColor="#008ed6" paginationColor="#ffffff">
                        <slide class="pedagog team_list-pedagog" v-for="teach in teachers" :key="teach.id">
                            <div class="pedagog_photo">
                                <img :src="teach.src">
                            </div>
                            <p class="pedagog_name">{{ teach.ped_name }}</p>
                            <span class="blue">{{ teach.ped_d }}</span>
                            <p class="pedagog_text">{{ teach.ped_info}}</p>
                            <hr>
                            <div class="pedagog_logo">
                                <i class="fab fa-telegram-plane"></i>
                                <i class="fab fa-facebook-f"></i>
                                <i class="fab fa-instagram"></i>
                            </div> 
                        </slide>
                    </carousel> 
                </div>
            </article>
        </section>
        <section class="plan" id="plan">
            <article class="day_plan">
                <header class="day_plan-text">
                    <span class="blue pre_title">табір "Ювілейний"</span>
                    <h1 class="title">Розклад дня</h1>
                </header>
                <div class="container">
                    <div class="day_plan-wrap">
                        <img src="../assets/img/London.png" alt="">
                        <div class="plan">
                            <p>08:00 — 08:30   <span class="blue">Підйом</span></p>
                            <p>08:30 — 08:45   <span class="blue">Зарядка</span></p>
                            <p>08:45 — 09:00   <span class="blue">Планування дня у загонах</span></p>
                            <p>09:00 — 09:45   <span class="blue">Сніданок</span></p>
                            <p>10:00 — 11:30   <span class="blue">Пляж</span></p>
                            <p>11:45 — 12:45   <span class="blue">Спорт, ігри, репетиції</span></p>
                            <p>13:00 — 13:45   <span class="blue">Обід</span></p>
                            <p>14:00 — 16:00   <span class="blue">Після обідній сон</span></p>
                            <p>16:30 — 16:45   <span class="blue">Полдник</span></p>
                            <p>17:00 — 18:00   <span class="blue">Пляж</span></p>
                            <p>17:00 — 18:30   <span class="blue">Спорт,ігри, репетиції</span></p>
                            <p>19:00 — 19:45   <span class="blue">Вечеря</span></p>
                            <p>20:00 — 21:00   <span class="blue">Вечірній захід</span></p>
                            <p>21:00 — 22:30   <span class="blue">Дискотека</span></p>
                            <p>21:30 — 22:00   <span class="blue">Друга вечеря у молодших загонах</span></p>
                            <p>22:00           <span class="blue">Відбій у молодших загонах </span></p>
                            <p>22:30 — 23:00   <span class="blue">Друга вечеря у cтарших загонах</span></p>
                            <p>23:00           <span class="blue">Відбій у старших загонах</span></p>
                        </div>
                    </div>
                </div>
            </article>
        </section>
        <section class="kalendar" id="kalendar_plan">
            <article class="kalendar_plan">
                <header class="kalendar_plan-text">
                    <span class="blue pre_title">табір "Ювілейний"</span>
                    <h1 class="title">Календар зміни</h1>
                </header>
                <div class="filter_form">
                    <datepicker  id="dob" v-model="n_date"></datepicker>
                    <button class="button"  v-on:click="dateFilterKey = 'filterDate'"><span class="blue">Знайти</span></button>
                    <button class="button" v-on:click="dateFilterKey = 'all'"><span class="blue">Скасувати</span></button>
                </div>
                <div class="container">
                    <div class="kalendar_plan-wrap">
                        <div class="event kalendar_card" v-for="myevent in mainFilter" :key="myevent.id">
                            <h1 class="event_name"><span class="blue">{{myevent.event_name}}</span></h1>
                            <img :src="myevent.src">
                            <p>{{myevent.event_date}}</p>
                        </div>
                    </div>
                </div>
            </article>
        </section>
        <section class="contact" id="contact">
            <article class="contact_us">
                <header class="contact_us-text">
                    <span class="blue pre_title">табір "Ювілейний"</span>
                    <h1 class="title">Контакти</h1>
                </header>
                <div class="container">
                    <div class="contact_us-wrap">
                        <div class="coordinate contact-coordinate">
                            <img src="../assets/img/phone_cnt.png" id="phn">
                            <p class="coordinate_text">Телефон: (093) 432-2310</p>
                        </div>
                        <div class="coordinate contact-coordinate">
                            <img src="../assets/img/Pointer.png">
                            <p class="coordinate_text">Курортна вулиця, 15<br>
                                Приморськ <br>
                                Запорізька область</p>
                        </div>
                        <div class="coordinate contact-coordinate">
                            <img src="../assets/img/Envelope.png" id="env">
                            <p class="coordinate_text">support@yourname.com</p>
                        </div>
                    </div>
                </div>
            </article>
        </section>
    </main>
    <footer class="footer">
        <div class="footer_wrap">
            <div class="description footer_description">
                <div>
                    <i class="fab fa-telegram-plane"></i>
                    <i class="fab fa-facebook-f"></i>
                    <i class="fab fa-instagram"></i> 
                </div>
                <span class="blue">
                    developed by Kosenko @2019
                </span>
            </div>
        </div>
    </footer>
        <!--</router-view>
    </div>-->
    </div>
</template>

<style>

</style>

<script>
import Vue from 'vue';
import axios from 'axios';
import Datepicker from './TouchDatePicker.vue';
import $ from 'jquery'
import { Carousel, Slide } from 'vue-carousel';


export default {
  components: {
    Datepicker,
    Carousel,
    Slide
  },
  name: "App",
  data() {
    return {
      news: [],
      event:[],
      n_date:'',
      dateFilterKey: 'all',
      teachers:[]
    };
  },
  mounted: function() {
    Vue.axios.get("https://yubi-server.herokuapp.com/api/news").then((response) => {
        this.news = response.data
    })
    Vue.axios.get("https://yubi-server.herokuapp.com/api/event").then((response) => {
        this.event = response.data
    })
    Vue.axios.get("https://yubi-server.herokuapp.com/api/teach").then((response) => {
        this.teachers = response.data
    })
   },
    computed:{
        navigationNext: function() { return `<i class="fas fa-chevron-right"></i>` },
        navigationPrev: function() { return `<i class="fas fa-chevron-left"></i>` },
        mainFilter() {
            return this[this.dateFilterKey]
        },
        all(){
            return this.event; 
        },
        filterDate() {
        var d=this.n_date;
           return this.event.filter(ev=>{
               return ev.event_date===d;
           })
       }
   }

  };
</script>