# Highcharts Wrapper
[![npm](https://img.shields.io/npm/l/express.svg?style=flat-square)]()
[![react](https://img.shields.io/badge/React-Native-yellow.svg)]()

A react-native wrapper module for highcharts.

## Note
A modified version of [this module](https://github.com/TradingPal/react-native-highcharts). Native-highcharts-wrapper works better for dynamic data coming from API calls since the previous module/highcharts implementation would not accept data within the configuration that was null.

## Installation
`npm install native-highcharts-wrapper --save`

## Demo
![](https://i.gyazo.com/093481c6af328fda4e5153319b1bcb08.gif)

## Example Implementation
```javascript
render() {
  var Highcharts='Highcharts';
  const exampleConfig = {
      chart: {
          plotBackgroundColor: null,
          plotBorderWidth: null,
          plotShadow: false,
          type: 'pie'
      },
      title: {
          text: 'Browser market shares January, 2015 to May, 2015'
      },
      tooltip: {
          pointFormat: '{series.name}: <b>{point.percentage:.1f}%</b>'
      },
      plotOptions: {
          pie: {
              allowPointSelect: true,
              cursor: 'pointer',
              dataLabels: {
                  enabled: true,
                  format: '<b>{point.name}</b>: {point.percentage:.1f} %',
                  style: {
                      color: (Highcharts.theme && Highcharts.theme.contrastTextColor) || 'black'
                  }
              }
          }
      },
      series: [{
          name: 'Brands',
          colorByPoint: true,
          data: [{
              name: 'Microsoft Internet Explorer',
              y: 56.33
          }, {
              name: 'Chrome',
              y: 24.03,
              sliced: true,
              selected: true
          }, {
              name: 'Firefox',
              y: 10.38
          }, {
              name: 'Safari',
              y: 4.77
          }, {
              name: 'Opera',
              y: 0.91
          }, {
              name: 'Proprietary or Undetectable',
              y: 0.2
          }]
      }]
  }
  return (
    <ChartView style={{height:400}} config={exampleConfig}></ChartView>
  );
}
```

## Example Results

![](http://www.jacobsteves.ca/images/pieChart.gif)

## Props
| Prop          | Required      | Description  |
| ------------- |:-------------:| ------------:|
| config        | true          | Highcharts configuration [See the docs.>>](http://www.highcharts.com/docs/getting-started/your-first-chart)  |
| stock     | false      |   Default false; use Highstock |
| style | false      |   Style object to be passed onto the WebView |
