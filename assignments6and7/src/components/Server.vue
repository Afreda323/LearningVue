<template>
  <div class="col-xs-12 col-sm-6">
    <ul class="list-group">
      <li
        class="list-group-item"
        v-for="server in servers"
        :key="server.id"
        @click="onSelect(server)"
      >
        Server #{{ server.id }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    servers: {
      type: Array,
    },
    onSelect: {
      type: Function,
    },
  },
}
</script>