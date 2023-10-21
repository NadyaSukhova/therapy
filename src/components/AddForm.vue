<template>
  <center>
    <form @submit.prevent>
      <h3>Добавить запись</h3>
      <img id="thyme" src="../assets/thyme.png" />
      <label for="thought">Мысль:</label>
      <textarea id="thought" v-model="thought"></textarea><br />
      <label for="mistakes">Когнитивное искажение:</label>
      <div id="mistakes">
        <input type="checkbox" value="0" v-model="mistakes" />Мышление «Всё или
        ничего» <br />
        <input
          type="checkbox"
          value="1"
          v-model="mistakes"
        />Сверхобобщение<br />
        <input type="checkbox" value="2" v-model="mistakes" />Пессимизм<br />
        <input type="checkbox" value="3" v-model="mistakes" />Обесценивание
        положительного<br />
        <input type="checkbox" value="4" v-model="mistakes" />Чтение мыслей<br />
        <input type="checkbox" value="5" v-model="mistakes" />Ошибка
        предсказания<br />
        <input
          type="checkbox"
          value="6"
          v-model="mistakes"
        />Преувеличение/преуменьшение<br />
        <input type="checkbox" value="7" v-model="mistakes" />Эмоциональное
        обоснование<br />
        <input type="checkbox" value="8" v-model="mistakes" />Императивы<br />
        <input type="checkbox" value="9" v-model="mistakes" />Ярлыки<br />
        <input type="checkbox" value="10" v-model="mistakes" />Вина
      </div>
      <button id="question" @click="showHint = !showHint"></button>
      <div class="hint" v-if="showHint">
        <strong>«Всё или ничего».</strong> Этот вид когнитивных искажений
        описывает склонность к оценке своих личных качеств исключительно в
        черно-белых тонах.<br /><strong> Сверхобобщение.</strong> Вы делаете
        ошибочный вывод, что событие, которое произошло с вами один раз, будет
        повторяться снова и снова. <br /><strong> Пессимизм.</strong> Находясь в
        определенной ситуации, вы выбираете негативную деталь и фиксируетесь
        исключительно на ней, таким образом негативно воспринимая всю ситуацию в
        целом.<br /><strong> Обесценивание положительного. </strong>Настойчивая
        привычка некоторых людей в депрессии превращать нейтральный или даже
        позитивный опыт в негативный. Вы не просто игнорируете положительный
        опыт — вы быстро и умело превращаете его в кошмар.<br /><strong>
          Чтение мыслей.</strong
        >
        Вы делаете предположение, что другие люди смотрят на вас свысока, и
        настолько убеждены в этом, что даже не пытаетесь проверить это
        предположение. <br /><strong> Ошибка предсказания.</strong> Вы
        предполагаете, что произойдет что-то плохое, и принимаете это
        предсказание как факт, хотя оно не соответствует реальности.
        <br /><strong> Преувеличение/преуменьшение.</strong> Вы либо раздуваете
        вещи до гигантских масштабов, либо делаете их микроскопически
        маленькими. Обычно эффект увеличения работает, когда вы смотрите на свои
        собственные ошибки, страхи или недостатки, преувеличивая их важность, а
        когда вы думаете о своих сильных сторонах, то можете делать
        противоположное — преуменьшать их значимость . <br /><strong>
          Эмоциональное обоснование. </strong
        >Вы принимаете свои эмоции как доводы в пользу некой истины. Такая
        логика гласит: «Я чувствую себя дураком — следовательно, я дурак».
        <br /><strong> Императивы.</strong> Вы пытаетесь замотивировать себя,
        говоря: «Я должен это сделать» или «Я обязан это сделать». Эти заявления
        вызывают ощущение принуждения и обиды. Как ни парадоксально, в итоге вы
        чувствуете апатию и отсутствие мотивации.<br /><strong> Ярлыки.</strong>
        Навешивание на себя ярлыков, крайняя форма сверхобобщения. Вы можете
        подумать «Я неудачник», хотя это можно заменить на «Я допустил ошибку».
        <br /><strong> Вина. </strong>Вместо решения проблемы, вы ищите
        виноватых. В данном случае возможно обвинение других или самообвинение.
      </div>
      <label for="argument">Опровержение:</label>
      <textarea id="argument" v-model="argument"></textarea><br>
      <label for="date">Дата:</label>
      <input
        type="date"
        id="date"
        :max="nowDate"
        v-model="noteDate"
        style="margin-bottom: 20px"
      /><br />
      <div id="end">
        <button @click="addNote">Добавить</button>
        <img id="mint" src="../assets/mint.png" />
      </div>
    </form>
  </center>
</template>

<script>
import moment from "moment";

export default {
  name: "AddForm",
  data() {
    return {
      thought: "",
      mistakes: [],
      argument: "",
      noteDate: moment().format("YYYY-MM-DD"),
      nowDate: moment().format("YYYY-MM-DD"),
      showHint: false,
    };
  },
  methods: {
    addNote() {
      console.log({
        thought: this.thought,
        mistakes: [...this.mistakes],
        argument: this.argument,
        date: this.noteDate,
      });
    },
  },
};
</script>

<style>
form {
  width: 334px;
  height: fit-content;
  border-radius: 30px;
  background: #fff;
  text-align: left;
}
h3 {
  padding-top: 7px;
  color: #297d77;
  text-align: center;
  font-size: 36px;
  font-weight: 500;
}

#thyme {
  width: 71px;
  position: absolute;
  left: calc(50% - 167px);
  top: calc(169px + 16.5px);
}

form #mint {
  width: 60px;
  position: relative;
  left: 180px;
  bottom: 0;
}

#question {
  background-image: url("../assets/question.png");
  background-color: transparent;
  background-repeat: no-repeat;
  background-size: contain;
  border: 0;
  width: 36px;
  height: 34px;
  margin-left: calc(50% + 107px);
  margin-bottom: 15px;
  position: relative;
}

label {
  margin-left: 16px;
  font-size: 24px;
  vertical-align: top;
  margin-right: 16px;
}

textarea {
  margin-bottom: 20px;
  resize: both;
  min-height: 40px;
}

button {
  font-size: 24px;
  border: 0;
  background-color: #297d77;
  color: #fff;
  border-radius: 20px;
  position: relative;
  left: 16px;
  bottom: 20px;
}

#mistakes {
  text-align: left;
  margin-left: 10px;
  font-size: 20px;
}

#end {
  display: inline;
}

.hint {
  height: 200px;
  overflow-y: scroll;
  font-size: 18px;
  margin-bottom: 20px;
  margin-left: 16px;
}
</style>
