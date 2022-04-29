<template>

  <el-container>
    <el-header>Header</el-header>
    <el-container>
      <el-aside width="300px">
        <div>
          <el-row class="tac">
            <el-col :span="12">
              <el-menu
                default-active="2"
                class="el-menu-vertical-demo"
                background-color="#545c64"
                text-color="#fff"
                active-text-color="#ffd04b">
                <el-menu-item index="1" @click="changeView('Group')">
                  <i class="el-icon-menu"></i>
                  <span slot="title">Group</span>
                </el-menu-item>
                <el-menu-item index="2" @click="changeView('Influence')">
                  <i class="el-icon-menu"></i>
                  <span slot="title">Influence</span>
                </el-menu-item>
                <el-menu-item index="3" @click="changeView('Correlation')">
                  <i class="el-icon-document"></i>
                  <span slot="title">Correlation</span>
                </el-menu-item>
                <el-menu-item index="4" @click="changeView('Continent')">
                  <i class="el-icon-setting"></i>
                  <span slot="title">Continent</span>
                </el-menu-item>
                <el-menu-item index="5" @click="changeView('Deviation')">
                  <i class="el-icon-setting"></i>
                  <span slot="title">Deviation</span>
                </el-menu-item>
                <el-menu-item index="6" @click="changeView('Global')">
                  <i class="el-icon-setting"></i>
                  <span slot="title">Global</span>
                </el-menu-item>
              </el-menu>
            </el-col>
          </el-row>
        </div>
      </el-aside>
      <el-main>
        <div v-if="this.currentView=== 'Group'" class="wrap">
          <h1>Group</h1>
        </div>
        <div v-else-if="this.currentView=== 'Influence'" class="wrap">
          <h1>Influence</h1>
        </div>
        <div v-else-if="this.currentView=== 'Correlation'" class="wrap">
          <h1>Correlation</h1>
        </div>
        <div v-else-if="this.currentView=== 'Continent'" class="wrap">
          <h1>Continent</h1>
          <iframe frameBorder="0" src="https://barrt-test.herokuapp.com/"></iframe>
        </div>
        <div v-else-if="this.currentView=== 'Deviation'" class="wrap">
          <h1>Deviation</h1>
        </div>
        <div v-else-if="this.currentView=== 'Global'" class="wrap">
          <h1>Global</h1>
        </div>
        <div v-else-if="this.currentView=== 'Unknown'" class="wrap">
          <h1>Unknown</h1>
        </div>
      </el-main>
    </el-container>
  </el-container>

</template>

<script>
export default {
  data() {
    return {
      currentView: ''
    }
  },
  methods: {
    changeView(view) {
      console.log(view)
      this.currentView = view;
      console.log(this.currentView)
    },
  },
  created() {
    this.currentView = 'Group';
  }
}
</script>

<style>
.wrap {
  width: 1440px;
  height: 1580px;
  overflow: hidden;
}

iframe {
  width: 150% !important;
  height: 100% !important;
  -webkit-transform: scale(0.6);
  transform: scale(0.6);
  -webkit-transform-origin: 0 0;
  transform-origin: 0 0;
}
</style>
