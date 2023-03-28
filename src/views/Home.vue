<template>
  <div>
    <div class="info">
      <h1 class="name">{{name}}</h1>
      <p>
        {{address}}
      </p>
      <p>
        Tel: <a href="tel:+1(415)608-3052">{{tel}}</a>
        <span class="email">E-mail: <a href="mailto:zhiyuanfw@gmail.com">{{email}}</a></span>
      </p>
      <p class="github">
        Github: <a :href="github">{{github}}</a>
      </p>
      <p class="website">
        Personal Website: <a :href="website">{{website}}</a>
      </p>
      <p class="linkedin">
        LinkedIn: <a :href="linkedin">{{linkedin}}</a>
      </p>
      <p class="area">
        <span class="auth">{{auth}}</span>
      </p>
    </div>

    <div class="projects">
      <h4>Work Experience</h4>
      <hr>
      <List :source="experience"></List>
    </div>

    <div class="skills">
      <h4>SKILLS</h4>
      <hr>
      <Skills :skills="skills"></Skills>
    </div>

    <div class="projects">
      <h4>PROJECTS</h4>
      <hr>
      <List :source="projects"></List>
    </div>

    <div class="edu">
      <h4>EDUCATION</h4>
      <hr>
      <List :source="edus"></List>
    </div>

  </div>
</template>

<script>
  import List from '../components/List'
  import Skills from '../components/Skills'
  import info from '../assets/info'

  export default {
    name: 'Home',
    data() {
      return info
    },
    components: {
      List,
      Skills,
    }
  }
</script>

<style scoped lang="scss">
  .info {
    .name {
      text-align: center;
    }

    p {
      text-align: center;
    }

    .email {
      margin-left: 10px;
    }

    .auth {
      margin-left: 10px;
    }
  }

  a {
    color: #42b983;
    text-decoration: none;
  }

  .projects, .skills, .edu {
    margin-top: 8px;
  }
</style>
