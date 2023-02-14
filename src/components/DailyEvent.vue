<template>
  <div class="daily-event">
    <h3 class="daily-event-title">bizim günlük aktivitemiz</h3>
    <button class="daily-event-random-button" @click="randomEvent">
      Çevir gelsin
    </button>
    <h1 v-show="resultVisible" class="daily-event-result">
      {{ dailyEventResult }}
    </h1>
  </div>
</template>

<script>
export default {
  name: "DailyEvent",
  props: {
    msg: String,
  },
  data() {
    return {
      resultVisible: false,
      dailyEventResult: "",
      eventKeyValue: null,
      eventList: [
        "Kitap Okuma",
        "Sohbet Etme",
        "Yeni bir şeyler öğrenme",
        "Kısa bir proje yapımı",
        "Kısa bir diziye başlama",
        "Film izleme",
        "Kur-an'ı Kerim Öğrenme",
        "Apo istenilen konuyu anlatacak:D",
        "Beraber Message-App uygulamasına bakacağız",
        "Apo ne isterse o",
        "Meryem ne isterse o",
        "İngilizce çalışma.",
        "Hackerrank algoritma çalışma",
        "Codepen çalışma yapma. ",
        "Git kullanımı",
        "Socketıo",
        "Vuex",
      ],
    };
  },
  methods: {
    randomEvent() {
      this.eventKeyValue = Math.floor(Math.random() * this.eventList.length);
      this.resultVisible = true;
      this.dailyEventResult = this.eventList[this.eventKeyValue];
    },
  },
};
</script>
<style lang="scss">
@import "../assets/daily-event";
</style>
