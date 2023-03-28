<template>
  <ul>
    <li v-for="item in skills" :key="item">
      <p class="item">
        <span v-html="renderLeft(item.left)" class="left">
          {{item}}
        </span>
      </p>
    </li>
  </ul>
</template>

<script>
  export default {
    name: 'Skills',
    props: {
      skills: {
        type: Array,
        required: true
      }
    },
    methods: {
      renderLeft(left) {
        return left.replace(/\*([\w.\s&()/,-]+)\*/g, '<strong>$1</strong>')
      }
    }
  }
</script>

<style scoped lang="scss">
  .item{
    display: flex;
    justify-content: space-between;
    margin-top: 3px;
  }
</style>
