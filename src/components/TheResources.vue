<template>
  <base-card>
    <base-button
      type="Stored Resources"
      @click="setSelectedTab('stored-resources')"
      >Stored Resources</base-button
    >
    <base-button type="Add Resource" @click="setSelectedTab('add-resource')"
      >Add Resource</base-button
    >
  </base-card>
  <component :is="selectedTab"></component>
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
          id: "google",
          title: "Google",
          description: "Learn to google...",
          link: "https://www.google.com",
        },
      ],
    };
  },
  provide() {
    return {
      resources: this.storedResources,
    };
  },
  methods: {
    setSelectedTab(tab) {
      this.selectedTab = tab;
    },
  },
};
</script>

<style></style>
