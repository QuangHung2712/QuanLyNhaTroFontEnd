<template>
  <v-row class="m0">
    <v-cols cols="2" class="bg-red-lighten-2 text-center">
      <h1>QUẢN LÝ NHÀ TRỌ</h1>
      <p>Xin chào: {{ NameLandlord }}</p>
      <p>Địa chỉ: {{ AddressTower }}</p>
    </v-cols>
  </v-row>
</template>
<script>
  export default {
    data(){
      return{
        AddressTower: 'số 11 ngõ 91 cầu diễn',
        NameLandlord: 'Phạm Quang Hưng'
      }
    }
  }
</script>
<style scoped>
.m0{
  margin: 0;
}
</style>