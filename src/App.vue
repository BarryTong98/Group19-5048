<template>
  <el-container style="background-color: #abd1c6">
    <el-header height="90px" class="out-head">
      <div class="wordHead">World Happiness Report - Group 19</div>
    </el-header>
    <el-container class="out-container">
      <el-aside class="out-aside">
        <div>
          <el-menu
            default-active="1"
            background-color="#004643"
            text-color="#fffffe"
            active-text-color="#f9bc60">
            <el-menu-item index="1" @click="changeView('Group')">
              <i class="el-icon-s-data"></i>
              <span slot="title">Group</span>
            </el-menu-item>
            <el-menu-item index="2" @click="changeView('Correlation')">
              <i class="el-icon-set-up"></i>
              <span slot="title">Correlation</span>
            </el-menu-item>
            <el-menu-item index="3" @click="changeView('Deviation')">
              <i class="el-icon-aim"></i>
              <span slot="title">Deviation</span>
            </el-menu-item>
            <el-menu-item index="4" @click="changeView('Factors')">
              <i class="el-icon-data-line"></i>
              <span slot="title">Factors</span>
            </el-menu-item>
            <el-menu-item index="5" @click="changeView('Continent')">
              <i class="el-icon-place"></i>
              <span slot="title">Continent</span>
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
      <el-main class="out-main">
        <div v-if="this.currentView=== 'Group'" class="wrap">
          <h1>Group</h1>
          <img style="width: 55%; height: 60%; margin-left: 15%" class="groupImg" src="../static/WechatIMG2987.png">
        </div>
        <div v-else-if="this.currentView=== 'Factors'" class="wrap">
          <h1>Factors</h1>
          <span><span style="color: #e16162">Tip: </span>There are 2 visualizations to explain the relationship of Factors with happiness. Please slide down.</span>
          <el-container>
            <el-main>
              <el-tabs v-model="activeName" @tab-click="handleClick">
                <el-tab-pane label="Economy(GDP)" name="first">
                  <div v-show="show2015">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/influence-scatter/2015/GDP.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2015/2015-gdp.html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2016">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/influence-scatter/2016/GDP.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2016/2016-gdp.html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2017">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/influence-scatter/2017/GDP.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2017/2017-gdp.html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2018">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/influence-scatter/2018/GDP.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2018/2018-gdp.html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2019">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/influence-scatter/2019/GDP.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2019/2019-gdp.html"></iframe>
                    </div>
                  </div>
                </el-tab-pane>
                <el-tab-pane label="Family" name="second">
                  <div v-show="show2015">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/influence-scatter/2015/family.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2015/2015-family.html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2016">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/influence-scatter/2016/family.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2016/2016-family.html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2017">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/influence-scatter/2017/family.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2017/2017-family.html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2018">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/influence-scatter/2018/family.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2018/2018-family.html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2019">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/influence-scatter/2019/family.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2019/2019-family.html"></iframe>
                    </div>
                  </div>
                </el-tab-pane>
                <el-tab-pane label="Health" name="third">
                  <div v-show="show2015">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/influence-scatter/2015/healthy.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2015/2015-health.html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2016">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/influence-scatter/2016/health.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2016/2016-health.html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2017">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/influence-scatter/2017/healthy.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2017/2017-health.html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2018">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/influence-scatter/2018/healthy.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2018/2018-health.html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2019">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/influence-scatter/2019/healthy.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2019/2019-health.html"></iframe>
                    </div>
                  </div>
                </el-tab-pane>
                <el-tab-pane label="Freedom" name="fourth">
                  <div v-show="show2015">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/influence-scatter/2015/freedom.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2015/2015-freedom.html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2016">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/influence-scatter/2016/freedom.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2016/2016-freedom.html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2017">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/influence-scatter/2017/freedom.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2017/2017-freedom.html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2018">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/influence-scatter/2018/freedom.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2018/2018-freedom.html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2019">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/influence-scatter/2019/freedom.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2019/2019-freedom.html"></iframe>
                    </div>
                  </div>
                </el-tab-pane>
                <el-tab-pane label="Trust(Government Corruption)" name="fifth">
                  <div v-show="show2015">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/influence-scatter/2015/trust.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0"
                              src="./static/influence-map/2015/2015-trust(Government%20Corruption).html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2016">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/influence-scatter/2016/trust.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0"
                              src="./static/influence-map/2016/2016-trust(Government%20Corruption).html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2017">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/influence-scatter/2017/trust.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0"
                              src="./static/influence-map/2017/2017-trust(Government%20Corruption).html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2018">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/influence-scatter/2018/trust.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0"
                              src="./static/influence-map/2018/2018-trust(Government%20Corruption).html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2019">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/influence-scatter/2019/trust.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0"
                              src="./static/influence-map/2019/2019-trust(Government%20Corruption).html"></iframe>
                    </div>
                  </div>
                </el-tab-pane>
                <el-tab-pane label="Generosity" name="sixth">
                  <div v-show="show2015">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/influence-scatter/2015/generosity.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2015/2015-generosity.html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2016">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/influence-scatter/2016/generosity.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2016/2016-generosity.html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2017">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/influence-scatter/2017/generosity.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2017/2017-generosity.html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2018">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/influence-scatter/2018/generosity.html"></iframe>
                    </div>
                    <div style="height: 500px;margin-top: 100px">
                      <iframe frameBorder="0" src="./static/influence-map/2018/2018-generosity.html"></iframe>
                    </div>
                  </div>
                  <div v-show="show2019">
                    <div style="height:500px">
                      <iframe frameBorder="0" src="./static/influence-scatter/2019/generosity.html"></iframe>
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
                        fit="contain" 4></el-image>
            </div>
            <el-footer>
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
          <Correlation></Correlation>
        </div>
        <div v-else-if="this.currentView=== 'Continent'" class="wrap">
          <h1>Continent</h1>
          <span><span style="color: #e16162">Tip: </span>It may take a while to reload the visualisation since I deploy it in the website</span>
          <iframe class="Continent" frameBorder="0" src="https://barrt-test.herokuapp.com/"></iframe>
        </div>
        <div v-else-if="this.currentView=== 'Deviation'" class="wrap">
          <h1>Deviation</h1>
          <div style="height:500px">
            <iframe class="Deviation" frameBorder="0" src="static/result.html"/>
          </div>
        </div>
        <div v-else-if="this.currentView=== 'Global'" class="wrap">
          <h1>Global</h1>
          <iframe class="Global" frameBorder="0" src="static/map.html"/>
        </div>
      </el-main>
    </el-container>
  </el-container>

</template>

<script>

import Correlation from "./components/Correlation";

export default {
  components: {Correlation},
  data() {
    return {
      currentView: '',
      Intro: {
        'Group': 'Use given data set and clustering algorithms to classify countries into three clusters. Calculate the Difference between the clustering results and the actual classification values and mark them with different colors on the map. The larger red areas illustrate the better performance of the clustering algorithm and the greater  association of these data with the country\'s level of development',
        'Factors': 'These visualizations are trying to analyze the relationship between six factors and happiness. \n' +
          'Each circle in the diagram represents a country, X-axis represents factor rank, Y-axis represents happiness rank, the color represents the continent the country belongs to, and the size of the circle represents the population of this country.  On the map, the bigger circle means the higher happiness scores, and the color represents the ranking of the contribution degree of a factor. ',
        'Correlation': 'These visualizations show correlations between individual factors based on the data provided. In the Correlation Matrix, the closer the value is to 1 or -1, the greater the correlation between the two factors. At the same time, the Correlation Histogram shows the correlation between various factors and happiness. This makes it very intuitive to see which factors have the greatest impact on happiness. In the Scatter and Density plot, by looking at the trend of points, the influence between the features can also be obtained.\n',
        'Continent': 'This multi-level pie chart shows the overall happiness score in different regions and the happiness variance rate over years. The darker(bluer) color of the region/country means this area is more happy. It is possible to compare the overall happiness score of countries in several regions through the selection of different regions. A positive and higher happiness rate means that the country is becoming happier, while a negative happiness rate means that the country is becoming less happy. ',
        'Deviation': 'This figure divides the dataset into five years, with each year\'s data falling in the same grid. Also the data in different intervals are represented by different colors. We can find that the overall difference of the data decreases as the year score increases, indicating that the effect of health on well-being increases with the year. An interesting finding is that the top 10 and bottom 10 countries in health rankings typically have vastly different happiness rankings.',
        'Global': 'Display the happiness ranking segment and the most important influencing factor for each country in different colors in two maps. Using timeline in pyecharts to display data in different year. The largest contributors to happiness in most countries are economic and family.In particular, economy occupied the majority of areas in 2016, while in other years family factors take up a greater proportion\n',
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

      show2015: true,
      show2016: false,
      show2017: false,
      show2018: false,
      show2019: false,
    }
  },

  methods: {
    getYear(mark) {
      console.log(mark)
      if (mark === 0) {
        this.show2015 = true
        this.show2016 = false
        this.show2017 = false
        this.show2018 = false
        this.show2019 = false
      } else if (mark === 25) {
        this.show2016 = true
        this.show2015 = false
        this.show2017 = false
        this.show2018 = false
        this.show2019 = false
      } else if (mark === 50) {
        this.show2017 = true
        this.show2015 = false
        this.show2016 = false
        this.show2018 = false
        this.show2019 = false
      } else if (mark === 75) {
        this.show2018 = true
        this.show2015 = false
        this.show2016 = false
        this.show2017 = false
        this.show2019 = false
      } else if (mark === 100) {
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
.out-head {
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

.out-main {
  margin-left: 20px;
  margin-right: 20px;
  margin-bottom: 20px;
  background-color: #fffffe;
}

.out-aside {
  margin-left: 20px;
  margin-bottom: 20px;
}

.textBox {
  margin-left: 20px;
  margin-right: 10px;
  height: 70%;
  overflow-x: hidden;
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

h2 {
  text-align: center;
}

p {
  text-indent: 25px
}


.groupImg {
  margin: 5%
}


.el-divider--horizontal {
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

html, body, #app, .out-head {
  /*设置内部填充为0，几个布局元素之间没有间距*/
  padding: 0px;
  /*外部间距也是如此设置*/
  margin: 0px;
  /*统一设置高度为100%*/
  height: 100%;
}

.el-tabs__item.is-active {
  color: #004643
}

.el-tabs__active-bar {
  background-color: #004643
}

.el-tabs__item:hover {
  color: #004643
}


</style>
