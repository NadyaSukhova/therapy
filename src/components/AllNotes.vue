<template>
  <center>
    <form id="allNotesForm">
      <h3>Предыдущие записи</h3>
      <img src="../assets/basil.png" id="basil">
      <div id="notes">
        <div id="note" v-for="note in notes" :key="note.thought">
          {{ note.date }} <br>
          Мысль: {{ note.thought }}<br>
          Ошибка мышления: {{ note.mistakes }}<br>
          Опровержение: {{ note.argument }}<hr style="margin-left: -12px; border-top: dashed 2px; color:#A1D9B7;">
        </div>
      </div>
      <img src="../assets/clover.png" id="clover">
    </form>
  </center>
</template>

<script>
export default {
  name: "AllNotes",
  data() {
    return {
      notes: [{
          date: "2023-10-21",
          thought: "Нельзя не работать",
          mistakes: "Императивы",
          argument: "Отдых нужен всем",
        },{
          date: "2023-10-21",
          thought: "Нельзя не работать",
          mistakes: "Императивы",
          argument: "Отдых нужен всем",
        },
        {
          date: "2023-10-21",
          thought: "Нельзя не работать",
          mistakes: "Императивы",
          argument: "Отдых нужен всем",
        },
      ],
    };
  },
  
};
</script>

<style scoped>
#notes{
  padding-bottom: 30px;
}

#note{
  margin-left: 12px;
  font-size: 24px;
}

h3{
  margin-bottom: 0;
}

#allNotesForm #basil {
position:relative;
top: -20px;
width: 53px;
}
#allNotesForm #clover {
position:relative;
width: 53px;
bottom: 0;
left: 265px;
}
</style>
