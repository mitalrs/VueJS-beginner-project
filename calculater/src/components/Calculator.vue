<script>
export default {
  data() {
    return {
      calculateVale: "",
      calculaterElement: ["C","*","/","-","7","8","9","+","4","5","6","%","1","2","3","=","0","."],
    };
  },
  methods: {
    action(n){
        if(!isNaN(n) || n==='.'){
            this.calculateVale += n+'';
        }
    }
  }
};
</script>

<template>
  <div class="p-3" style="background-color: white">
    <div
      class="w-full rounded m-1 p-3 ext-right lead font-weight-bold text-black"
      style="background-color: #cccccc"
    >
      {{ calculateVale || 0 }}
    </div>

    <div class="row no-gutters">
        <div class="col-3" v-for="n in calculaterElement" :key="n">
            <div class="lead text-black text-center hover-class"
            :class="{'bg-green': ['c','*','/','-','+','%','='].includes(n)}"
            @click="action(n)"
            >
                {{ n }}
            </div>
        </div>
    </div>
  </div>
</template>

<style scoped>
.hover-class:hover {
    cursor: pointer;
    background-color: rgb(209, 209, 209);
}
.bg-green{
    background-color: green;
}
</style>
