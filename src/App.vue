<template>

  <el-container>
    <el-header>
      <div class="wordHead">Group 19 World Happiness Report</div>
    </el-header>
    <el-container>
      <el-aside>
        <div>
          <el-menu
            default-active="2"
            class="el-menu-vertical-demo"
            background-color="#5CDB9F"
            text-color="#fff"
            active-text-color="green">
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
        </div>
        <el-form class="text">
          <h2>Introduction</h2>
          <el-divider></el-divider>
          <div class="textBox">
            <p>
              {{ Intro[currentView] }}
            </p>
          </div>
        </el-form>
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
          <iframe class="Continent" frameBorder="0" src="https://barrt-test.herokuapp.com/"></iframe>
        </div>
        <div v-else-if="this.currentView=== 'Deviation'" class="wrap">
          <h1>Deviation</h1>
        </div>
        <div v-else-if="this.currentView=== 'Global'" class="wrap">
          <h1>Global</h1>
          <iframe class="Global" frameBorder="0" src="static/map.html"/>
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
      currentView: '',
      Intro: {
        'Group': 'Group',
        'Influence': 'Influence',
        'Correlation': 'Correlation',
        'Continent': 'Continent',
        'Deviation': 'Deviation',
        'Global': 'Global',
      }
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

.textBox{
  margin-left: 20px;
  margin-right: 10px;
  height: 70%;
  overflow-x:hidden;
}

.text {
  background-color: #F7F7F7;
  border-radius: 4px;
  margin-top: 5px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, .12),
  0 0 10px rgba(0, 0, 0, .25);
  width: 94%;
  height: 400px;
  margin-left: 2px;
  padding-top: 7px;
  padding-left: 5px;
  padding-right: 5px;
}

.item {
  padding: 18px 0;
}

.box-card {
  width: 295px;
}


.wrap {
  width: 1150px;
  height: 690px;
  overflow: hidden;
}


.wordHead {
  color: black;
}


.el-icon-menu {
  color: #42b983;
}

h2{
  text-align: center;
}

p{
  text-indent:25px
}

.el-header{
  margin: 20px 20px 20px 20px;
  font-weight: 100;
  text-transform: uppercase;
  color: black;
  font-family: Arial, Helvetica, sans-serif;
  font-size: 40px;
  text-shadow: 2px 5px 0 rgba(0,0,0,0.2);
}

.el-divider--horizontal{
  margin-bottom: 10px;
  margin-top: 10px;
}

.el-main{
  background-color: #F7F7F7;
  box-shadow: 0 2px 4px rgba(0, 0, 0, .12),
  0 0 10px rgba(0, 0, 0, .25);
}
iframe {
  width: 165% !important;
  height: 200% !important;
  -webkit-transform: scale(0.6);
  transform: scale(0.6);
  -webkit-transform-origin: 0 0;
  transform-origin: 0 0;
}
</style>
