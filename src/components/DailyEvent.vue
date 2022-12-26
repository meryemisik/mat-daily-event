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
        {
          eventKey: 0,
          eventValue: "Kitap Okuma",
        },
        {
          eventKey: 1,
          eventValue: "Sohbet Etme",
        },
        {
          eventKey: 2,
          eventValue: "Yeni bir şeyler öğrenme",
        },
        {
          eventKey: 3,
          eventValue: "Kısa bir proje yapımı",
        },
        {
          eventKey: 4,
          eventValue: "Kısa bir diziye başlama",
        },
        {
          eventKey: 5,
          eventValue: "Film izleme",
        },
        {
          eventKey: 6,
          eventValue: "Kur-an'ı Kerim Öğrenme",
        },
        {
          eventKey: 7,
          eventValue: "Apo istenilen konuyu anlatacak:D",
        },
        {
          eventKey: 8,
          eventValue: "Beraber Message-App uygulamasına bakacağız",
        },
        {
          eventKey: 9,
          eventValue: "Apo ne isterse o",
        },
        {
          eventKey: 10,
          eventValue: "Meryem ne isterse o",
        },
      ],
    };
  },
  methods: {
    randomEvent() {
      this.eventKeyValue = Math.floor(Math.random() * this.eventList.length);
      this.resultVisible = true;
      this.dailyEventResult = this.eventList[this.eventKeyValue].eventValue;
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
@import "../assets/daily-event";
</style>
