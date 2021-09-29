<template >
  <div>
    <div>
      <div class="column is-half is-offset-one-quarter panel is-primary p-0">
        <p class="button is-small is-info is-pulled-left">STEP2</p>
        <h1 class="title is-6 has-text-centered panel-heading mb-0">以下にお答えください</h1>
        <div>
          <dt
            v-for="questiondata in health_Confirmation"
            v-bind:key="questiondata.id"
            class="has-text-info"
          >{{ questiondata.question1 }}</dt>
          <br />
          <label for="yes">はい</label>
          <input type="radio" value="yes" id="yes" v-model="question.answer1" />
          <label>いいえ</label>
          <input type="radio" value="no" id="no" v-model="question.answer1" />
          <br />
          <br />
          <div v-if="question.answer1 !== ''">
            <dt
              v-for="questiondata in health_Confirmation"
              v-bind:key="questiondata.id"
              class="has-text-info"
            >{{ questiondata.question2 }}</dt>
            <br />
            <label for="yes">はい</label>
            <input type="radio" value="yes" id="yes" v-model="question.answer2" />
            <label>いいえ</label>
            <input type="radio" value="no" id="no" v-model="question.answer2" />
          </div>
          <br />
          <div v-if="question.answer2 !== ''">
            <dt
              v-for="questiondata in health_confirmation"
              v-bind:key="questiondata.id"
              class="has-text-info"
            >{{ questiondata.question3 }}</dt>
            <br />
            <label for="yes">はい</label>
            <input type="radio" value="yes" id="yes" v-model="question.answer3" />
            <label>いいえ</label>
            <input type="radio" value="no" id="no" v-model="question.answer3" />
          </div>
          <br />
        </div>
      </div>
    </div>
    <div class="has-text-centered">
      <router-link to="/" class="button is-primary mr-6 mb-5">前へ戻る</router-link>
      <router-link to="/Text" class="button is-primary mb-5">次へ進む</router-link>
    </div>
  </div>
</template>

<script>
import { question_List } from "../store/question";

export default {
  data() {
    return {
      question: {
        answer1: "",
        answer2: "",
        answer3: "",
      },
      question_List,
    };
  },
  computed: {
    health_Confirmation() {
      return this.question_List.health_Confirmation;
    },
  },
};
</script>

<style>
</style>



