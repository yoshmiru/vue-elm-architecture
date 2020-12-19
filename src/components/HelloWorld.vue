<template>
  <div class="hello">
    <h1>{{ msg }}</h1>

    <div v-if="model.view.equals(DEFAULT_VIEW)">
      <h3>{{ model.view.i }}</h3>
      <button @click="update(COUNT_UP, model)">+</button>
    </div>

    <h2>Essential Links</h2>
    <ul>
      <li>
        <a
          href="https://guide.elm-lang.org/architecture/"
          target="_blank"
        >
          The Elm Architecture
        </a>
      </li>
      <li>
        <a
          href="https://vuejs.org"
          target="_blank"
        >
          Core Docs
        </a>
      </li>
      <li>
        <a
          href="https://forum.vuejs.org"
          target="_blank"
        >
          Forum
        </a>
      </li>
      <li>
        <a
          href="https://chat.vuejs.org"
          target="_blank"
        >
          Community Chat
        </a>
      </li>
      <li>
        <a
          href="https://twitter.com/vuejs"
          target="_blank"
        >
          Twitter
        </a>
      </li>
      <br>
      <li>
        <a
          href="http://vuejs-templates.github.io/webpack/"
          target="_blank"
        >
          Docs for This Template
        </a>
      </li>
    </ul>
    <h2>Ecosystem</h2>
    <ul>
      <li>
        <a
          href="http://router.vuejs.org/"
          target="_blank"
        >
          vue-router
        </a>
      </li>
      <li>
        <a
          href="http://vuex.vuejs.org/"
          target="_blank"
        >
          vuex
        </a>
      </li>
      <li>
        <a
          href="http://vue-loader.vuejs.org/"
          target="_blank"
        >
          vue-loader
        </a>
      </li>
      <li>
        <a
          href="https://github.com/vuejs/awesome-vue"
          target="_blank"
        >
          awesome-vue
        </a>
      </li>
    </ul>
  </div>
</template>

<script>

const VIEW = (view, obj) => {
  return { ...obj, equals (view_) { return view === view_ } }
}

const DEFAULT_VIEW = (i) => VIEW(DEFAULT_VIEW, {i})

const COUNT_UP = (i) => i + 1

export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App With Elm Architecture',
      // Msg
      COUNT_UP,
      // View
      DEFAULT_VIEW,
      model: {
        view: DEFAULT_VIEW(0)
      }
    }
  },
  methods: {
    update (msg, model) {
      if (msg === COUNT_UP) {
        model.view.i = COUNT_UP(model.view.i)
      } else {
        //
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
