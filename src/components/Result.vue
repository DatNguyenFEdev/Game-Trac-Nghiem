<template>
  <div id="result">
      <h1>Result: {{questions.reduce( (total,question) => {
          if(question.correctAnswer == question.answer){
            total = total + question.point
          }
          return total;
        }, 0)    }}</h1>
      <div v-for="(question,questionsIndex) in questions" :key="questionsIndex">
        {{question.content}}
        <div v-for="(answer, index) in question.answers" :key="index">
          <div :class="{error: question.answer == index && question.correctAnswer != question.answer,
                        correct: question.correctAnswer == index}">
            {{answer}}
          </div>
        </div>
      </div>
  </div>
</template>

<script>
export default {
    props:['questions'],
    data() {
        return {

        }
    }
}
</script>

<style scoped>
.correct {
  background-color: blue;
  color: white;
}
.error {
  background-color: red;
  color: white;
}
</style>