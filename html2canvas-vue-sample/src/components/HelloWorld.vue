<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h2>Essential Links</h2>
    <br><br><br>
    img test
    <br><br><br>
    <div class="save_btn">
      <button href='javascript:void(0);' @click="PrintDiv();">이미지로 저장</button>
    </div>
시작
<div class="card card-default pb-5">
  <div id="bar_chart2" >
    <div class="card-header justify-content-center">
    	<h2 class="text-center">회사명</h2>
    </div>
    이름 직급 / 부서명<br>
  </div>
</div>
끝
<br><br><br><br>

시작
<img id="canvas_div" src="">
끝


  </div>
</template>

<script>
import html2canvas from 'html2canvas'

export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  methods: {
    PrintDiv() {
      
      let div = document.getElementById('bar_chart2')
      console.log('called printDiv' + div);

      html2canvas(div).then(function(canvas){
        var myImage = canvas.toDataURL();
        console.log(myImage);
        document.getElementById("canvas_div").src = myImage;

        
        console.log('222222222');
        console.log('222222222');
        console.log('222222222');
        downloadURI(myImage, "저장이미지이름.png") 
      });      
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
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
