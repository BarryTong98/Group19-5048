<template>

  <el-tabs v-model="activeName" @tab-click="handleClick">
    <el-tab-pane label="Correlation Matrix" name="first">
      <el-row>
        <el-col :offset="5" span="14">
          <img :src=CorrelationMatrix alt="CorrelationMatrix.png" class="correlationMatrix">
        </el-col>
        <el-col span="1">
          <el-radio-group v-model="radio" @change="change" class="radio-group">
            <el-radio label="1" class="radio">World</el-radio>
            <el-radio label="5" class="radio">Middle East and Northern Africa</el-radio>
            <el-radio label="2" class="radio">Western Europe</el-radio>
            <el-radio label="3" class="radio">North America</el-radio>
            <el-radio label="4" class="radio">Australia and New Zealand</el-radio>
            <el-radio label="6" class="radio">Latin America and Caribbean</el-radio>
            <el-radio label="7" class="radio">Southeastern Asia</el-radio>
            <el-radio label="8" class="radio">Central and Eastern Europe</el-radio>
            <el-radio label="9" class="radio">Eastern Asia</el-radio>
            <el-radio label="10" class="radio">Sub-Saharan Africa</el-radio>
            <el-radio label="11" class="radio">Southern Asia</el-radio>
          </el-radio-group>
        </el-col>
      </el-row>
    </el-tab-pane>
    <el-tab-pane label="Correlation Histogram" name="second">
      <el-row>
        <el-col :offset="5" span="14">
          <img :src=CorrelationHistogram alt="CorrelationHistogram.png" class="correlationHistogram">
        </el-col>
        <el-col span="1">
          <el-radio-group v-model="radio" @change="change" class="radio-group">
            <el-radio label="1" class="radio">World</el-radio>
            <el-radio label="5" class="radio">Middle East and Northern Africa</el-radio>
            <el-radio label="2" class="radio">Western Europe</el-radio>
            <el-radio label="3" class="radio">North America</el-radio>
            <el-radio label="4" class="radio">Australia and New Zealand</el-radio>
            <el-radio label="6" class="radio">Latin America and Caribbean</el-radio>
            <el-radio label="7" class="radio">Southeastern Asia</el-radio>
            <el-radio label="8" class="radio">Central and Eastern Europe</el-radio>
            <el-radio label="9" class="radio">Eastern Asia</el-radio>
            <el-radio label="10" class="radio">Sub-Saharan Africa</el-radio>
            <el-radio label="11" class="radio">Southern Asia</el-radio>
          </el-radio-group>
        </el-col>
      </el-row>
    </el-tab-pane>
    <el-tab-pane label="Scatter and Density Plot Matrix" name="third">
      <el-row>
        <el-col :offset="5" span="14">
          <img :src=plotScatterMatrix alt="plotScatterMatrix.png" class="plotScatterMatrix">
        </el-col>
        <el-col span="1">
          <el-radio-group v-model="radio" @change="change" class="radio-group">
            <el-radio label="1" class="radio">World</el-radio>
            <el-radio label="5" class="radio">Middle East and Northern Africa</el-radio>
            <el-radio label="2" class="radio">Western Europe</el-radio>
            <el-radio label="3" class="radio">North America</el-radio>
            <el-radio label="4" class="radio">Australia and New Zealand</el-radio>
            <el-radio label="6" class="radio">Latin America and Caribbean</el-radio>
            <el-radio label="7" class="radio">Southeastern Asia</el-radio>
            <el-radio label="8" class="radio">Central and Eastern Europe</el-radio>
            <el-radio label="9" class="radio">Eastern Asia</el-radio>
            <el-radio label="10" class="radio">Sub-Saharan Africa</el-radio>
            <el-radio label="11" class="radio">Southern Asia</el-radio>
          </el-radio-group>
        </el-col>
      </el-row>

    </el-tab-pane>
  </el-tabs>

</template>

<script>
export default {
  name: "Correlation",

  data() {
    return {
      activeName: 'first',
      radio: '1',
      region: 'World',
      CorrelationMatrix: "../../static/correlationFig/WorldCorrelationMatrix.png",
      CorrelationHistogram: "../../static/correlationFig/WorldCorrelationHistogram.png",
      plotScatterMatrix: "../../static/correlationFig/WorldplotScatterMatrix.png"
    };
  },
  methods: {
    handleClick(tab, event) {
      console.log(tab, event);
    },
    change(){
      switch (this.radio){
        case "1":
          this.region = 'World'
          break
        case "2":
          this.region = 'Western Europe'
          break
        case "3":
          this.region = "North America"
          break
        case "4":
          this.region = "Australia and New Zealand"
          break
        case "5":
          this.region = "Middle East and Northern Africa"
          break
        case "6":
          this.region = "Latin America and Caribbean"
          break
        case "7":
          this.region = "Southeastern Asia"
          break
        case "8":
          this.region = "Central and Eastern Europe"
          break
        case "9":
          this.region = "Eastern Asia"
          break
        case "10":
          this.region = "Sub-Saharan Africa"
          break
        case "11":
          this.region = "Southern Asia"
          break
      }
      this.CorrelationMatrix = "../../static/correlationFig/" + this.region + "CorrelationMatrix.png"
      this.CorrelationHistogram = "../../static/correlationFig/" + this.region + "CorrelationHistogram.png"
      this.plotScatterMatrix = "../../static/correlationFig/" + this.region + "plotScatterMatrix.png"
    }
  }
}
</script>

<style scoped>
.correlationMatrix {
  width: 610px;
  text-align: center;
}

.correlationHistogram {
  width: 610px;
  text-align: center;
}

.plotScatterMatrix {
  width: 610px;
  text-align: center;
}

.radio{
  margin-top: 10px;
}

.radio-group{
  margin-top: 100px;
}

</style>
