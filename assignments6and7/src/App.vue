<template>
    <div class="container">
      <Header />
      <hr>
      <div class="row">
        <Server :onSelect="selectServer" :servers="servers"/>
        <ServerDetails :onRestart="restartServer" :server="activeServer"/>
      </div>
      <hr>
      <Footer />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Server from './components/Server.vue'
import ServerDetails from './components/ServerDetails.vue'
import Footer from './components/Footer.vue'

export default {
  data() {
    return {
      activeServer: null,
      servers: [
        {
          id: 1,
          status: 'Down',
        },
        {
          id: 2,
          status: 'Critical',
        },
        {
          id: 3,
          status: 'Normal',
        },
      ],
    }
  },
  methods: {
    selectServer(server) {
      this.activeServer = server
    },
    restartServer(id) {
      const mapped = this.servers.map(
        server => (server.id === id ? { ...server, status: 'Normal' } : server)
      )
      this.servers = mapped
      this.activeServer.status = 'Normal'
    },
  },
  components: {
    Header,
    Server,
    ServerDetails,
    Footer,
  },
}
</script>
