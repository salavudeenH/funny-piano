<template>
  <div id="app" class="pt-mono" >
  <v-header></v-header>
  </div>
</template>

<script>
import VHeader from '@/components/VHeader'
export default {
  components: {
    VHeader,
    
  }
}
</script>
<style>
#app{
content: '';
        display: block;
        height: 100%;
        width: 100%;
          background: linear-gradient(135deg, #FF9D6C 0%, #BB4E75 100%); 
position: absolute;
        top: 0;
        left: 0;
        z-index: -1;
    
  }
.pt-mono{
  font-family: 'PT Mono', monospace;
}
</style>

