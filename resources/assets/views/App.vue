<template>
<div class="container body">
  <div id="app">
    <div class="main_container">
      <sidebar></sidebar>
      <navbar></navbar>
      <!-- Main content -->
      <div class="right_col" role="main">
        <section class="content">
          <!-- Page Title -->
          <titlebar></titlebar>
          <!-- Your Page Content Here -->
          <!-- route outlet -->
          <router-view></router-view>
        </section>
      </div>
      <!-- /.content -->
      <footbar></footbar>
    </div>
  </div>
</div>
</template>

<script>
import Titlebar from './components/layouts/Titlebar.vue';
import Navbar from './components/layouts/Navbar.vue';
import Sidebar from './components/layouts/Sidebar.vue';
import Footbar from './components/layouts/Footbar.vue';
import store from '../vuex/store';

export default {
  data() {
    return {
      show: false
    }
  },
  ready() {
    this.$set('show', this.$route.auth);
  },
  components: {
    Titlebar,
    Navbar,
    Sidebar,
    Footbar
  },
  store,
  replace: false
}
</script>