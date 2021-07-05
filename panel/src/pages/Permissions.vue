<template>
  <q-layout view="lHh lpr lFf" class="flex content-center justify-center">
    <Header/>
    <q-page-container>
      <q-page>
        {{columns}}
        <q-table
        title="Разрешения"
        :columns="columns"
        >

        </q-table>
      </q-page>
    </q-page-container>
  </q-layout>
</template>

<script lang="ts">
import {
  defineComponent,
  reactive, ref,
  toRefs
} from 'vue'
import Roles from '../type/role'
import Header from '../components/LayoutComponents/Header';
export default defineComponent({
  name: "Permissions",
  components: {Header},
  setup() {
    const state = reactive({
      apiUrl: 'https://threecrabs.tech',
      columns: [] as Roles
    })

    return {
      ...toRefs(state)
    }
  },
  mounted() {
    this.getRoles()
  },
  methods: {
    async getRoles() {
      let response = await fetch(`${this.apiUrl}/roles`, {
        headers: {
          'Content-Type': 'application/json'
        }
      })
      response = await response.json()

      this.columns = response;
    }
  }
})
</script>

<style scoped>

</style>
