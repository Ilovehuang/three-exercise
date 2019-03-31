<template>
  <div class="hello">
      <div id="info">Description</div>
  </div> 
</template>

<script>
export default {
  name: 'Createtext',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    #info{
        position:absolute;
        top:10px;
        width: 100%;
        text-align: center;
	    z-index: 100;
	    display:block;
    }
</style>
