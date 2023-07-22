<script>
import CardComponent from './Cards.vue'
import ContactMe from './ContactMe.vue'
import img1 from '../assets/Image1.png'
import img2 from '../assets/Image2.png'
import img3 from '../assets/Image3.png'
import img4 from '../assets/Image4.png'
export default {
  name: 'TabsComponent',
  components: {
    CardComponent,
    ContactMe
  },
  data() {
    return {
      tabs: ['Web Design', 'Mobile App Design', 'Freebies'],
      activeTabIndex: 0,
      projectList: [
        { title: 'Minify - Web Design', imageUrl: img1 },
        { title: 'Ant - Personal Portofolio', imageUrl: img2 },
        { title: 'Lumy - Dashboard UI Kit', imageUrl: img3 },
        { title: 'Keeper - Soccer Site', imageUrl: img4 }
      ]
    }
  },
  methods: {
    setActiveTab(index) {
      this.activeTabIndex = index
    }
  }
}
</script>

<template>
  <section class="container">
    <div class="title-container">
      <h1 class="title">Our Projects</h1>
    </div>
    <div class="tab-container">
      <div class="tabs">
        <div
          v-for="(tab, index) in tabs"
          :key="index"
          :class="{ activeTab: this.activeTabIndex === index }"
          @click="setActiveTab(index)"
        >
          {{ tab }}
        </div>
      </div>
      <!-- Conditional rendering for tab content based on activeTabIndex -->
      <div v-if="activeTabIndex === 0" class="tab-cards">
        <CardComponent
          v-for="(project, index) in projectList"
          :key="index"
          :title="project.title"
          :imageUrl="project.imageUrl"
          :options="true"
        />
      </div>
      <div v-if="activeTabIndex === 1">Mobile App design content under construction</div>
      <div v-if="activeTabIndex === 2">Freebies content under construction</div>
    </div>
    <ContactMe />
  </section>
</template>

<style lang="scss">
.title-container {
  width: 285px;
  padding: 0 2rem;
  .title {
    font-size: 48px;
    line-height: 62px;
    font-weight: 600;
  }
}
.tab-container {
  padding: 0 2rem;
  .tabs {
    display: flex;
    gap: 5rem;
    padding: 8px 0px;
    color: #828282;
    font-size: 32px;
    line-height: 54px;
  }

  .tabs > div {
    cursor: pointer;
    padding: 8px 0px;
  }

  .tabs > div.activeTab {
    /* text-decoration: underline; */
    color: #eebf63;
    border-bottom: 4px solid #eebf63;
    margin-bottom: 20px;
    border-radius: 1px;
  }
  .tab-cards {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(550px, 1fr));
    gap: 30px;
  }
}
</style>
