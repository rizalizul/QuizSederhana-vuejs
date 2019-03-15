<template>

  <div class="hello">
  <center>
  <div v-if="show">
  <h1>Quiz Tidak Berhadiah</h1>
	
  <table>
		<hr>
    <div v-for="soall in soal1" v-bind:key="soall.soal1">
      <tr>
        <td><b>{{ soall.no }}.</b> {{ soall.soal }}</td>
      </tr>
      <tr>
				<div class="control">
					<td>
						<input type="radio" name="soal1" value="a" v-model="picked1">{{soall.jwbn_a}}
						<input type="radio" name="soal1" value="b" v-model="picked1">{{soall.jwbn_b}}
						<input type="radio" name="soal1" value="c" v-model="picked1">{{soall.jwbn_c}}
						<input type="radio" name="soal1" value="d" v-model="picked1">{{soall.jwbn_d}}
						<input type="radio" name="soal1" value="e" v-model="picked1">{{soall.jwbn_e}}
					</td>
				</div>
      </tr><br>
    </div><br>
    <div v-for="soall in soal2" v-bind:key="soall.soal2">
      <tr>
				<td><b>{{ soall.no }}.</b> {{ soall.soal }}</td>
      </tr>
      <tr>
				<div class="control">
					<td>
						<input type="radio" name="soal2" value="a" v-model="picked2">{{soall.jwbn_a}}
						<input type="radio" name="soal2" value="b" v-model="picked2">{{soall.jwbn_b}}
						<input type="radio" name="soal2" value="c" v-model="picked2">{{soall.jwbn_c}}
						<input type="radio" name="soal2" value="d" v-model="picked2">{{soall.jwbn_d}}
						<input type="radio" name="soal2" value="e" v-model="picked2">{{soall.jwbn_e}}
					</td>
				</div>
      </tr><br><br>
    </div>
    <div v-for="soall in soal3" v-bind:key="soall.soal3">
      <tr>
				<td><b>{{ soall.no }}.</b> {{ soall.soal }}</td>
      </tr>
      <tr>
				<div class="control">
					<td>
						<input type="radio" name="soal3" value="a" v-model="picked3">{{soall.jwbn_a}}
						<input type="radio" name="soal3" value="b" v-model="picked3">{{soall.jwbn_b}}
						<input type="radio" name="soal3" value="c" v-model="picked3">{{soall.jwbn_c}}
						<input type="radio" name="soal3" value="d" v-model="picked3">{{soall.jwbn_d}}
						<input type="radio" name="soal3" value="e" v-model="picked3">{{soall.jwbn_e}}
					</td>
				</div>
      </tr><br><br>
    </div>
     <div v-for="soall in soal4" v-bind:key="soall.soal4">
      <tr>
				<td><b>{{ soall.no }}.</b> {{ soall.soal }}</td>
      </tr>
      <tr>
				<div class="control">
					<td>
						<input type="radio" name="soal4" value="a" v-model="picked4">{{soall.jwbn_a}}
						<input type="radio" name="soal4" value="b" v-model="picked4">{{soall.jwbn_b}}
						<input type="radio" name="soal4" value="c" v-model="picked4">{{soall.jwbn_c}}
						<input type="radio" name="soal4" value="d" v-model="picked4">{{soall.jwbn_d}}
						<input type="radio" name="soal4" value="e" v-model="picked4">{{soall.jwbn_e}}
					</td>
				</div>
      </tr><br><br>
    </div>
    <div v-for="soall in soal5" v-bind:key="soall.soal5">
      <tr>
				<td><b>{{ soall.no }}.</b> {{ soall.soal }}</td>
      </tr>
      <tr>
				<div class="control">
					<td>
						<input type="radio" name="soal5" value="a" v-model="picked5">{{soall.jwbn_a}}
						<input type="radio" name="soal5" value="b" v-model="picked5">{{soall.jwbn_b}}
						<input type="radio" name="soal5" value="c" v-model="picked5">{{soall.jwbn_c}}
						<input type="radio" name="soal5" value="d" v-model="picked5">{{soall.jwbn_d}}
						<input type="radio" name="soal5" value="e" v-model="picked5">{{soall.jwbn_e}}
					</td>
				</div>
      </tr><br><hr>
    </div>
		<tr>
			<td style="text-align:center;">
				<button type="button" v-on:click="hideTitle">Submit Jawaban</button>
				</td>
		</tr>
		
  </table>

  </div>

  <div v-else>
		<h1>Selesai Mengerjakan !! <br></h1>
		<h1>Nilai: {{ nilai() }}</h1>
		<h2>Jumlah benar : {{jumlah_benar() }}</h2>
		<h2>Jumlah salah : {{jumlah_salah() }}</h2>

		<button type="button" v-on:click="hideTitle">Coba Lagi ?</button>
	</div>
	</center>
  </div>
</template>

<script>
export default {
  data () {
    return {
      show:true,
      picked1:'',picked2:'',picked3:'',picked4:'',picked5:'',
      soal1:[
      {
        no:'1',
        soal:"Siapa Presiden Indonesia Pertama...",
        jwbn_a:" Manusia",
        jwbn_b:" Jokowi",
        jwbn_c:" Soekarno",
        jwbn_d:" Megawati",
        jwbn_e:" Prabowo"
      }
      ],
      soal2:[
      {
        no:'2',
        soal:"Tahun Berapakah Sekarang...",
        jwbn_a:" 2000",
        jwbn_b:" 1998",
        jwbn_c:" 2018",
        jwbn_d:" 2019",
        jwbn_e:" 2019 SM"
      }
    ],
      soal3:[
      {
        no:'3',
        soal:"1 x 1 = ...",
        jwbn_a:" 5",
        jwbn_b:" 4",
        jwbn_c:" 3",
        jwbn_d:" 2",
        jwbn_e:" 1"
      }
    ],
      soal4:[
      {
        no:'4',
        soal:"5 + 10 * 4 = ...",
        jwbn_a:" 45",
        jwbn_b:" 50",
        jwbn_c:" 60",
        jwbn_d:" 40",
        jwbn_e:" 35"
      }
    ],
      soal5:[
      {
        no:'5',
        soal:"Perusahaan Unicorn di Indonesia adalah, kecuali ...",
        jwbn_a:" Go-Jek",
        jwbn_b:" Traveloka",
        jwbn_c:" Bukalapak",
        jwbn_d:" Tokopedia",
        jwbn_e:" Chamilan"
      }
    ]
    }
  },
  methods: {
    nilai: function(){
      var jwbn_1, jwbn_2, jwbn_3, jwbn_4, jwbn_5;

      if(this.picked1 == 'c'){ jwbn_1 = 20; }else{ jwbn_1 = 0;}
      if(this.picked2 == 'd'){ jwbn_2 = 20; }else{ jwbn_2 = 0;}
      if(this.picked3 == 'e'){ jwbn_3 = 20; }else{ jwbn_3 = 0;}
      if(this.picked4 == 'a'){ jwbn_4 = 20; }else{ jwbn_4 = 0;}
      if(this.picked5 == 'e'){ jwbn_5 = 20; }else{ jwbn_5 = 0;}

      return jwbn_1 + jwbn_2 + jwbn_3 + jwbn_4 + jwbn_5;

    },
    jumlah_benar: function(){
      return this.nilai() / 20;
    },
    jumlah_salah: function(){
      return 5 - this.jumlah_benar() ;
    },
    hideTitle(){
      this.show = !this.show
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
input {
	margin-left: 20px;	
}
</style>
