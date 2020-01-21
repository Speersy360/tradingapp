<template>
  <div>
    <header style="display: inline-flex; width: 100%">
      
        <tabs style="min-width: 100%" v-bind:tabsToCreateProp="topTabs">  </tabs>
      
      
      <div style="position: absolute; right: 0px">
        <p>assd</p> 
      </div>
         

       
      
      
      </header>  
    
  </div>
</template>


<script>
import Tabs from './Components/Tabs.vue'
export default {
  components: {
    'tabs': Tabs
  },
  data () {
    return {
      topTabs: ['Prices','Alerts', 'Trades']
    }
  }
}
</script>
