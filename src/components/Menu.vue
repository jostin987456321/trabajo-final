<template>
<div class="card-mayor">
  <div class="card-contenedor" id="contenedor">
      <div class="card1">
         <div class="usuario">
             <span>{{nombre}}</span>
              
         </div>
         <div class="N-orden">
             <span>N-orden</span>
         </div> 
    </div>
    <div class="card2">
          <div class="pedidos" v-for="todo in todos" :key="todo.id">
          <h3>{{todo.name}}</h3>
            <div class="numeracion">
              <p>{{todo.id}}</p>
          </div>
        </div>
    </div>
    <div class="card3">
      <button  @click="color1">proseso</button>
      <button @click="color2">finalizado</button>
    </div>
  </div>
</div>     
</template>
<script>
import axios from "axios";

export default {
  data() {
    return {
      todos: [],
      hora: 0,
      minutos: 0,
      segundos: 0,
      nombre: "jostin"
    };
  },
  // <----------lista de array---------------->
  mounted() {
    this.getTodos();
  },
  methods: {
    getTodos() {
      axios
        .get("https://jsonplaceholder.typicode.com/users/")
        .then(response => {
          this.todos = response.data;
        })
        .catche(e => console.log(e));
    },
    color1() {
      let btn1 = document.getElementById("contenedor");
      

      btn1.addEventListener("click", e => {
        btn1.style.backgroundColor = "gold";
        btn1.style.transition = "1s";
        btn1.style.color= "#2c3e50"
      });
      
    },
    color2(){
      let btn2 = document.getElementById("contenedor");
      btn2.addEventListener("click", e => {
          btn2.style.backgroundColor = "rgb(37, 204, 22)"
          btn2.style.transition = "1s"
          btn2.style.color = "white"
      });
    },
    actualizarhora(){
      
    }

  }
};

// setInterval(clock.actualizartiempo, 1000);
</script>
<style>
.card-mayor {
  width: auto;
  height: 50%;
  margin-bottom: 20px;
  border-radius: 20px;
  /* display: flex; */
  /* background-color: aqua; */
}

.card-contenedor {
  width: 350px;
  height: 50%;
  margin-bottom: 20px;
  margin: 10px;
  border-radius: 20px;

  border: 3px solid rgb(179, 171, 171);
}

.card1 {
  width: 100%;
  height: 125px;
  display: flex;
  border-bottom: 1px solid rgb(163, 155, 155);
}

.usuario {
  width: 68%;
  height: 125px;
  /* background-color: gold; */
  display: flex;
  /* border-top: 1px solid black; */
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

.N-orden {
  width: 32%;
  height: 125px;
  /* background-color: rgb(37, 204, 22); */
  display: flex;
  justify-content: center;
  align-items: center;
}
/* <---------segunda card-----------> */

.card2 {
  width: 70%;
  height: 515px;
  /* background-color: rgb(53, 162, 224); */
  /* display: flex; */
}

.card3 {
  width: 100%;
  height: 70px;
  /* background-color: aqua; */
  border: 1px solid black;
  border-radius: 20px;
  display: flex;
  justify-content: space-around;
  align-items: center;
}

button {
  width: 100px;
  height: 50px;
  border-radius: 30px;
  color: blue;
  border: 1px solid rgb(19, 96, 211);
}

.pedidos {
  width: 315px;
  height: 50px;
  /* background-color: chartreuse; */
  display: flex;
}

.numeracion {
  width: 110px;
  height: 50px;
  /* display: inline; */
  /* height: 100%; */
  /* background-color: rgb(219, 46, 46); */
}

h3 {
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  font-size: 16px;
  width: 235px;
  height: 25px;
  /* background-color: aqua; */
  /* color: red; */
}

p {
  color: black;
  text-align: center;
}

/* <-----------MODO MOVIL----------------> */

@media screen and (max-width: 360px) {
  .card-mayor {
    width: 100%;
    height: 100%;
    margin-bottom: 20px;
    /* background-color: aqua; */
  }
  /* <----------primera card------------> */
  .card1 {
    width: 100%;
    height: 125px;
    /* background-color: blue; */
    display: flex;
  }

  .usuario {
    width: 69%;
    height: 125px;
    /* background-color: gold; */
    display: flex;
    /* border-top: 1px solid black; */
    flex-direction: column;
    align-items: center;
    justify-content: space-around;
  }

  .card-contenedor {
    width: 100%;
    height: 50%;
    margin-bottom: 20px;
    border-radius: 20px;
    /* display: flex; */
    /* background-color: aqua; */
  }

  .N-orden {
    width: 32%;
    height: 125px;
    /* background-color: rgb(163, 154, 168); */
    display: flex;
    flex-direction: column;
    justify-content: center;
  }
  /* <---------segunda card-----------> */

  .card2 {
    width: 100%;
    height: 100%;
    /* background-color: rgb(53, 162, 224); */
    /* display: flex; */
  }

  .card3 {
    width: 100%;
    height: 70px;
    /* background-color: aqua; */
    display: flex;
    justify-content: space-around;
    align-items: center;
  }
  .pedidos {
    width: 345px;
    height: 50px;
    /* background-color: chartreuse; */
    display: flex;
  }

  .numeracion {
    width: 110px;
    height: 50px;
    /* display: inline; */
    /* height: 100%; */
    /* background-color: rgb(219, 46, 46); */
  }

  h6 {
    font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
    font-size: 13px;
    width: 235px;
    /* background-color: aqua; */
    /* color: red; */
  }

  p {
    color: rgb(2, 2, 2);
    text-align: center;
  }
}
</style>


