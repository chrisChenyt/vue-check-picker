<template>
  <div id="app" class="main-wrapper">
    <textarea v-model="value"></textarea>
    <p class="btn" @click="showPicker0">多列</p>
    <awesome-picker
      ref="picker0"
      :textTitle="picker0.textTitle"
      :data="picker0.data"
      :anchor="picker0.anchor"
      @confirm="handlePicker0Confirm">
    </awesome-picker>
  </div>
</template>

<script>
import areaData from './area.js'

const data1 = ['2015', '2016', '2017', '2018', '2019', '2020']
const data2 = ['1', '2', '3', '4', '5', '6', '7', '8', '9', '10', '11', '12']

export default {
  name: 'app',
  data () {
    return {
      value: null,
      picker0: {
        anchor: [],
        textTitle: '多列选择器',
        data: [data1, data2]
      },
    }
  },
  methods: {
    showPicker0 () {
      this.$refs.picker0.show()
    },
    handlePicker0Confirm (v) {
      this.picker0.anchor = v
      this.value = v ? JSON.stringify(v) : null
    }
  }
}
</script>

<style lang="scss">
  .main-wrapper {
    padding: 24px;
  }

  textarea {
    height: 176px;
    width: 100%;
    margin-bottom:24px;
    padding: 24px;
    border: 4px solid #35495d;
    border-radius: 8px;
    box-sizing: border-box;
    outline: none;
    color: #35495d;
    font-size: 28px;
    resize: none;
  }

  .btn {
    width: 100%;
    height: 88px;
    margin-bottom: 24px;
    line-height: 88px;
    text-align: center;
    color: #fff;
    background: #42b983;
  }
</style>
