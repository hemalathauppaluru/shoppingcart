<template>
  <div class="main">
    <div class="header">&nbsp; Smarat Phones</div>
    <div class="cartitemheader">
     Number of Added Items {{ cartcounter(c1, c2) }}
    </div>
  </div>
  <div class="container">
    <div class="box">
      <img
        src=" https://encrypted-tbn0.gstatic.com/shopping?q=tbn:ANd9GcTblSYJ4485lqPY4vau0_PmnmbP_SOfbnjBFkEL9FWUsUah998gK0Dy_tXvXTjkDQ&usqp=CAc"/>
      <h3 class="boxh1">
        NOKIA 8 SMARTPHONE LTE,<br />
         POLISHED COPPER
      </h3>
      
      <h3 class="boxh3">₹12900</h3>
      <button class="boxbutton1" v-on:click="increase">ADD TO CART</button>
      <h1 class="boxbutton2">{{ counter1 }}</h1>
      <button class="boxbutton3" v-on:click="decrease">REMOVE FROM CART</button>
    </div>
    <div class="box">
      <img
        src= "https://encrypted-tbn2.gstatic.com/shopping?q=tbn:ANd9GcTO48_IJcFD5uT8XeTywX5bylOlhM2Vi4C4aq63oGDGUIEbf7f0mdtbyIRHfxielT__tgyCreuuBA&usqp=CAc"/>
      <h1 class="boxh1">
        MOTOROLOLA MOTO G5S<br />
        SMARTPHONE, GREY
        
      </h1>
      
      <h3 class="boxh3">₹17000</h3>
      <button class="boxbutton1" v-on:click="plus">ADD TO CART</button>
      <h1 class="boxbutton2">{{ counter2 }}</h1>
      <button class="boxbutton3" v-on:click="mines">REMOVE FROM CART</button>
    </div>
  </div>
  <div class="totalamount">TOTAL = ₹{{ total(t1, t2) }}</div>
  <button class="totalreset" v-on:click="reset(pud1, pud2)">RESET</button>
  <hr />
</template>
<script>
export default {
  name: "App",
  data: () => {
    return {
      counter1: 0,
      counter2: 0,
    };
  },
  methods: {
    increase () {
      this.counter1++;
    },
    decrease() {
      if (this.counter1 > 0) {
        this.counter1--;
      }
    },
    pud1() {
      this.counter1 = 0;
    },
    pud2() {
      this.counter2 = 0;
    },
    reset (pud1, pud2) {
      pud1();
      pud2();
    },
    plus() {
      this.counter2++;
    },
    mines () {
      if (this.counter2 > 0) {
        this.counter2--;
      }
    },
    c1() {
      this.counter1;
    },
    c2() {
      this.counter2;
    },
    cartcounter () {
      return this.counter1 + this.counter2;
    },
    t1() {
      return this.counter1 * 12900;
    },
    t2 () {
      return this.counter2 * 17000;
    },
    total(t1, t2) {
      return t1() + t2();
    },
  },
};
</script>

<style scoped>
.main {
  background-color: #41d6e1;
  border-radius: 5px;
  display: flex;
  color: white;
  padding: 10px;
}
.header {
  text-align: center;
  font-size: 35px;

}
.cartitemheader {
  font-size: 25px;
  padding-top: 10px;
  margin-left: 400px;
  color: black;
  margin-left: 800px;
}

.header i {
  font-size: 50px;
}
body {
  margin: 0;
  padding: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
}
.container {
  width: 700px;
  height: auto;
  margin: 0 auto;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  grid-gap: 20px;
  padding: 10px;
}
.box img {
  height: 250px;
  text-align: center;
}
.boxh1 {
  font-size: 25px;
}
.boxp {
  font-size: 16px;
  margin-top: 30px;
  color: gray;
}
.boxh3 {
  font-size: 25px;
}
.boxp1 {
  color: gray;
}
.boxbutton1 {
  padding-left: 50px;
  padding-right: 50px;
  padding-top: 10px;
  padding-bottom: 10px;
  color: white;
  background-color: #4169e1;
  border: none;
  border-radius: 50px;
  cursor: pointer;
}
.boxbutton2 {
  text-align: center;
  padding: 10px;
  border: 0px solid black;
  width: 50px;
  margin-left: 110px;
  color: gray;
}
.boxbutton3 {
  padding-left: 30px;
  padding-right: 30px;
  padding-top: 10px;
  padding-bottom: 10px;
  color: white;
  background-color: #4169e1;
  border: none;
  border-radius: 3px;
  cursor: pointer;
  border-radius: 20px;
}
.totalamount {
  font-size: 20px;
  margin-left: 600px;
  padding-top: 20px;
  color: gray;
}
.totalreset {
  margin-left: 650px;
  margin-top: 20px;
  background-color: #13c2e0;
  padding-left: 50px;
  padding-right: 50px;
  padding-top: 10px;
  padding-bottom: 10px;
  border: none;
  cursor: pointer;
  color: rgb(146, 15, 15);
}
</style>