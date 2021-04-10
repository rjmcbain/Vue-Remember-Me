<template>
  <base-card>
    <base-button
      type="Stored Resources"
      :mode="storedResButtonMode"
      @click="setSelectedTab('stored-resources')"
      >Stored Resources</base-button
    >
    <base-button
      type="Add Resource"
      :mode="addResButtonMode"
      @click="setSelectedTab('add-resource')"
      >Add Resource</base-button
    >
  </base-card>
  <keep-alive>
    <component :is="selectedTab"></component>
  </keep-alive>
</template>

<script>
import StoredResources from "../components/StoredResources";
import AddResource from "../components/AddResource";
import BaseButton from "../components/UI/BaseButton";
import BaseCard from "../components/UI/BaseCard";
export default {
  components: {
    BaseCard,
    BaseButton,
    StoredResources,
    AddResource,
  },
  data() {
    return {
      selectedTab: "stored-resources",
      storedResources: [
        {
          id: "official-guide",
          title: "Official Guide",
          description: "The official Vue.js documentation",
          link: "https://vuejs.org",
        },
        {
          id: "stackoverflow",
          title: "Stack Overflow",
          description:
            "A public platform building the definitive collection of coding questions & answers",
          link: "https://stackoverflow.com/",
        },
        {
          id: "google",
          title: "Google",
          description:
            "Provides users with the most relevant, highest quality results based on user search queries",
          link: "https://www.google.com",
        },
      ],
    };
  },
  provide() {
    return {
      resources: this.storedResources,
      addResource: this.addResource,
      deleteResource: this.removeResource,
    };
  },
  computed: {
    storedResButtonMode() {
      return this.selectedTab === "stored-resources" ? null : "flat";
    },
    addResButtonMode() {
      return this.selectedTab === "add-resource" ? null : "flat";
    },
  },
  methods: {
    setSelectedTab(tab) {
      this.selectedTab = tab;
    },
    addResource(title, description, url) {
      const newResource = {
        id: new Date().toISOString(),
        title: title,
        description,
        description,
        link: url,
      };
      this.storedResources.unshift(newResource);
      this.selectedTab = "stored-resources";
    },
    removeResource(resId) {
      const resIndex = this.storedResources.findIndex(
        (res) => res.id === resId
      );
      this.storedResources.splice(resIndex, 1);
    },
  },
};
</script>

<style></style>
