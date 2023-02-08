<template>
  <base-card>
    <base-button :bg="storedButtonMode" textcolor="text-brown-600" @click="setSelectedTab('stored-resources')"
      >Stored Resource</base-button
    >
    <base-button :bg="addButtonMode" textcolor="text-brown-600" @click="setSelectedTab('add-resources')"
      >Add Resource</base-button
    >
  </base-card>
  <component :is="selectedTab"></component>
</template>

<script>
import StoredResources from "./StoredResources.vue";
import AddResources from "./AddResources.vue";

export default {
  components: {
    AddResources,
    StoredResources,
  },
  data() {
    return {
      selectedTab: "stored-resources",
      storedResources: [
        {
          id: "official-guide",
          title: "The Official",
          description: "Official Vue.js documentation",
          link: "https://vuejs.org",
        },
        {
          id: "google",
          title: "Google",
          description: "Google to learn",
          link: "https://google.com",
        },
      ],
    };
  },
  computed:{
    storedButtonMode(){
        return this.selectedTab === "stored-resources" ? "bg-purple-400" : "bg-white";
    },
    addButtonMode(){
        return this.selectedTab === "add-resources" ? "bg-purple-400" : "bg-white";
    }
  },
  provide(){
    return{
        resources: this.storedResources
    }
  },
  methods: {
    setSelectedTab(tab) {
      this.selectedTab = tab;
    },
  },
};
</script>
