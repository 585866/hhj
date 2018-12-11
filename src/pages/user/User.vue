<template>
  <div>
    <UserHeader></UserHeader>
    <UserMoney></UserMoney>
    <UserList></UserList>
  </div>
</template>

<script>
  import UserHeader from '../user/components/Header'
  import UserMoney from '../user/components/Money'
  import UserList from '../user/components/List'
    export default {
        name: "UserHome",
      components:{
          UserHeader,
          UserMoney,
          UserList
      }
    }
</script>

<style lang="stylus" scoped>
</style>
