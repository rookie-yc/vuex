<template>
  <div>
    <!-- <h3>当前最新的count:{{$store.state.count}}</h3> -->
    <h3>{{showNum}}</h3>
    <button @click="btnHandler1">-1</button>
    <button @click="btnHandler2">-N</button>
    <button @click="btnHandler3">-1 Aysnc</button>
    <button @click="btnHandler4">-N Aysnc</button>
  </div>
</template>

<script>
import { mapState, mapMutations, mapActions, mapGetters } from 'vuex'
export default {
  data () {
    return {}
  },
  computed: {
    ...mapState(['count']),
    ...mapGetters(['showNum'])
  },
  methods: {
    ...mapMutations(['sub', 'subN']),
    ...mapActions(['subAsync', 'subNAsync']),
    btnHandler1() {
      this.sub()
    },
    btnHandler2() {
      this.subN(3)
    },
    btnHandler3() {
      this.subAsync()
    },
    btnHandler4() {
      this.subNAsync(4)
    }
  }
}
</script>
