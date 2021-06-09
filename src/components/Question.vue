<template>
    <div>
        <div class="question">
            Câu hỏi: {{question.content}} ({{question.point}} điểm)
        </div>
        <div class="answers row col" v-for="(answer,index) in question.answers" :key="index">
            <div class="btn btn-primary" 
            @click="question.answer = index"
            :class="{selected:question.answer == index}"
            >{{answer}}</div>
        </div>
    </div>
</template>

<script>
export default {
    props: ['question'],
    data() {
        return {

        }
    }
}
</script>

<style scoped>
    .btn {
        display: block;
       margin-bottom: 10px;
    }
    .selected {
        background-color: red;
    }
</style>