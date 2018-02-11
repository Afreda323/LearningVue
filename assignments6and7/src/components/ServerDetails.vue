<template>
  <div class="col-xs-12 col-sm-6">
    <p v-if="!server">Server Details are currently not updated</p>
    <template v-if="server">
      Server Number: {{server.id}}
      <br />
      Server Status: 
      <span 
        :class="server.status === 'Normal' 
          ? 'text-success' 
          : 'text-danger'"
      >
        {{server.status}}
      </span>
      <br />
      <br />
      <button 
        v-if="server.status !== 'Normal'"
        class="btn btn-primary"
        @click="onRestart(server.id)"
      >
        Restart Server
      </button>
    </template>
  </div>
</template>

<script>
export default {
  props: {
    server: Object,
    onRestart: Function,
  },
}
</script>
