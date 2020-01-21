<template>
    
<li v-bind:class="{'is-active': isActive}"> 
    <a @click="$emit('tabClick',tabValue)"> {{tabValue}} </a>
</li>
 
</template>


<script>
export default {
  data () {
    return {
        isActive: false,
        value: 'text'
    }
  },    
  props: {
      tabValue: {
          type: String
      }
  },    
  methods: {
        activate: function(){
          isActive = true;
      },
      deActivate: function(){
          isActive = false;
      }
  },
  computed: {

  }
}
</script>