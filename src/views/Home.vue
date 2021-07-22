<template>
  <div class="home">
    <div class="actions">
        <div class="action"> Dosyayı Oku</div>
        <div class="action"> Dosyayı Güncelle</div>
    </div>
    <div class="text">
      <textarea placeholder="içerik"></textarea>
    </div>
  </div>
</template>

<script>

export default {
  name: 'Home',
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