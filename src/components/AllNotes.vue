<template>
  <center>
    <form id="allNotesForm">
      <h3>Предыдущие записи</h3>
      <img src="../assets/basil.png" id="basil" />
      <div id="notes" v-if="getNotes">
        <div id="note" v-for="note in getNotes.reverse()" :key="note.thought">
          {{ note.date.slice(8, 10)+'.' + note.date.slice(5, 7)+'.' + note.date.slice(0, 4) }} <br />
          Мысль: {{ note.thought }}
          <div v-if="note.mistakes.length != 0">
            Ошибка мышления: {{ note.mistakes }}
          </div>
          <div v-else>Ошибка мышления: не выбрано</div>
          Опровержение: {{ note.argument }}
          <hr
            style="margin-left: -12px; border-top: dashed 2px; color: #a1d9b7"
          />
        </div>
      </div>
      <img src="../assets/clover.png" id="clover" />
    </form>
  </center>
</template>

<script>
import vuecookies from "vue-cookies";

export default {
  name: "AllNotes",
  data() {
    return {
      notes: [],
    };
  },
  computed: {
    getNotes() {
      if (vuecookies.get("allNotes")) {
        return [...vuecookies.get("allNotes")];
      } else {
        return [];
      }
    },
  },
};
</script>

<style scoped>
#notes {
  padding-bottom: 30px;
}

#note {
  margin-left: 12px;
  font-size: 24px;
}

h3 {
  margin-bottom: 0;
}

#allNotesForm #basil {
  position: relative;
  top: -20px;
  width: 53px;
}
#allNotesForm #clover {
  position: relative;
  width: 53px;
  bottom: 0;
  left: 265px;
}
</style>
