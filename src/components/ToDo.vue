<template>
<div class="container">
  <div class="wrapper">
  
          <div class="head">
  
            <div class="logo">
              TODO
            </div>
            
          </div>
  
          <div class="creates">
  
            <i class="fas fa-plus icon" @click="addToList"></i>
  
            <input class="testo" v-model="toDo" v-on:keyup.enter="addToList" placeholder="Inserisci una faccenda">
          </div>
  
          <div class="delete">
  
            <i class="fas fa-trash icon" @click="cleanAll(index)"></i>
  
            <p class="testo">Clean All</p>
            
          </div>
  
          <div class="list">
            <ul class="todolist">
              <li v-for="(element,index) in list" :key="element.id">
                 <i class="fas fa-minus icon" @click="remove(index)"></i>
                 <div class="txt testo">{{element}}</div> 
              </li>
            </ul>
          </div>
  
</div>
</div>
</template>

<script>
export default {
  name: 'Todo',
  props: {
    msg: String
  },
  data() {
    return {
    list: [],
    toDo:'',
    active:true,
    darkModeSet: false,
    lightMode:{
      background: '#FAFAFA',
    }
    };
  },
  methods: {
    addToList: function() {
      if (this.toDo === '' || this.toDo === null || this.toDo.value === 0){
        this.toDo=alert('Please enter a job!');
      } else {
      this.list.push(this.toDo);
      this.toDo= '';
    }
    },
    remove: function(index) {
     this.list.splice(index,1);
    },
    cleanAll: function() {
      this.list = [];
    },
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import '../../public/style/positions.scss';
@import '../../public/style/color.scss';

.icon {
  font-size: 25px;
  color: $color-white;
  margin: 0 30px;
}

.testo {
  font-size: 25px;
  color: $color-white;
}
.container{
  background-color: #171824;
  background-image: url("../assets/back.jpg");
  background-repeat: no-repeat;
  background-size: 100%;
  overflow-x: hidden;
  .wrapper {
  @include col-c;
  min-height: 100vh;

  .head{
  width: 40%;
  height: 100px;
  @include row-sb-c;
  .logo{
    color: $color-white;
    font-size: 45px;
  }
  .mode{
    color: $color-white;
    font-size: 18px;
  }
  }

  .creates{
  width: 40%;
  height: 100px;
  margin: 30px 0;
  background-color: $color-black;
  @include row-st-c;
  input {
  border: 0px;
  background-color: $color-black;
  word-break: break-all;
  width: 80%;
  max-height: 100%;
}
input:focus {
  border: none;
  outline: 0;
}
}

  .delete{
  width: 40%;
  height: 100px;
  margin: 0 0 30px 0;
  background-color: $color-black;
  @include row-st-c;
  }

  .list{
  width: 40%;
  min-height: 500px;
  background-color: $color-black;
  .todolist {
  list-style: none;
  li {
  width: 100%;
  min-height: 100px;
  @include row-st-c;
  .far {
  color: $color-white;
  font-size: 18px;
  margin-left: 30px;
}
.txt {
  word-break: break-all;
  width: 75%;
}
}
}
  }
}
}

@media screen and (min-width: 620px) and (max-width: 768px) {
  .testo {
    font-size: 18px;
  }

  .icon {
    font-size: 18px;
    margin: 0 15px;
  }

  .wrapper{
    .head {
    width: 60vw;
  }
  .creates {
    width: 60vw;
    input {
    width: 60%;
  }
  }
  .delete {
    width: 60vw;
  }
  .list {
    width: 60vw;
  }
  }
}

@media screen and (min-width: 360px) and (max-width: 619px) {
  .testo {
    font-size: 18px;
  }

  .icon {
    font-size: 18px;
    margin: 0 15px;
  }

  .wrapper{
    .head {
    width: 85vw;
  }
  .creates {
    width: 85vw;
  }
  .delete {
    width: 85vw;
  }
  .list {
    width: 85vw;
  }
  }
}
</style>
