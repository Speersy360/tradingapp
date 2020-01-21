<template>
    <span>
    <div> 
  <div class="tabs">
  <ul>
      <!--
    <tab tabValue="Prices" v-on:tabClick="changeTab($event)"> </tab>
    <tab tabValue="Alerts" v-on:tabClick="changeTab($event)"> </tab>
    <tab tabValue="Trades" v-on:tabClick="changeTab($event)"> </tab> !-->
    <li v-for= "item in tabsToCreateProp">
        <tab v-bind:tabValue="item" v-on:tabClick="changeTab($event)"> </tab>
    </li>

  </ul>
  
</div> 
  </div>

    </span>
  
</template>


<script>
import Tab from './Tab.vue'
export default {
  data () {
    return {
        tabs: [],
        tabsToCreate: ['Prices','Alerts','Trades'],    
    };
  },
  props: {
      tabsToCreateProp: []
  },
  components: {
    'tab': Tab
  },
  methods: {
      changeTab: function(name) {
          console.log(name);
          this.tabs.forEach(tab => {
              
              tab.isActive = (name == tab.tabValue)
          });
      }
  },
  created() {
      this.tabs = this.$children;
      
  },
  mounted() {
      this.changeTab('Prices');
      console.log(this.tabs);
      this.tabs.forEach(tab => {
        console.log(tab.tabValue);
      });
      console.log(this.tabsToCreateProp);
  }
}
</script>