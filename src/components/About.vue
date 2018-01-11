<template>
  <div id="example">
    <div class="panel panel-default">
      <div class="panel-heading">About</div>
      <div class="panel-body">About 화면입니다</div>
      <div>
        <button @click="changeVisible">보여주기 버튼 토글</button>
      </div>
      <div class="box">
        <img src="../assets/hill.jpg" v-if="visible" alt="언덕"/>
      </div>
      <button @click="changeVisible2">보여주기 버튼 토글2</button>
      <div class="box">
        <img src="../assets/hill.jpg" v-show="visible2" alt="언덕"/>
      </div>
      <div class="box" id="id1">
        <button @click="getvalue">값 가져오기</button>
        <input type="text" name="idinput" v-model="idinput" value="">
      </div>
      <div class="box">
        {{message}}
      </div>
    </div>
  </div>
</template>

<script>
  export default {
     name : 'about',
     data : function() {
        return { 
          message : '',
          idinput : '1111',
          visible : true,
          visible2 : true
        }
     },
     methods : {
        getvalue : function() {
          console.log(this.idinput);
          this.message = this.idinput
        },
        changeVisible : function() {
            this.visible = !this.visible
        },
        changeVisible2 : function() {
            this.visible2 = !this.visible2
        }
    }
  }

</script>

<style>
 .box { margin:10px; }
 #example { margin:10px auto; max-width: 820px; min-width: 820px;
    padding:0px; position:relative; font: 13px "verdana"; }
</style>