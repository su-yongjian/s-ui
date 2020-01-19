<template>
  <button
    @click="handleClick"
    class="s-button"
    :class="[ `s-button--${type}`, { 'is-plain': plain,'is-circle': circle,'is-disabled': disabled}]"
  >
    <i :class="icon" v-if="icon"></i>
    <!-- 如果没有传入插槽的时候才显示 -->
    <span v-if="$slots.default">
      <slot></slot>
    </span>
  </button>
</template>
<style lang="scss" scoped>
.s-button {
  box-sizing: border-box;
  outline: none;
  margin: 0;
  transition: 0.1s;
  font-weight: 500;
  -moz-user-select: none;
  -webkit-user-select: none;
  -ms-user-select: none;
  padding: 5px 15px 6px;
  font-size: 12px;
  border-radius: 4px;
  cursor: pointer;
  &.is-plain:hover,
  &.is-plain:focus {
    background: #fff;
    border-color: #409eff;
    color: #409eff;
  }
  &.is-round {
    border-radius: 20px;
    padding: 12px 23px;
  }
}
.s-button--default{
  border: 1px solid #dddddd
}
.s-button--primary {
    color: #fff;
    background-color: #2d8cf0;
    border-color: #2d8cf0;
}
.s-button--success {
    color: #fff;
    background-color: #19be6b;
    border-color: #19be6b;
}
.s-button--warning {
    color: #fff;
    background-color: #f90;
    border-color: #f90;
}
.s-button--danger {
    color: #fff;
    background-color: #ed4014;
    border-color: #ed4014;
}
.s-button--info {
    color: #fff;
    background-color: #2db7f5;
    border-color: #2db7f5;
}
.s-button--text {
    color: #333;
    background-color: #ffffff;
    border-color: #ffffff;
}
</style>
<script>
export default {
  name: 'SButtom',
  components: {},
  props: {
    type: {
      type: String, // primary / success / warning / danger / info / text
      default: 'default'
    },
    plain: {
      type: Boolean,
      default: false
    },
    circle: {
      type: Boolean,
      default: false
    },
    disabled: {
      type: Boolean,
      default: false
    },
    icon: {
      type: String,
      default: ''
    }
  },
  data () {
    return {}
  },
  methods: {
    handleClick (e) {
      this.$emit('click', e) // 向父组件派发一个click事件，e表示携带的参数
    }
  }
}
</script>
