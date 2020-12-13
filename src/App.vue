<template>
  <q-layout view="lHh Lpr lFf">
    <q-tabs inline-label no-caps class="bg-black text-white shadow-2" align="center">
      <q-tab name="Home" label="Home" />
      <q-tab name="Project" label="Projects" />
      <q-tab name="Datasets" label="Datasets" />
      <q-tab name="About" label="About" />
    </q-tabs>
    <div class="main">
      <h3>Dataset upload</h3>
      <h5>
        Follow the guide to structure your folder and make it into a usable dataset.
      </h5>
      <p>Upload a dataset with an equal amount of cats and dogs</p>

      <!-- File Input -->
      <q-file
        v-model="selectedDataset"
        label="Drag & drop or select a folder"
        outlined
        use-chips
        webkitdirectory
        mozdirectory
        multiple
        @input="onDatasetSelected"
      >
      </q-file>
      <ul>
        <li v-for="(item, index) in selectedDataset" :key="index">{{ item.type }}</li>
      </ul>
    </div>
    <p>Dataset {{ selectedDataset }}</p>
  </q-layout>
</template>

<script>
export default {
  name: "LayoutDefault",

  components: {},

  data() {
    return {
      selectedDataset: null, //[] or null?
    };
  },

  methods: {
    onDatasetSelected: function (event) {
      console.log(event);
    },
  },
};
</script>

<style>
.main {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  padding-top: 1em;
}

h3 {
  margin: 0.2em;
}

h5 {
  margin-top: 0.2em;
}

label.q-field.q-validation-component.row.no-wrap.items-start.q-file.q-field--auto-height.q-field--outlined.q-field--labeled {
  width: 50%;
}
</style>
