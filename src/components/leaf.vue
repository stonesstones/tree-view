<template>
<!--  :open="initiallyOpen"-->
<!--  open-on-click-->
  <v-treeview
      v-model="tree"
      :items="items"
      activatable
      item-key="name"


  >
    <template v-slot:append="{ item }" >
      <v-btn v-show="!(item.file)" @click="addFolder(item)" >add folder</v-btn>
      <v-btn v-show="!(item.file)" @click="addFile(item)" >add file</v-btn>
    </template>
  </v-treeview>
</template>

<script>
export default {
  name: "leaf",
  methods:{
    addFolder: function(item){
      //alert(item)
      item.children.push({
        name: "folder",
        file: false,
        children:[{
          name:"file",
          file: true,
        }]

      })
    },
    addFile: function(item){
      item.children.push({
        name: "file",
        file: true,
      })
      //alert(item.children)
    }
  },
  data(){
    return{
      binder: "",
      initiallyOpen: ['public'],
      tree: [],
      items: [
        {
          name: '5gatu13niti',
          file: false,
          children: [
            {
              name: 'simo',
              file: false,
              children: [{
                name: 'happy birthday',
                file: true,
              }],
            },
            {
              name: '(^-^)',
              file: true,
            },
            {
              name: '!!!!!',
              file: false,
              children:[{
                name: "happy birthday",
                file: true,
              }]
            },
          ],
        },
      ],
    }
  }
}
</script>

<style scoped>

</style>