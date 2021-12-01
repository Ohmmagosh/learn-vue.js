<template>
  <section>
    <div>
      <img v-bind:src="picture" :width="size" height="" alt="" ref="imageURL"><br>
      <!-- <form action="" @submit.prevent="submitForm">
        <label for="">Nickname   </label>
        <input type="text"  ref="nickNameEL">
        <button type="submit">Submit</button>
      </form> -->
      <h1>ชื่อ-นามสกุล : {{getFullname}}</h1>
      <h1>salary : {{salary}} bath</h1>
      <h1>salary per year: {{gitIncome}} bath</h1>
      <h1>Position : {{getDepartment}}</h1>
      
      <!-- <h2>Nickname : {{Nname}}</h2> -->
      
      <!-- {{isVisible}} -->
      <button @click="addSalary(5000)">Add salary</button>
      <button @click="reduceSalary(5000)">reduce salary</button>
      <button @click="toggleVisible">{{isVisible ? "Hide" : "Show"}} Detail</button>
      <button @click="toggleVisible2">{{isVisible2 ? "Hide" : "Show"}} Method</button>
      <article v-show="isVisible">
        <p>ที่อยู่ : <span v-html=address></span></p>
        <p>Social : <a :href="social" target="_blank">Link</a></p>
        <p v-if="hobby.length === 0">ไม่มีงานอดิเรก</p>
        <div v-else>
          <p>Hobby :</p>
          <ul>
              <li v-for="(item,index) in hobby" :key="index">{{index+1}} - {{item}}</li>
          </ul>
        </div>
        <p>ข้อมูลพื้นฐาน :</p>
        <ul>
          <li v-for="(item,key) in general" :key="key">{{key}} : {{item}}</li>
          <!-- <li>gender : {{general.gender}}</li>
          <li>weight : {{general.weight}} kg</li>
          <li>height : {{general.height}} cm</li>
          <li>status : {{general.status}}</li>
          <li>Cdiese : {{general.Cisease}}</li> -->
        </ul>
      </article>
      <article v-show="isVisible2">
        <hr>
        <h2>Method : {{getRandomByMethod()}}</h2>
        <h2>Method2 : {{getRandomByMethod()}}</h2>
        <h2>Method3 : {{getRandomByMethod()}}</h2>
        <hr>
        <h2>Computed : {{getRandomByComputed}}</h2>
        <h2>Computed2 : {{getRandomByComputed}}</h2>
        <h2>Computed3 : {{getRandomByComputed}}</h2>
        <hr>
      </article>
      <!-- <button @click="showData">Click</button>
      <button @click.ctrl="increment(10)">เพิ่ม</button>
      <button @click.middle="decrement(10)">ลด</button> -->
    </div>
  </section>
</template>

<script>


export default {
  name: 'App',
  data(){
    return {
      fname:"lilly",
      lname:"yang",
      Nname:"",
      age:20,
      address:"<strong>Bangkok</strong>",
      picture:"https://images.unsplash.com/photo-1542996966-2e31c00bae31?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=687&q=80",
      size : 500,
      social:"https://unsplash.com/photos/orYdcTza06E",
      hobby:["reading a book","playgame","watching tv"],
      general:{gender:"female",weight:47,height:155,status:"single",Cisease:false},
      isVisible:false,
      isVisible2:false,
      salary:30000
    }
  },
  methods:{
    showData(){
      alert(this.fname+" "+this.lname)
    },
    // increment(value){
    //   this.age+=value
    // },
    // decrement(value){
    //   this.age-=value
    // },
    submitForm(){
      this.Nname = this.$refs.nickNameEL.value;
      console.log(this.$refs.imageURL);
      console.log(this.$refs.nickNameEL);
      alert("Submit complete");
    },
    toggleVisible(){
      this.isVisible = !this.isVisible
    },
    toggleVisible2(){
      this.isVisible2 = !this.isVisible2
    },
    getRandomByMethod(){
      return Math.random();
    },
    addSalary(value){
      return this.salary+=value
    },
    reduceSalary(value){
      return this.salary-=value
    }
  },
  computed:{
    getFullname(){
      return `${this.fname+" "+this.lname} อายุ : ${this.age}`
    },
    getRandomByComputed(){
      return Math.random();
    },
    gitIncome(){
      return this.salary * 12 ;
    },
    getDepartment(){
      return this.salary>=35000 ? "Project manager" : "Programmer"
    }
  },
  watch:{
    salary(value){
      if(value>50000){
        alert("เงินเดือนไม่ควรเกิน 50,000 บาท");
        setTimeout(()=>{
          this.salary = 30000
        },500)
      }
    }
  }
}
</script>

<style>
ul{
  list-style-type: none;
}

</style>
