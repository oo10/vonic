<template>
  <div class="list von-radio">
    <label class="item item-icon-left"
           v-for="(index, option) in options">
      <input type="radio" name="{{ radioId }}" @click="onOptionClick(index)">
      <i class="icon"
         :class="{'ion-ios-circle-outline': value!=index, 'ion-ios-checkmark assertive': value==index}"></i>
      <span>{{ option }}</span>
    </label>
  </div>
</template>
<style lang="scss" scoped>
  .von-radio {
    .item {
      padding: 15px 15px 15px 50px;
      font-size: 14px;
      line-height: 20px;
    }

    .item-icon-left {
      .icon {
        font-size: 28px;
        left: 10px;
      }
    }

    .ion-ios-circle-outline {
      color: #ccc;
    }

    input[type=radio] {
      position: absolute;
      top: -50000px;
      left: -50000px;
    }
  }
</style>
<script>

  export default{
    props: {
      options: {
        type: Array,
        required: true
      },

      value: {
        type: Number,
        required: true
      },
    },

    data() {
      return {
        radioId: 'von-radio-' + Math.random().toString(36).substring(3, 8)
      }
    },

    methods: {
      onOptionClick($index) {
        this.value = $index
      }
    }
  }
</script>
