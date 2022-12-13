<template>
    <header style="padding: 15px;">
      <h1>Step 2: Identifying noun phrases</h1>
      <p>To identify noun phrases, drag words from the scenario description sentences and drop them into the noun phrase boxes. Some boxes take multiple words.</p>
    </header>
    <main>
      <div class="flexbox">
        <board_component :id="board_two">
          
          </board_component>
      </div>
      <div class="flexbox">
        <board_component :cards="first" :id="board_one">
          <card_component v-for="card in first" :key="card" :card="card" :draggable="true" :content="card">
            <p>{{ card }}</p>
            </card_component>
          </board_component>  
      </div>
      <div class="flexbox">
        <board_component :cards="second" :id="2">
          <card_component v-for="card in second" :key="card" :card="card" :draggable="true" :content="card">
            <p>{{ card }}</p>
            </card_component>
          </board_component>
      </div>
      <div class="flexbox">
        <board_component :cards="third" :id="3">
          <card_component v-for="card in third" :key="card" :card="card" :draggable="true" :content="card">
            <p>{{ card }}</p>
            </card_component>
          </board_component>
      </div>
      <div class="flexbox">
        <board_component :cards="fourth" :id="4">
          <card_component v-for="card in fourth" :key="card" :card="card" :draggable="true" :content="card">
            <p>{{ card }}</p>
            </card_component>
          </board_component>
      </div>
      <div class="flexbox">
        <board_component :cards="fifth" :id="5">
          <card_component v-for="card in fifth" :key="card" :card="card" :draggable="true" :content="card">
            <p>{{ card }}</p>
            </card_component>
          </board_component>
      </div>
      <div class="flexbox">
        <board_component :cards="sixth" :id="6">
          <card_component v-for="card in sixth" :key="card" :card="card" :draggable="true" :content="card">
            <p>{{ card }}</p>
            </card_component>
          </board_component>
      </div>
      
    </main>
    <div id="buttons">
      <input type="submit" value="VERIFY" class="button button4" v-on:click="validate()">
    </div>
</template>

<script>
import card_component from '@/components/card_component.vue';
import board_component from '@/components/board_component.vue';
export default {
  name: 'page_two',
  components: {
    card_component,
    board_component,
},
  data() {
    return {
      first: ['This','is','a','test'],
      second: ['This','is','a','test','too'],
      third: ['This','is','a','test','too','again'],
      fourth: ['This','is','a','test','too','again','again'],
      fifth: ['This','is','a','test','too','again','again','again'],
      sixth: ['This','is','a','test','too','again','again','again','again','again','again','again','again','again','again','again','again','again','again','again','again','again','again','again','again','again','again'],
    }
  },
  methods: {
    validate() {
      alert("Hello");
    }
  }
}

</script>

<style scoped>
* {
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Open Sans', sans-serif;
  background-color: #f5f5f5;
}

.flexbox {
  display: flex;
  justify-content: space-evenly;

  height: 100%;
  width: 100%;

  margin: 0 10;
  padding: 15px
}

.flexbox .board {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;

  width: 90%;
  height: fit-content;
  min-height: 5vh;

  background-color: #313131;

  padding: 15px;
}

.flexbox .first_board {
  display: flex;
  flex-direction: column;
  height: 90%;
  width: 100%;

  background-color: #ebeaea;
  margin-right: 1.5rem;
}

.flexbox .board .card {
  padding: 15px 25px;
  background-color: #f5f5f5;
  text-align: center;
  color: #313131;
  width: fit-content;
  cursor: pointer;
  margin-bottom: 15px;
  margin-right: 10px;
}

.flexbox .first_board .card {
  padding: 15px;
  width: 95%;
  background-color: #f5f5f5;
  cursor: pointer;
  margin-bottom: 15px;
}

#buttons {
  width: 50px;
  margin: 15;
  text-align: center;
}

.button {
  border: none;
  color: white;
  padding: 13px 50px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin: 50px 20px;
  transition-duration: 0.4s;
  cursor: pointer;
  border-radius: 5%;
}

.button4 {
  background-color: white;
  color: black;
  border: 2px solid #017047;
}

.button4:hover {
  background-color: #017047;
  color: white;
}
</style>
