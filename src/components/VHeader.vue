<template>
<div class="Header"> 
  <div class="title_container">
    <div class="rectangle mx-auto">
        <h1 class="pt-2">The emoji piano</h1>
    </div>
  </div>
  <div class="c-piano pt-6">
      <v-piano> </v-piano>
  </div>
</div>
</template>

<style>
.title_container{
padding-top:40px;
color: white ;
}

.rectangle{
	width:332px;
    height:60px;
    border-radius: 10px;
    background:black;
    text-align: center;
    font-size: 30px;
}
</style>

<script>
import VPiano from '@/components/VPiano'
export default {
  components: {
    VPiano
  }
}
</script>