<template>
  <div id="app">
    <headers />
    <body>
   <b-tabs>
        <b-tab  v-for="(item,index) in listtabs" :key="index">
          <template v-slot:title>
            <b type="grow" small  >{{item}} </b> 
          </template>
          <Monitor v-if="index==1" /> 
        </b-tab>

   
    </b-tabs>
    </body>
  </div>
</template>

<script>
import Vue from 'vue';
import headers from './Components/Header';
import Monitor from './Components/Monitoring';
import { BootstrapVue, IconsPlugin } from 'bootstrap-vue';
import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'
Vue.use(BootstrapVue);
Vue.use(IconsPlugin)


export default {
    name:'Tab',
    
    data(){
        return{
            listtabs:[
                'Chỉ số hoạt động',
                'Tồn giám sát',
                'Chất lượng dịch vụ',
                'Quy trình công việc',
                'Top Ranking',
                'Báo Cáo'
            ] ,
            
            
        }
    },
    components:{
      headers,
      Monitor
    },
    methods:{
      
    }
}
</script>
<style src="vue-multiselect/dist/vue-multiselect.min.css"></style>
<style>

</style>
