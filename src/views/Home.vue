<template>
  <div class="home">
    <div class="actions">
        <div class="action" @click="readFile"> Dosyayı Oku</div>
        <div class="action" @click="writeFile"> Dosyayı Güncelle</div>
    </div>
    <div class="text">
      <textarea placeholder="içerik" v-model="desc"></textarea>
    </div>
  </div>
</template>

<script>
import { ipcRenderer } from 'electron'

export default {
  name: 'Home',
  data: function(){
    return{
      desc: ""
    }
  },
  methods:{
    readFile: function(){
      this.desc = ipcRenderer.sendSync('readFile')
    },
    writeFile: function(){
      let res = ipcRenderer.sendSync('writeFile', this.desc)
      res ? alert('dosya başarı ile kaydedildi') : alert('dosya yazma işlemi başarısız')
    }
  }
}
</script>
<style scoped>
  .actions{
    display: flex;
    flex-direction: row;
    justify-content: flex-end;
    background-color: #3d5a80;
  }
  .action{
    cursor: pointer;
    margin: .5rem;
    padding: .5rem;
    border: 1px solid #98c1d9; 
    color: #e0fbfc;
    border-radius:.5rem ;
  }
  .text{
    margin: 2rem;

  }
  textarea{
    width: 100%;
    height: 500px;
    background-color: #3d5a80;
    color: #e0fbfc;
  }
</style>