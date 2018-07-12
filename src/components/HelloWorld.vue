<template>
  <div class="hello">
    <div id="swagger-ui"></div>
  </div>
</template>

<script>

import SwaggerUIBundle from 'swagger-ui'
import 'swagger-ui/dist/swagger-ui.css'

export default {
  name: 'console',
  data () {
    return {
      error: false
    }
  },
  created () {

  },
  mounted () {
    this.dispatchSwagger()
  },
  methods: {
    dispatchSwagger () {
      SwaggerUIBundle({
        url: 'https://petstore.swagger.io/v2/swagger.json',
        dom_id: '#swagger-ui',
        deepLinking: false,
        presets: [
          SwaggerUIBundle.presets.apis,
          SwaggerUIBundle.SwaggerUIStandalonePreset
        ],
        plugins: [
          SwaggerUIBundle.plugins.DownloadUrl
        ]
      })
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
#swagger-ui {
  text-align: left
}
</style>
