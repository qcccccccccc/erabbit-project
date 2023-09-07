<template>
<!-- 1.使用根模块state的数据 -->
  <p>{{ $store.state.username }}</p>
  <!--2. 使用根模块getters的数据 -->
  <!-- <p>{{ $store.getters.newName }}</p> -->
  <p>{{ $store.getters['newName'] }}</p>
  <button @click="mutationsFn">改变名字</button>
</template>
<script>
import { useStore } from 'vuex'
export default {
  name: 'App',
  setup () {
    // <!-- 1.使用根模块state的数据 -->
    const store = useStore()
    console.log(store.state.username)
    // 2.使用根模块getters的数据
    console.log(store.getters.newName)
    // 3.提交根模块mutation的数据
    // const changeName = () => {
    //   store.commit('updateName')
    // }
    // 4.调用根模块action函数
    const mutationsFn = () => {
      store.dispatch('updateName')
    }
    return { mutationsFn }
    // return { changeName }
  }
}
</script>
<style lang="less">
</style>
