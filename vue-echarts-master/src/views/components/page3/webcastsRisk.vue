<template>
    <div class="webcastsRisk"></div>
</template>

<script>
import axios from 'axios';
// import baseUrl from '../../../utils/interface.js'
export default {
    name: 'webcastsRisk',
    props:['msg'],
    data() {
        return {
          option :{
            title: {
              text: 'Number of Contributions',
              textStyle: {
                color: "#fff",
                fontSize: 12
              },
              top: '4%',
              left: '4%'
            },
            tooltip: {
              trigger: 'axis',
              axisPointer: {            // 坐标轴指示器，坐标轴触发有效
                type: 'shadow'        // 默认为直线，可选为：'line' | 'shadow'
              }
            },
            legend: {
              data: [
                {name: 'ss', icon: 'circle'},
                {name: 'ssss', icon: 'circle'},
                {name: 'dddddddd', icon: 'circle'},
                {name: 'wwwwwwwww', icon: 'circle'},
              ],
              gridIndex: 3,
              right: "5%",
              top: "6%",
              itemWidth: 7,
              itemHeight: 7,
              textStyle: {
                color: '#00CCFF',
                fontSize: 10
              }
            },
            grid: {
              top: '15%',
              left: '3%',
              right: '50%',
              bottom: '5%',
              containLabel: true
            },
            xAxis: {
              type: 'value',
              axisLabel: {show: false},
              axisTick: {show: false},
              splitLine: {show: false},
              axisLine: {show: false}
            },
            yAxis: {
              type: 'category',
              axisTick: {show: false},
              splitLine: {show: false},
              axisLine: {show: false},
              axisLabel: {
                color: '#fff',
                backgroundColor: '#4A7AFF',
                borderRadius: 3,
                margin: 0,
                padding: [1, 3, 1, 3]
              },
              inverse: true,
              data: ['1', '2', '3', '4', '5', '6', '7', '8', '9', '10']
            },
            series: [
              {
                name: '',
                type: 'bar',
                stack: '',
                barWidth: 8,
                itemStyle: {
                  color: '#142AFE',
                  barBorderRadius: [0, 8, 8, 0]
                },
                label: {
                  normal: {
                    show: false,

                    position: 'insideRight'
                  }
                },
                data: [1, 1, 1, 1, 1, 1, 1, 1, 210, 15]
              },
              {
                name: '',
                type: 'bar',
                stack: '',
                barWidth: 8,
                itemStyle: {
                  color: '#1456FE',
                  barBorderRadius: [0, 8, 8, 0]
                },
                label: {
                  normal: {
                    show: false,
                    position: 'insideRight'
                  }
                },
                data: [100, 90, 80, 70, 60, 50, 40, 30, 20, 15]
              },
              {
                name: '',
                type: 'bar',
                stack: '总量',
                barWidth: 8,
                itemStyle: {
                  color: '#1493FE',
                  barBorderRadius: [0, 8, 8, 0]
                },
                label: {
                  normal: {
                    show: false,
                    position: 'insideRight'
                  }
                },
                data: [100, 90, 80, 70, 60, 50, 40, 30, 20, 15]
              },
              {
                name: '',
                type: 'bar',
                barWidth: 8,
                stack: '总量',
                itemStyle: {
                  color: '#00CCFF',
                  barBorderRadius: [0, 8, 8, 0]
                },
                label: {
                  normal: {
                    show: false,
                    position: 'insideRight'
                  }
                },
                data: [100, 90, 80, 70, 60, 50, 40, 30, 20, 15]
              },
              {
                type: 'pie',
                radius: ['20%', '21%'],
                center: ['72%', '60%'],
                data: [{value: '1'}],
                label: {show: false},
                itemStyle: {
                  color: '#7D7DA2'
                }
              },
              {
                type: 'pie',
                radius: ['40%', '65%'],
                roseType: 'area',
                center: ['72%', '60%'],
                avoidLabelOverlap: true,
                startAngle: 180,
                label: {
                  normal: {
                    show: true,
                    padding: [0, -30],
                    formatter: '{c} \n\n',
                    position: 'outside',
                    color: '#fff'
                  },
                  emphasis: {
                    show: true,
                    textStyle: {
                      fontSize: '30',
                      fontWeight: 'bold'
                    }
                  }
                },
                labelLine: {
                  show: true,
                  length2: 30,
                  lineStyle: {
                    //color:["#408BE8",'#FE405C',"#3E3E7F","#FFC740"]
                  },

                },
                itemStyle: {
                  color: function (params) {
                    let corList = ["#142AFE", '#3FA0FF', "#00CCFF", "#1456FE","#142AFE", '#3FA0FF', "#00CCFF", "#1456FE","#00CCFF", "#1456FE"];
                    return corList[params.dataIndex]
                  }
                },
                data: [
                  {value: 535, name: '你好'},
                  {value: 310, name: '快手'},
                  {value: 135, name: '花椒'},
                  {value: 254, name: '其他'},
                  {value: 535, name: '抖音'},
                  {value: 310, name: '快手'},
                  {value: 135, name: '花椒'},
                  {value: 254, name: '其他'},
                  {value: 135, name: '花椒'},
                  {value: 254, name: '其他'},
                ]
              }
            ]
          }
        }
    },
    methods: {
        // 网播风险分析
        setWebcasts() {
            // let option = {
            //     title: {
            //         text: 'Number of Contributions',
            //         textStyle: {
            //             color: "#fff",
            //             fontSize: 12
            //         },
            //         top: '4%',
            //         left: '4%'
            //     },
            //     tooltip: {
            //         trigger: 'axis',
            //         axisPointer: {            // 坐标轴指示器，坐标轴触发有效
            //             type: 'shadow'        // 默认为直线，可选为：'line' | 'shadow'
            //         }
            //     },
            //     legend: {
            //         data: [
            //             {name: '', icon: 'circle'},
            //             {name: '', icon: 'circle'},
            //             {name: '', icon: 'circle'},
            //             {name: '', icon: 'circle'},
            //         ],
            //         gridIndex: 3,
            //         right: "5%",
            //         top: "6%",
            //         itemWidth: 7,
            //         itemHeight: 7,
            //         textStyle: {
            //             color: '#00CCFF',
            //             fontSize: 10
            //         }
            //     },
            //     grid: {
            //         top: '15%',
            //         left: '3%',
            //         right: '50%',
            //         bottom: '5%',
            //         containLabel: true
            //     },
            //     xAxis: {
            //         type: 'value',
            //         axisLabel: {show: false},
            //         axisTick: {show: false},
            //         splitLine: {show: false},
            //         axisLine: {show: false}
            //     },
            //     yAxis: {
            //         type: 'category',
            //         axisTick: {show: false},
            //         splitLine: {show: false},
            //         axisLine: {show: false},
            //         axisLabel: {
            //             color: '#fff',
            //             backgroundColor: '#4A7AFF',
            //             borderRadius: 3,
            //             margin: 0,
            //             padding: [1, 3, 1, 3]
            //         },
            //         inverse: true,
            //         data: ['1', '2', '3', '4', '5', '6', '7', '8', '9', '10']
            //     },
            //     series: [
            //         {
            //             name: '',
            //             type: 'bar',
            //             stack: '',
            //             barWidth: 8,
            //             itemStyle: {
            //                 color: '#142AFE',
            //                 barBorderRadius: [0, 8, 8, 0]
            //             },
            //             label: {
            //                 normal: {
            //                     show: false,
            //
            //                     position: 'insideRight'
            //                 }
            //             },
            //             data: [1, 1, 1, 1, 1, 1, 1, 1, 210, 15]
            //         },
            //         {
            //             name: '',
            //             type: 'bar',
            //             stack: '',
            //             barWidth: 8,
            //             itemStyle: {
            //                 color: '#1456FE',
            //                 barBorderRadius: [0, 8, 8, 0]
            //             },
            //             label: {
            //                 normal: {
            //                     show: false,
            //                     position: 'insideRight'
            //                 }
            //             },
            //             data: [100, 90, 80, 70, 60, 50, 40, 30, 20, 15]
            //         },
            //         {
            //             name: '',
            //             type: 'bar',
            //             stack: '总量',
            //             barWidth: 8,
            //             itemStyle: {
            //                 color: '#1493FE',
            //                 barBorderRadius: [0, 8, 8, 0]
            //             },
            //             label: {
            //                 normal: {
            //                     show: false,
            //                     position: 'insideRight'
            //                 }
            //             },
            //             data: [100, 90, 80, 70, 60, 50, 40, 30, 20, 15]
            //         },
            //         {
            //             name: '',
            //             type: 'bar',
            //             barWidth: 8,
            //             stack: '总量',
            //             itemStyle: {
            //                 color: '#00CCFF',
            //                 barBorderRadius: [0, 8, 8, 0]
            //             },
            //             label: {
            //                 normal: {
            //                     show: false,
            //                     position: 'insideRight'
            //                 }
            //             },
            //             data: [100, 90, 80, 70, 60, 50, 40, 30, 20, 15]
            //         },
            //         {
            //             type: 'pie',
            //             radius: ['20%', '21%'],
            //             center: ['72%', '60%'],
            //             data: [{value: '1'}],
            //             label: {show: false},
            //             itemStyle: {
            //                 color: '#7D7DA2'
            //             }
            //         },
            //         {
            //             type: 'pie',
            //             radius: ['40%', '65%'],
            //             roseType: 'area',
            //             center: ['72%', '60%'],
            //             avoidLabelOverlap: true,
            //             startAngle: 180,
            //             label: {
            //                 normal: {
            //                     show: true,
            //                     padding: [0, -30],
            //                     formatter: '{c} \n\n',
            //                     position: 'outside',
            //                     color: '#fff'
            //                 },
            //                 emphasis: {
            //                     show: true,
            //                     textStyle: {
            //                         fontSize: '30',
            //                         fontWeight: 'bold'
            //                     }
            //                 }
            //             },
            //             labelLine: {
            //                 show: true,
            //                 length2: 30,
            //                 lineStyle: {
            //                     //color:["#408BE8",'#FE405C',"#3E3E7F","#FFC740"]
            //                 },
            //
            //             },
            //             itemStyle: {
            //                 color: function (params) {
            //                     let corList = ["#142AFE", '#3FA0FF', "#00CCFF", "#1456FE"];
            //                     return corList[params.dataIndex]
            //                 }
            //             },
            //             data: [
            //                 {value: 535, name: '抖音'},
            //                 {value: 310, name: '快手'},
            //                 {value: 135, name: '花椒'},
            //                 {value: 254, name: '其他'},
            //             ]
            //         }
            //     ]
            // };
            let myChart = this.$echarts(this.$el);
            myChart.clear();
            myChart.resize();
            myChart.setOption(this.option);
          console.log("hha",this.option.yAxis.data[1])
        },
    },
    mounted() {
      console.log("11111111111111",this);
      // return 'asd'
      // if(this.props.msg=="pytorch"){
      //   axios.get(`http://localhost:8090/company/getPyTorchInfo`).then((response)=>{
      //     console.log(response)
      //     for(let i=0;i<10;i++){
      //       this.option.yAxis.data[i]=response.data[i]["domain"]
      //       this.option.series[0].data[i]=response.data[i]["contributions"]
      //       this.option.series[5].data[i].value=this.option.series[0].data[i]
      //     }
      //     this.setWebcasts()
      //   })
      // }else {
        axios.get(`http://localhost:8090/company/getTensorFlowInfo`).then((response)=>{
          console.log(response)
          for(let i=0;i<10;i++){
            this.option.yAxis.data[i]=response.data[i]["domain"]
            this.option.series[0].data[i]=response.data[i]["contributions"]
            this.option.series[5].data[i].value=this.option.series[0].data[i]
          }
          this.setWebcasts()
        })
      // }
    },
}
</script>

<style lang="less" scoped>
.webcastsRisk {
    height: 100%;
}
</style>
