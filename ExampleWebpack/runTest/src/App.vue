
<template>
    <div class="header">
        <h1 class="headerText"> TodoList</h1>
        <nav>
            <ul>
                <li>
                    <router-link to="/home">Chars</router-link>
                </li>
                <li>
                    <router-link to="/about">Min</router-link>
                </li>
                <li>
                    <router-link to="/contacts">Lee</router-link>
                </li>
            </ul>
        </nav>
    

    <div class="container">
        <router-view></router-view>
    </div>


    </div>
</template>



<script>

import Home2 from './components/12/Home2.vue';
import About2 from './components/12/About2.vue';
import contacts from './dynamicRoute/contacts.vue';
import ContactByNo from './dynamicRoute/ContactByNo.vue'
import VueRouter from 'vue-router';

const router = new VueRouter({
    routes:[
        {path:'/',component: Home2},
        {path:'/home',component: Home2},
        {path:'/about',component: About2},
        {path:'/contacts',component: contacts},
        {path:'/contacts/:no',component: ContactByNo},
    ]
})

export default {
  name :'app',
  router    
}
</script>
<style>

    @import url("http://cdn.bootcss.com/bootstrap/3.3.5/css/bootstrap.css");

    .header{background-color:aqua; padding: 10px 0px 0px 0px}
    .headerText{padding : 0px 20px 0px 20px;}
    ul{list-style-type:none;margin: 0 ;padding: 0;overflow: hidden; background-color:purple;}
    li{float:left;}
    li a {display: block;color:yellow;text-align:center;  padding: 14px 16px; text-decoration: none;}
    li a:hover{background-color:aqua;color:black;}

</style>
