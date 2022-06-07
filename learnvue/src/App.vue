<template>
  <div id="app">
    <Input  v-model="nick"/>
  </div>
</template>

<script>
import Main from './components/Main.vue'
import Article from './components/Article.vue'
import ComponentA from './components/ComponentA.vue'
import Popup from './components/Popup.vue'
import Input from './components/Input.vue'


export default {    
  name: 'App',
  components:{
    Main,
    Article,
    ComponentA,
    Popup,
    Input,
  },
  
  data(){
    return{
      nick: '',
      showPopup: false,
      hey: 'bye',
      no:'Yes',
      isDisabled: true,  
      name:'Batman',
      html: '<i>italic</i>',
      hack: `<a href="#" onClick="alert('you have been hacked!!!')">Win A Price</a>`,
      num: 11,
      basemultiplier: 10,
      mainnames:['kyle', 'marin', 'paul', 'leander'],
      showElement: true,

      style: {
        color: 'pink',
        background: 'black',
        border: '3px solid blue'
      },

      fullNames:[
        {firstname: 'ronaldo', lastname: 'cristiano'},
        {firstname: 'ramos', lastname: 'sergio'},
        {firstname: 'benzema', lastname: 'karims'}
      ],

      football:[
        {
          player: 'Cristiano Ronaldo',
          team: ['realmadarid', 'manchester united']
        },
        {
          player: 'Neymar Jr',
          team: ['psg', 'barcelona']
        },
        {
          player: 'D Maria',
          team: ['Realmadarid', 'psg']
        }
      ],

      info:{
          name: 'ranaldo',
          goals: 747,
          team: 'manchester united'
        },
        
      count: 0,

      formvalue:{
        name: '',
        textarea: '', 
        age:'',
        country: [],
        check: false,
        skillset:[],
        yearofexp:''
      },

      firstname: 'Mike',
      lastname: 'Tyson',
      item: [
        {
          id:1,
          title: 'tv',
          price: 100,
        },
        {
          id:2,
          title: 'phone',
          price: 200,
        },
        {
          id:3,
          title: 'ipad',
          price: 300,
        },
        {
          id:4,
          title: 'laptop',
          price: 500,
        }
      ],
      volume: 0,
      uname: 'greyaxis-c1',

    }
  },

  methods :{
    add(a, b, c){
      return a + b + c
    },
    multiply(num){
      return num * this.basemultiplier
    },
    inc(num){
      this.count += num
    },
    dec(num){
      this.count -= num
    },
    submitform(){
      console.log('Form Values', this.formvalue)
    },
    changefullname(){
      this.fullname = "Michal Ross"
    },
    closepopup(name){
      this.showPopup= false
      console.log(name)
    },
  },  

  computed:{
    fullname: {
      get(){
         return `${this.firstname} ${this.lastname}`;
      },
      set(value){                                         
        const names = value.split(' ');
        this.firstname = names[0];
        this.lastname = names[1]
      }
    },
    total(){
      return this.item.reduce(function(tot , curr){
      tot = tot + curr.price;
      return tot;
      }, 0)
    },
    expitems(){
      return this.item.filter(item => item.price > 100)
    }
  },

  watch:{
    volume(newv , oldv){
      if(newv > oldv && newv === 16){
        alert('listening to high volume for too long can destroy your hearing')
      }
      if(newv < oldv && newv === 6){
        alert('voice is too low')
      }
    }
  },
  provide(){
    return{
    username: this.uname,
    }
  },
}

</script>

<style>
body{
  padding-bottom: 20vw;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialixased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  /* color: #2c3e50; */   
  color: black;
  margin-top: 60px;
}

.bye{
  margin-top: 1vw;
  color:rgb(123, 192, 120);
  font-style:italic;
  text-transform: capitalize;
}

.red{
  color:red;
  background: black; 
}
.mar{
  margin: 1vw;
  font-size: 3vw;
  margin-bottom: 5vw;
}

.h{
  padding-top: 3vw;
  font-size: 5vw;
}                                                      
</style>
