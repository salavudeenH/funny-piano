<template>
    <div class="relative">
        <div class="container-gif mx-auto"> 
        <img class="mx-auto" :src="gifs">
        </div>
    <div class="container-piano pt-16">
       <div class="buttonRectangle mx-auto flex relative">
       <button class="firstWhiteButton Ckey" @click="getGifs()"><span class="note">DO</span></button>
       <button class="whiteButton Dkey" @click="getGifs()"><span class="note">RÉ</span> </button>
       <button class="whiteButton Ekey" @click="getGifs()"><span class="note">MI</span></button>
       <button class="whiteButton Fkey" @click="getGifs()"><span class="note">FA</span></button>
       <button class="whiteButton Gkey" @click="getGifs()"><span class="note">SOL</span></button>
       <button class="whiteButton Akey" @click="getGifs()"><span class="note">LA</span></button>
       <button class="lastWhiteButton Bkey" @click="getGifs()"><span class="note">SI</span></button>
     <div class="absolute flex">
     <button class="blackButton b1 C2" @click="getGifs()"></button>
     <button class="blackButton b2 D2" @click="getGifs()"></button>
     <button class="blackButton b3 F2" @click="getGifs()"></button>
     <button class="blackButton b4 G2" @click="getGifs()"></button>
     <button class="blackButton b5 A2" @click="getGifs()"></button>
    </div>
    </div> 
    </div>
    </div>
</template>

<script>
import { GiphyFetch } from "@giphy/js-fetch-api";
export default {
    data(){
        return{
        gifs:null
        };
    },
  mounted() {
    //white keys
const C = document.querySelector(".Ckey");
const D = document.querySelector(".Dkey");
const E = document.querySelector(".Ekey");
const F = document.querySelector(".Fkey");
const G = document.querySelector(".Gkey");
const A = document.querySelector(".Akey");
const B = document.querySelector(".Bkey");
//black keys
const C2 = document.querySelector(".C2");
const D2 = document.querySelector(".D2");
const F2 = document.querySelector(".F2");
const G2 = document.querySelector(".G2");
const A2 = document.querySelector(".A2");
//white keys addevent
C.addEventListener("click",this.playC)
D.addEventListener("click",this.playD)
E.addEventListener("click",this.playE)
F.addEventListener("click",this.playF)
G.addEventListener("click",this.playG)
A.addEventListener("click",this.playA)
B.addEventListener("click",this.playB)
C.addEventListener("click",this.playC)
//black keys addevent
C2.addEventListener("click",this.playC2)
D2.addEventListener("click",this.playD2)
F2.addEventListener("click",this.playF2)
G2.addEventListener("click",this.playG2)
A2.addEventListener("click",this.playA2)
//console.log(C2)
window.addEventListener(KeyboardEvent,(event)=>{
    console.log(event)
})
  },
methods: {
    // play(e){
    //     {console.log(e.target)}
    // },
    async getGifs(){
        const gf = new GiphyFetch('hoc7Xw81iwUP2iewXhekupQznVmYDlHK')
        const result = await gf.emoji({
            limit:10
        })
        const image = Math.floor(Math.random() * Math.floor(10))
        this.gifs = result.data[image].images.downsized.url

        console.log(this.gifs)
        console.log(result)
    },
    playC(){
        const audio = document.createElement('audio')
        audio.src = '/assets/sounds/C.mp3',
        audio.play()
    },
    playD(){
        const audio = document.createElement('audio')
        audio.src = '/assets/sounds/D.mp3',
        audio.play()
    },
    playE(){
        const audio = document.createElement('audio')
        audio.src = '/assets/sounds/E.mp3',
        audio.play()
    },playF(){
        const audio = document.createElement('audio')
        audio.src = '/assets/sounds/F.mp3',
        audio.play()
    },
    playG(){
        const audio = document.createElement('audio')
        audio.src = '/assets/sounds/G.mp3',
        audio.play()
    },

    playA(){
        const audio = document.createElement('audio')
        audio.src = '/assets/sounds/A.mp3',
        audio.play()
    },
    playB(){
        const audio = document.createElement('audio')
        audio.src = '/assets/sounds/B.mp3',
        audio.play()
    },
    playC2(){
        const audio = document.createElement('audio')
        audio.src = '/assets/sounds/C%23.mp3',
        audio.play()
    },
     playD2(){
        const audio = document.createElement('audio')
        audio.src = '/assets/sounds/D%23.mp3',
        audio.play()
    },
     playF2(){
        const audio = document.createElement('audio')
        audio.src = '/assets/sounds/F%23.mp3',
        audio.play()
    },
     playG2(){
        const audio = document.createElement('audio')
        audio.src = '/assets/sounds/G%23.mp3',
        audio.play()
    },
     playA2(){
        const audio = document.createElement('audio')
        audio.src = '/assets/sounds/A%23.mp3',
        audio.play()
    }
  } 
}
</script>

<style lang="postcss" scoped>
.buttonRectangle{
height: 276px;
width: 531px;
border-radius: 12px;
background: black;
border-width:12px;
border-color: black;
}

.firstWhiteButton{
background-color: white;
  height: 252px;
  width: 531px;
  border-right-width: 4px;
  border-color: black;
 border-radius: 5px 0px 0px 5px;
} 

.firstWhiteButton:hover{
    background-color: #FFD12D;
}
.firstWhiteButton:hover .note{
   color: rgba(255, 255, 255);
}
 .whiteButton{
  background-color: white;
  height: 252px;
  width: 531px;
  border-right-width: 4px;
  border-color: black;
  justify-content: space-between;
} 
.whiteButton:hover{
    background-color: #FFD12D;
}
.lastWhiteButton{
background-color: white;
  height: 252px;
  width: 531px;
  border-radius: 0px 5px 5px 0px;
}
.lastWhiteButton:hover .note{
   color: rgba(255, 255, 255);
}

.lastWhiteButton:hover{
    background-color: #FFD12D;
}

.whiteButton:hover .note{
   color: rgba(255, 255, 255);
}
.blackButton{
width:30px;
height:184px;
background: black;
border-radius: 0px 0px 5px 5px;
}
.blackButton:hover{
    background-color: #E6016F;
}


.b1{
margin-left:55px;
}
.b2{
margin-left:43px;
}   
.b3{
margin-left:116px;
} 
.b4{
margin-left:43px;
}  
.b5{
margin-left:43px;
}   

.note{
font-family: PT Mono;
font-style: normal;
font-weight: normal;
font-size: 20px;
position: absolute;
bottom: -60px;
margin-left: -10px;
color: rgba(255, 255, 255,0.4);
}

.container-gif{
width: 200px;
height: 200px;
}

@media (max-width: 640px) {
.buttonRectangle{
height: 172.87px;
width: 351.7px;
border-width:5.32px;
justify-content: space-between;
}
.whiteButton { 
width:47.82px;
height:160.87px;
border-right-width: 1px;
}
.firstWhiteButton{ 
width:47.82px;
height:160.87px;
border-right-width: 1px;
}
.lastWhiteButton{ 
width:47.82px;
height:160.87px;
}
.blackButton{
width:20.79px;
height:126.22px;
}
.b1{
margin-left:36px;
}
.b2{
margin-left:30px;
}   
.b3{
margin-left:76px;
} 
.b4{
margin-left:28px;
}  
.b5{
margin-left:28px;
}   
.note{
    display: none;
}
.container-piano{
    @apply pt-32
}
.container-gif{
    @apply pt-24
}
}

</style>