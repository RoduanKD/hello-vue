<template>
  <table>
    <thead>
      <tr>
        <th :colspan="items.length">
          <slot></slot>
        </th>
      </tr>
      <tr>
        <th><button v-on:click="clearSelection">Clear Selection</button></th>
        <th v-for="header in headers" v-bind:key="header">{{ header }}</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="item in items" v-bind:key="item.name">
        <td><input type="radio" v-model="selectedItem" v-bind:value="item.name"></td>
        <td v-for="header in headers" :key="header">
          <slot :name="header" :item="item[header]">
            {{ item[header] }}
          </slot>
          </td>
      </tr>
    </tbody>
    <tfoot v-if="selectedItem">
      <tr>
        <td v-bind:colspan="headers.length + 1">
          <button v-on:click="$emit('deleteSelectedItem', selectedItem)">Delete Selected item</button>
          <button v-on:click="$emit('editSelectedItem', selectedItem)">Edit Selected item</button>
          <slot name="footer">nothing</slot>
        </td>
      </tr>
    </tfoot>
  </table>
</template>

<script>
export default {
  props: {
    items: {
      type: Array,
      default: () => []
    },
    headers: {
      type: Array,
      default: () => []
    }
  },
  data () {
    return {
      selectedItem: null
    }
  },
  methods: {
    clearSelection () {
      this.selectedItem = null
    }
  }
}
</script>
