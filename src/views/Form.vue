<template>
  <div>
    <div class="column is-half is-offset-one-quarter panel is-primary p-0">
      <p class="button is-small is-info is-pulled-left">STEP１</p>
      <h1 class="title is-6 has-text-centered panel-heading mb-0">お客様の情報を入力してください。</h1>

      <form>
        <div class="has-text-info">-性別-</div>
        <br />
        <label for="male">男性</label>
        <input type="radio" value="male" />
        <label for="female" class="ml-3">女性</label>
        <input type="radio" value="female" />
        <br />
        <br />
        <div class="has-text-info">-生年月日-</div>
        <br />
        <select v-model="year">
          <option v-for="age in chronology" :key="age.year" :value="age.year">{{ age.label }}年</option>
        </select>年
        <select>
          <option v-for="m of 12" v-bind:key="m" v-bind:value="m + '月'">{{ m }}</option>
        </select>月
        <select>
          <option v-for="d of 31" :key="d">{{ d }}</option>
        </select>日
      </form>
    </div>
    <div class="has-text-centered">
      <router-link to="/Question" class="button is-primary">次へ進む</router-link>
    </div>
  </div>
</template>
<script>
import "bulma/css/bulma.css";
import { chronology } from "../store/modules/years";

export default {
  data() {
    return {
      year: 2021,
      chronology,
    };
  },
};
</script>

<style></style>
