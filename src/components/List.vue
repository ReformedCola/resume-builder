<template>
  <ul>
    <li v-for="item in source" v-bind:key="item">
      <p class="item">
                <span class="left">
                    {{item.left}}
                    <br>
                    <a class="link" v-if="item.previewLink" :href="item.previewLink" target="_blank">Preview </a>
                    <a class="link" v-if="item.sourceLink" :href="item.sourceLink" target="_blank">| Source Code</a>
                </span>
        <span class="right">{{item.right}}</span>
      </p>
      <ul>
        <li v-for="childrenItem in item.children" v-bind:key="childrenItem">
          <p class="children-item">
            <span v-html="renderLeft(childrenItem.left)" class="left"></span>
            <span class="right">{{childrenItem.right}}</span>
          </p>
        </li>
      </ul>
      <p class="item">
        <span class="left">
          <span class="skillStack" v-if="item.skillStack">Skills: {{item.skillStack}}</span>
        </span>
      </p>
    </li>
  </ul>
</template>

<script>
  export default {
    name: 'Edu',
    props: {
      source: {
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
  .item, .children-item {
    display: flex;
    justify-content: space-between;
  }

  .item {
    margin-top: 3px;
    font-weight: bold;

    .link {
      color: #42b983;
      text-decoration: none;

      &:hover {
        text-decoration: underline;
      }
    }

    .skillStack {
      font-style: italic;
    }
  }

  .children-item {
    font-size: 0.9em;
  }
</style>
