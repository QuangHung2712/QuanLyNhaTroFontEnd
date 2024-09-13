<template>
<v-main>
  <v-row class="m0 header d-flex">
    <v-col cols="4" >
      <button class="text-left text-header">QUẢN LÝ NHÀ TRỌ</button>
    </v-col>
    <v-col cols="4">
      <v-row v-show="!AddressTower" class="m0 d-flex align-center">
        <v-col cols="3" class="p0 mb-5 title-address">
          Địa chỉ: 
        </v-col>
        <v-col cols="9" class="p0">
          <v-select 
          v-model="selectTower"
          :items="AddressTower"
          item-title="title"
          item-value="value"></v-select>
        </v-col>
      </v-row>
    </v-col>
    <v-col cols="4" class="text-right p0 "><p>Xin chào: {{ NameLandlord }}</p></v-col>
  </v-row>
  <v-row class="m0">
    <v-col cols="2" class="menu">
      <button @click="diglog = 0" class="menuitem">
        <span>Trang chủ</span>
      </button>
      <button @click="diglog = 1" class="menuitem">
        <v-icon icon="mdi-home" />
        <span>Phòng</span>
      </button>
      <button class="menuitem">
        <span>Dịch vụ</span>
      </button>
      <button class="menuitem">
        <v-icon icon="mdi-flash"></v-icon>
        <span>Số điện</span>
      </button>
      <button class="menuitem">
        <v-icon icon="mdi-water"></v-icon>
        <span>Số nước</span>
      </button>
      <button class="menuitem">
        <span>Hợp đồng</span>
      </button>
      <button class="menuitem">
        <v-icon icon="mdi-cash"></v-icon>
        <span>Phát sinh</span>
      </button>
      <button class="menuitem">
        <v-icon icon="mdi-chart-line"></v-icon>
        <span>Báo cáo</span>
      </button>
    </v-col>
    <home-page-view v-show="diglog==0"></home-page-view>
    <RoomView v-show="diglog==1"></RoomView>
  </v-row>
</v-main>
</template>
<script>
import HomePageView from '../../components/HomePageView.vue'
import RoomView from '@/components/RoomView.vue';
  export default {
  components: { HomePageView,RoomView },
    data(){
      return{
        AddressTower:[
          {title: "Số 11 ngõ 91 Cầu Diễn", value: 0},
          {title:"Trâu Quỳ Gia Lâm", value:1}
        ],
        selectTower:0,
        NameLandlord: 'Phạm Quang Hưng',
        diglog: 0
      }
    },
    methods: {

    }
  }
</script>
<style scoped>
.m0{
  margin: 0;
}
.p0{
  padding: 0;
}
button{
  width: 100%;
  text-align: left;
}
.header{
  background-color: #fed9c2;
  height: 12vh;
}
.menu{
  background-color: #fed9c2;
  height: 88vh;
  display: flex;
  flex-direction: column;
  padding-left: 30px;
}
.menu .menuitem{
  display: flex;
  align-items: center;
  font-size: 120%;
  flex: 1;
}
.menu .menuitem span{
  margin-left: 5px;
  margin-top: 5px;
}
.text-header{
  font-size: 200%;
  margin-left: 20px;
}
.title-address{
  font-size: 130%;
}
</style>