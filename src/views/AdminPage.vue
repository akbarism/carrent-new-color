<template>
  <div class="adminPageWrap">
    <div class="adminPage">
      <div @click="modulRequest" class="request">
        <h5>Request</h5>
      </div>
      <div @click="modulRent" class="rentaler">
        <h5>Rentaler</h5>
      </div>
      <div @click="modulAlluser" class="allUser">
        <h5>All User</h5>
      </div>
    </div>
    <CardRequest />
    <CardRent />
    <Alluser />
  </div>
</template>

<script>
import CardRequest from '../components/base_/CardRequest.vue'
import CardRent from '../components/base_/CardRent.vue'
import Alluser from '../components/base_/Alluser.vue'

export default {
  name: 'AdminPage',
  components: {
    CardRequest,
    CardRent,
    Alluser
  },
  methods: {
    modulRequest () {
      document.querySelector('.cardRentWrap').classList.remove('cardRentActive')
      document.querySelector('.allUserWrap').classList.remove('allUserActive')
      document.querySelector('.allUser').classList.remove('on')
      document.querySelector('.rentaler').classList.remove('on')
      document.querySelector('.request').classList.add('on')
      document.querySelector('.cardRequestWrap').classList.add('cardRequestActive')
    },
    modulRent () {
      document.querySelector('.allUserWrap').classList.remove('allUserActive')
      document.querySelector('.cardRequestWrap').classList.remove('cardRequestActive')
      document.querySelector('.request').classList.remove('on')
      document.querySelector('.allUser').classList.remove('on')
      document.querySelector('.rentaler').classList.add('on')
      document.querySelector('.cardRentWrap').classList.add('cardRentActive')
    },
    modulAlluser () {
      document.querySelector('.cardRequestWrap').classList.remove('cardRequestActive')
      document.querySelector('.cardRentWrap').classList.remove('cardRentActive')
      document.querySelector('.request').classList.remove('on')
      document.querySelector('.rentaler').classList.remove('on')
      document.querySelector('.allUser').classList.add('on')
      document.querySelector('.allUserWrap').classList.add('allUserActive')
    }
  },
  created () {
    if (localStorage.role_id === '0') this.$router.push('/')
  }
}
</script>

<style lang="scss" scoped>
.on {
  background-color: rgba(0, 0, 0, 0.055);
}
.adminPageWrap{
  background-color: rgba(0, 0, 0, 0.055);
  width: 100%;
  height: 3000px;
  display: flex;

  .adminPage{
    width: 100%;
    height: 50px;
    margin-top: 70px;
    background-color: rgba(255, 255, 255, 0.904);
    display: flex;
    cursor: pointer;
    .request{
      width: 33.33%;
      height: 100%;
      position: relative;
      display: flex;
      justify-content: center;
      align-items: center;
      border-right: 1px solid rgba(0, 0, 0, 0.199);
      border-bottom: 1px solid rgba(0, 0, 0, 0.199);
    }
    .rentaler{
      width: 33.33%;
      height: 100%;
      // background-color: brown;
      display: flex;
      justify-content: center;
      align-items: center;
      border-right: 1px solid rgba(0, 0, 0, 0.199);
      border-bottom: 1px solid rgba(0, 0, 0, 0.199);
    }
    .allUser{
      width: 33.33%;
      height: 100%;
      // background-color: cadetblue;
      display: flex;
      justify-content: center;
      align-items: center;
      border-bottom: 1px solid rgba(0, 0, 0, 0.199);
    }
  }
}

</style>
