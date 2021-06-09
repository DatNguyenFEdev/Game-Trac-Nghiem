<template>
  <div id="app">
    <div v-show="screen =='question'">
      <Question :question="questions[currentQuestion]"/>
      <button class="btn btn-primary" 
      @click="currentQuestion --" v-show="currentQuestion >0">&lt;</button>
      <button class="btn btn-primary" 
      @click="currentQuestion ++" v-show="currentQuestion <questions.length-1">&gt;</button>
      <button class="btn btn-primary" 
      v-show="currentQuestion  == questions.length-1"
      @click="screen = 'result'">
      Nộp bài</button>
    </div>
    <div v-show="screen == 'result'">
      <Result :questions="questions"/>
    </div>
  </div>
</template>

<script>
import Question from "./components/Question"
import Result from "./components/Result"
export default {
  name: 'App',
  data() {
    return {
      screen:'question',
      currentQuestion: 0,
      questions: [
        {
          content: 'ban ten la gi : ',
          answers: ['dat','duc','huy','ha'],
          correctAnswer: false,
          point: 1,
          answer: null
        },
        {
          content: 'em ban ten la gi : ',
          answers: ['rong','ran','ho','dai bang'],
          correctAnswer: false,
          point: 1,
          answer: null
        },
        {
          content: 'viet nam co bao nhieu tinh: ',
          answers: ['64','45','76','31'],
          correctAnswer: false,
          point: 1,
          answer: null
        },
        {
          content: 'ha noi cop bao nhieu pho : ',
          answers: ['5','6','9','8'],
          correctAnswer: false,
          point: 1,
          answer: null
        },
        {
          content: 'ban bao nhieu tuoi : ',
          answers: ['3','4','8','10'],
          correctAnswer: false,
          point: 1,
          answer: null
        },
      ]
    }
  },
  components: {
    Result,
    Question,
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
