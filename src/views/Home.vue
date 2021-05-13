<template>
  <div>
    <leaf
        @send="getId"
    />
    <p>{{msg}}</p>
  </div>

</template>

<script>
  import leaf from '../components/leaf'

  export default {
    name: 'Home',

    components: {
      leaf,
    },
    data(){
      return{
        msg: "",
      }
    },
    methods:{
      getId: function(value){
        this.msg=value;
        alert(value)
      }
    },
  }
</script>
