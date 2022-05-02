<template>
  <el-container style="background-color: #abd1c6">
    <el-header height="90px" class="out-head">
      <div class="wordHead">World Happiness Report - Group 19</div>
    </el-header>
    <el-container class="out-container">
      <el-aside class="out-aside">
        <div>
          <el-menu
            default-active="2"
            background-color="#004643"
            text-color="#fffffe"
            active-text-color="#f9bc60">
            <el-menu-item index="1" @click="changeView('Group')">
              <i class="el-icon-s-data"></i>
              <span slot="title">Group</span>
            </el-menu-item>
            <el-menu-item index="2" @click="changeView('Influence')">
              <i class="el-icon-data-line"></i>
              <span slot="title">Influence</span>
            </el-menu-item>
            <el-menu-item index="3" @click="changeView('Correlation')">
              <i class="el-icon-set-up"></i>
              <span slot="title">Correlation</span>
            </el-menu-item>
            <el-menu-item index="4" @click="changeView('Continent')">
              <i class="el-icon-place"></i>
              <span slot="title">Continent</span>
            </el-menu-item>
            <el-menu-item index="5" @click="changeView('Deviation')">
              <i class="el-icon-aim"></i>
              <span slot="title">Deviation</span>
            </el-menu-item>
            <el-menu-item index="6" @click="changeView('Global')">
              <i class="el-icon-pie-chart"></i>
              <span slot="title">Global</span>
            </el-menu-item>
          </el-menu>
        </div>
        <!--introduction-->
        <el-form class="introduction">
          <h2>Introduction</h2>
          <el-divider></el-divider>
          <div class="textBox">
            <p>
              {{ Intro[currentView] }}
            </p>
          </div>
        </el-form>
      </el-aside>
      <el-main  class="out-main">
        <div v-if="this.currentView=== 'Group'" class="wrap">
          <h1>Group</h1>
        </div>
        <div v-else-if="this.currentView=== 'Influence'" class="wrap">
          <h1>Influence</h1>
          <span><span style="color: #e16162">Tip: </span>There are 2 visualizations to explain the relationship of influence with happiness. Please slide down.</span>
          <el-container>
            <el-main>
              <el-tabs v-model="activeName" @tab-click="handleClick">
                <el-tab-pane label="Economy(GDP)" name="first">
                  <div v-show="show2015">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/2015_freedom.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2015/2015-gdp.html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2016">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/2015_freedom.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2016/2016-gdp.html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2017">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/2015_freedom.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2017/2017-gdp.html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2018">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/2015_freedom.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2018/2018-gdp.html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2019">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/2015_freedom.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2019/2019-gdp.html"></iframe>
                    </div>
                  </div>
                </el-tab-pane>
                <el-tab-pane label="Family" name="second">
                  <div v-show="show2015">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/2015_freedom.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2015/2015-family.html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2016">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/2015_freedom.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2016/2016-family.html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2017">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/2015_freedom.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2017/2017-family.html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2018">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/2015_freedom.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2018/2018-family.html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2019">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/2015_freedom.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2019/2019-family.html"></iframe>
                    </div>
                  </div>
                </el-tab-pane>
                <el-tab-pane label="Health" name="third">
                  <div v-show="show2015">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/2015_freedom.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2015/2015-health.html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2016">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/2015_freedom.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2016/2016-health.html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2017">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/2015_freedom.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2017/2017-health.html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2018">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/2015_freedom.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2018/2018-health.html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2019">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/2015_freedom.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2019/2019-health.html"></iframe>
                    </div>
                  </div>
                </el-tab-pane>
                <el-tab-pane label="Freedom" name="fourth">
                  <div v-show="show2015">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/2015_freedom.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2015/2015-freedom.html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2016">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/2015_freedom.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2016/2016-freedom.html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2017">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/2015_freedom.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2017/2017-freedom.html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2018">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/2015_freedom.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2018/2018-freedom.html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2019">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/2015_freedom.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2019/2019-freedom.html"></iframe>
                    </div>
                  </div>
                </el-tab-pane>
                <el-tab-pane label="Trust(Government Corruption)" name="fifth">
                  <div v-show="show2015">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/2015_freedom.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2015/2015-trust(Government%20Corruption).html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2016">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/2015_freedom.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2016/2016-trust(Government%20Corruption).html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2017">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/2015_freedom.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2017/2017-trust(Government%20Corruption).html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2018">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/2015_freedom.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2018/2018-trust(Government%20Corruption).html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2019">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/2015_freedom.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2019/2019-trust(Government%20Corruption).html"></iframe>
                    </div>
                  </div>
                </el-tab-pane>
                <el-tab-pane label="Generosity" name="sixth">
                  <div v-show="show2015">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/2015_freedom.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2015/2015-generosity.html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2016">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/2015_freedom.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2016/2016-generosity.html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2017">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/2015_freedom.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2017/2017-generosity.html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2018">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/2015_freedom.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2018/2018-generosity.html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2019">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/2015_freedom.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2019/2019-generosity.html"></iframe>
                    </div>
                  </div>
                </el-tab-pane>
              </el-tabs>
            </el-main>
            <div style="text-align: center">
              <el-image src="./static/img-influence-map.png"
                        style="width: 150px;"
                        fit="contain"></el-image>
            </div>
            <el-footer >
              <div class="influence-time">
                <el-slider
                  @change="getYear(value)"
                  v-model="value"
                  :step="25"
                  :marks="marks">
                </el-slider>
              </div>
            </el-footer>
          </el-container>
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
      },
      activeName: 'first',

      //for 时间条
      value: 0,
      marks: {
        0: '2015',
        25: '2016',
        50: '2017',
        75: '2018',
        100: '2019',
      },

      show2015:true,
      show2016:false,
      show2017:false,
      show2018:false,
      show2019:false,
    }
  },

  methods: {
    getYear(mark){
      console.log(mark)
      if (mark === 0){
        this.show2015 = true
        this.show2016 = false
        this.show2017 = false
        this.show2018 = false
        this.show2019 = false
      }
      else if(mark === 25){
        this.show2016 = true
        this.show2015 = false
        this.show2017 = false
        this.show2018 = false
        this.show2019 = false
      }
      else if(mark === 50){
        this.show2017 = true
        this.show2015 = false
        this.show2016 = false
        this.show2018 = false
        this.show2019 = false
      }
      else if(mark === 75){
        this.show2018 = true
        this.show2015 = false
        this.show2016 = false
        this.show2017 = false
        this.show2019 = false
      }
      else if(mark === 100){
        this.show2019 = true
        this.show2015 = false
        this.show2016 = false
        this.show2017 = false
        this.show2018 = false
      }
    },
    changeView(view) {
      console.log(view)
      this.currentView = view;
      console.log(this.currentView)
    },
    handleClick(tab, event) {
      console.log(tab, event);
    }
  },
  created() {
    this.currentView = 'Group';
  }
}
</script>

<style>
.out-head{
  font-weight: 100;
  text-transform: uppercase;
  color: #fffffe;
  font-family: Arial, Helvetica, sans-serif;
  font-size: 40px;
  background-color: #004643;
}
.wordHead {
  color: #fffffe;
  margin: 20px;
}

.out-container {
  margin-top: 20px;
}

.out-main{
  margin-left: 20px;
  margin-right: 20px;
  margin-bottom: 20px;
  background-color: #fffffe;
}

.out-aside {
  margin-left: 20px;
  margin-bottom: 20px;
}

.textBox{
  margin-left: 20px;
  margin-right: 10px;
  height: 70%;
  overflow-x:hidden;
}

.introduction {
  background-color: #fffffe;
  margin-top: 3px;
  height: 400px;
}

.item {
  padding: 18px 0;
}

.box-card {
  width: 295px;
}


.wrap {
  width: 100%;
  height: 100%;
  overflow: hidden;
}

.el-icon-menu {
  color: #d1d1e9;
}

h2{
  text-align: center;
}

p{
  text-indent:25px
}





.el-divider--horizontal{
  margin-bottom: 10px;
  margin-top: 10px;
}

iframe {
  width: 165% !important;
  height: 200% !important;
  -webkit-transform: scale(0.6);
  transform: scale(0.6);
  -webkit-transform-origin: 0 0;
  transform-origin: 0 0;
}

.influence-button {
  width: 100%;
}

.el-radio {
  width: 100px;
}

html,body,#app,.out-head{
  /*设置内部填充为0，几个布局元素之间没有间距*/
  padding: 0px;
  /*外部间距也是如此设置*/
  margin: 0px;
  /*统一设置高度为100%*/
  height: 100%;
}

.el-tabs__item.is-active{
  color: #004643
}

.el-tabs__active-bar{
  background-color:#004643
}
.el-tabs__item:hover{
  color: #004643
}


</style>
