<template>
  <div class="hello">
    <h1 v-if="show">{{ msg }}</h1>
    <div v-for="(question, index) in quiz.questions" v-bind:key="question.id">
      <div v-show="index === questionIndex">
        <h4>{{ question.text }}</h4>
        <ol>
          <li v-for="respon in question.respons" v-bind:key="respon.id">
            <label>
              <input type="radio"
                     v-bind:value="respon.pilihan"
                     v-bind:name="index"
                     v-model="picked"> {{ respon.text }}
            </label>
          </li>
        </ol>
        <button v-on:click="check(question.benar, picked)">
          <span v-if="questionIndex == quiz.questions.length - 1">Selesai</span>
          <span v-else>Selanjutnya</span>
        </button>
        <h5>Benar: {{ totalbenar }}</h5>
      </div>
    </div>
    <div v-show="questionIndex == quiz.questions.length">
      <h2>Kuis Selesai</h2>
      <p>Benar: {{ totalbenar }} / {{ quiz.questions.length }}</p>
      <p>Nilai: {{ scoreCal() }}</p>
    </div>
  </div>
</template>

<script>
var quiz = {
    questions: [
      {
        text: "1. Siapa Presiden Indonesia Pertama...",
        respons: [
          { text: 'Soekarno', pilihan: 'A' },
          { text: 'Joko Widodo', pilihan: 'B' },
          { text: 'Manusia', pilihan: 'C' }
        ],
        benar: 'A'
      }, 
      {
        text: "2. Tahun Berapakah Sekarang...",
        respons: [
          { text: '2000', pilihan: 'A' },
          { text: '2019 SM', pilihan: 'B' },
          { text: '2019', pilihan: 'C' }
        ],
        benar: 'C'
      }, 
      {
        text: "3. 1 x 1 = ",
        respons: [
          { text: '2', pilihan: 'A' },
          { text: '1', pilihan: 'B' },
          { text: '3', pilihan: 'C' }
        ],
        benar: 'B'
      }, 
      {
        text: "4. 5 + 10 * 4 = ",
        respons: [
          { text: '50', pilihan: 'A' },
          { text: '60', pilihan: 'B' },
          { text: '45', pilihan: 'C' }
        ],
        benar: 'C'
      }
    ]
  };
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data: function() {
    return {
      picked: '',
      show: true,
      quiz: quiz,
      questionIndex: 0,
      totalbenar: 0,
      userrespons: Array(quiz.questions.length).fill(false)
    }
  },
  methods: {
    check(benar, picked) {
      if (benar === picked) this.totalbenar++;
      this.questionIndex++;
    },
    scoreCal: function() {
      return (100 / quiz.questions.length) * this.totalbenar;
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
