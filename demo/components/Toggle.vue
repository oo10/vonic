<template>
  <div class="page has-navbar" v-nav="{title: '开关按钮', showBackButton: true}">
    <div class="page-content padding-top">
      <von-toggle :text="toggleText" :value.sync="pushNotification"></von-toggle>
      <div class="item item-divider">开关状态: <span>{{ pushNotification ? '开启' : '关闭' }}</span></div>

      <div class="item">其他主题色</div>
      <von-toggle text="assertive" theme="assertive" :value="true"></von-toggle>
      <von-toggle text="positive" theme="positive" :value="true"></von-toggle>
      <von-toggle text="energized" theme="energized" :value="true"></von-toggle>
      <von-toggle text="calm" theme="calm" :value="true"></von-toggle>
      <von-toggle text="dark" theme="dark" :value="true"></von-toggle>
    </div>

  </div>
</template>
<style lang="scss" scoped>

</style>
<script>
  import _ from 'lodash'
  import {VonToggle} from 'vonic'

  export default{
    components: {
      VonToggle
    },

    data(){
      return {
        toggleText: "是否开启推送",
        pushNotification: true
      }
    },

    methods: {
      back() {
        $router.back({path: '/'})
      }
    }
  }
</script>
