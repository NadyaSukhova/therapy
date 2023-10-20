<template>
  <center>
    <form>
      <h3>Добавить запись</h3>
      <img id="thyme" src="../assets/thyme.png" />
      <label for="thought">Мысль:</label>
      <textarea id="thought"></textarea><br />
      <label for="mistakes">Когнитивное искажение:</label>
      <div id="mistakes">
        <input type="checkbox" id="0" />Мышление "Всё или ничего" <br />
        <input type="checkbox" id="1" />Сверхобобщение<br />
        <input type="checkbox" id="2" />Пессимизм<br />
        <input type="checkbox" id="3" />Обесценивание положительного<br />
        <input type="checkbox" id="4" />Поспешные выводы<br />
        <input
          type="checkbox"
          id="5"
        />Преувеличение/преуменьшение<br />
        <input type="checkbox" id="6" />Эмоциональное обоснование<br />
        <input type="checkbox" id="7" />Императивы<br />
        <input type="checkbox" id="8" />Ярлыки<br />
        <input type="checkbox" id="9" />Вина
      </div>
      <button id="question"></button>
      <label for="argument">Опровержение:</label>
      <textarea id="argument"></textarea>
      <label for="date">Дата:</label>
      <input type="date" id="date" style="margin-bottom: 20px;"/><br>
      <div id="end">
      <button>Добавить</button>
      <img id="mint" src="../assets/mint.png" />
    </div>
    </form>
  </center>
</template>
4

<script>
export default {
  name: "AddForm",
  props: [],
  methods: {
    clickBascket() {
      this.$emit("clickBascket");
    },
  },
};
</script>

<style scoped>
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
  margin-bottom: 20px;
  position: relative;
}

label {
  margin-left: 16px;
  font-size: 24px;
  vertical-align: top;
  margin-right: 16px;
}

textarea{
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

#end{
  display: inline;
}
</style>
