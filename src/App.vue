<template>
  <div id="app">
   <div class="align">
    <Card>
      <template v-slot:header >
        <h1>HEADER</h1>
      </template>
      <template v-slot:default >
        <img src="https://dpi.gov.gy/wp-content/uploads/2019/06/pictures-for-profile-200x200-2.png" />
      </template>
      <template v-slot:footer >
      <button>View More</button>
      </template>
    </Card>
    <Card>  
      <template v-slot:header >
        <h1>HEADER</h1>
      </template>
      <template v-slot:default >
        <img src="https://dpi.gov.gy/wp-content/uploads/2019/06/pictures-for-profile-200x200-2.png" />
      </template>
      <template v-slot:footer >
      <button>View More</button>
      </template>
    </Card>
    <Card>
      <template v-slot:header >
        <h1>HEADER</h1>
      </template>
      <template v-slot:default >
        <img src="https://dpi.gov.gy/wp-content/uploads/2019/06/pictures-for-profile-200x200-2.png" />
      </template>
      <template v-slot:footer >
      <button>View More</button>
      </template>
    </Card>
    <Card>
      <template v-slot:header >
        <h1>HEADER</h1>
      </template>
      <template v-slot:default >
        <img src="https://dpi.gov.gy/wp-content/uploads/2019/06/pictures-for-profile-200x200-2.png" />
      </template>
      <template v-slot:footer >
      <button>View More</button>
      </template>
    </Card>
    <Card>
      <template v-slot:header >
        <h1>HEADER</h1>
      </template>
      <template v-slot:default >
        <img src="https://dpi.gov.gy/wp-content/uploads/2019/06/pictures-for-profile-200x200-2.png" />
      </template>
      <template v-slot:footer >
      <button>View More</button>
      </template>
    </Card>
    <Card>
      <template v-slot:header >
        <h1>HEADER</h1>
      </template>
      <template v-slot:default >
        <img src="https://dpi.gov.gy/wp-content/uploads/2019/06/pictures-for-profile-200x200-2.png" />
      </template>
      <template v-slot:footer >
      <button>View More</button>
      </template>
    </Card>
   </div>

   <Namelist>
    <template v-slot:default="slotprops" >
      {{slotprops.firstname}} {{slotprops.lastname}}
    </template>
   </Namelist>

   <Namelist>
    <template v-slot:default="slotprops" >
      {{slotprops.lastname}} {{slotprops.firstname}}
    </template>
   </Namelist>

   <Namelist>
    <template v-slot:default="slotprops" >
      {{slotprops.firstname}}
    </template>
   </Namelist>

   <h4>App Components</h4>
   <Childstyle>
   <h4>Childstyle component</h4>
   </Childstyle>

   <button @click="activetab = 'TabA'">TabA</button>
   <button @click="activetab = 'TabB'">TabB</button>
   <button @click="activetab = 'TabC'">TabC</button>

   <keep-alive>
      <component :is="activetab" />
   </keep-alive>
   <!--<TabA v-if="activetab === 'TabA'"/>
   <TabB v-if="activetab === 'TabB'" />
   <TabC v-if="activetab === 'TabC'"/>-->


   <teleport to="#portal-root">
      <Portal />
   </teleport>

  </div>
</template>

<script>
import Main from './components/Main.vue'
import Article from './components/Article.vue'
import ComponentA from './components/ComponentA.vue'
import Popup from './components/Popup.vue'
import Input from './components/Input.vue'
import Card from './components/Card.vue'
import Namelist from './components/Namelist.vue'
import Childstyle from './components/Childstyle.vue'
import TabA from './components/TabA.vue'
import TabB from './components/TabB.vue'
import TabC from './components/TabC.vue'
import Portal from './components/Portal.vue'


export default {    
  name: 'App',
  components:{
    Main,
    Article,
    ComponentA,
    Popup,
    Input,
    Card,
    Namelist,
    Childstyle,
    TabA,
    TabB,
    TabC,
    Portal,      
  },
  
  data(){
    return{
      activetab: 'TabA',
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

<style scoped>
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
  margin-bottom: 10vw;
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
.align{
  width: 70%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  flex-direction:row;
  margin: auto;
} 

h4{
  color: red;
}
</style>
