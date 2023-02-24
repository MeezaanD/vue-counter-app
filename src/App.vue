<template>
  <div class="container bg-dark p-5">
    <div class="row">
      <div class="col">
        <form class="form">
          <div>
            <input type="text" placeholder="Modify Value" readonly :value="counter">
          </div>
          <div class="row">
            <div class="col">
              <button @click.prevent="increase" class="btn btn-info">Increase</button>    
            </div>      
            <div class="col">
              <button @click.prevent="decrease" class="btn btn-danger">Decrease</button>
            </div>      
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script>



export default {
  computed: {
    counter() {
      return this.$store.state.counter  
    }
  },
  methods: {
    increase() {
      this.$store.dispatch('increaseCounter')
    },
    decrease() {
      this.$store.dispatch('decreaseCounter')
    }
  }
}

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
