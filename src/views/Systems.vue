<template>
  <div class="systems">
    <div class="row">
        <h2>Systems</h2>
        <p>A list of all graphs in the database.</p>

        <table>
            <tr>
                <th>Name</th>
                <th>Description</th>
            </tr>
            <tr v-for="system in systems" :key="system.id">
                <td>{{ system.name }}</td>
                <td>{{ system.description }}</td>
            </tr>
        </table>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'HomeView',
  data () {
    return {
        systems: [],
    }
  },
  components: {
    HelloWorld
  },
  async mounted () {
    const res = await fetch('https://nosy.kresh.me/api/services.php?op=list&q=system')
    this.systems = await res.json();
  },
}
</script>

<style>
.systems {
  display: flex;
  flex-direction: column;
  justify-content: start;
  align-items: start;
}

.systems .row {
    width: 100%;
}

.systems table {
    width: 100%;
    background: #77a;
    margin-top: 36px;
    background: #FFF;
    border-radius: 12px;
    padding: 0 16px;
}

.systems table th {
    border-bottom: #aaa;
}

.systems table th, .systems table tr {
    height: 42px;
    vertical-align: middle;
}

@media (prefers-color-scheme: dark) {
  #app {
    background: var(--bg-dark) !important;
  }
}

@media screen and (min-width: 900px) {
  .systems {
    width: calc(100vw - 2 * 200px);
    height: calc(100vh - 2 * 100px);
  }
}
</style>
