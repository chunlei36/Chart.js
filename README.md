# Chart.js

[![Build Status](https://travis-ci.org/chartjs/Chart.js.svg?branch=master)](https://travis-ci.org/chartjs/Chart.js) [![Code Climate](https://codeclimate.com/github/nnnick/Chart.js/badges/gpa.svg)](https://codeclimate.com/github/nnnick/Chart.js) [![Coverage Status](https://coveralls.io/repos/github/chartjs/Chart.js/badge.svg?branch=master)](https://coveralls.io/github/chartjs/Chart.js?branch=master)

[![Chart.js on Slack](https://img.shields.io/badge/slack-Chart.js-blue.svg)](https://chart-js-automation.herokuapp.com/)

*Simple HTML5 Charts using the canvas element* [chartjs.org](http://www.chartjs.org)

## Installation

You can download the latest version of Chart.js from the [GitHub releases](https://github.com/chartjs/Chart.js/releases/latest) or use a [Chart.js CDN](https://cdnjs.com/libraries/Chart.js).

To install via npm:

```bash
npm install chart.js --save
```

To install via bower:
```bash
bower install chart.js --save
```

#### Selecting the Correct Build

Chart.js provides two different builds that are available for your use. The `Chart.js` and `Chart.min.js` files include Chart.js and the accompanying color parsing library. If this version is used and you require the use of the time axis, [Moment.js](http://momentjs.com/) will need to be included before Chart.js.

The `Chart.bundle.js` and `Chart.bundle.min.js` builds include Moment.js in a single file. This version should be used if you require time axes and want a single file to include, select this version. Do not use this build if your application already includes Moment.js. If you do, Moment.js will be included twice, increasing the page load time and potentially introducing version issues.

## Documentation

You can find documentation at [www.chartjs.org/docs](http://www.chartjs.org/docs). The markdown files that build the site are available under `/docs`. Previous version documentation is available at [www.chartjs.org/docs/#notes-previous-versions](http://www.chartjs.org/docs/#notes-previous-versions).

## Contributing

Before submitting an issue or a pull request to the project, please take a moment to look over the [contributing guidelines](https://github.com/chartjs/Chart.js/blob/master/CONTRIBUTING.md) first.

For support using Chart.js, please post questions with the [`chartjs` tag on Stack Overflow](http://stackoverflow.com/questions/tagged/chartjs).

## Building and Testing

To build, run `gulp build`.

To test, run `gulp test`.

To test against code standards, run `gulp lint`.

More information on building and testing can be found in [gulpfile.js](gulpfile.js).

Thanks to [BrowserStack](https://browserstack.com) for allowing our team to test on thousands of browsers.

## License

Chart.js is available under the [MIT license](http://opensource.org/licenses/MIT).

===================================
## 做图表，基于canvas
## 官网：http://www.chartjs.org


The MIT License (MIT)

Copyright (c) 2013-2017 Nick Downie

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.


==============================
## demo
练习：
		<canvas id="cvs"></canvas>
		<script src="Chart.min.js" type="text/javascript" charset="utf-8"></script>
		<script type="text/javascript">
			var ctx = cvs.getContext('2d')
//			var ctx = document.getElementById("cvs");  和上面等效，但只能用于chart中
			var myChart = new Chart(ctx, {
				type: 'radar',   数据的展现形式，更多见githup
				data: {
					labels: ["Red", "Blue", "Yellow", "Green", "Purple", "Orange"],
					datasets: [{
						label: '# of Votes',
						data: [12, 19, 3, 5, 2, 3],
						backgroundColor: [
							'rgba(255, 99, 132, 0.2)',
							'rgba(54, 162, 235, 0.2)',
							'rgba(255, 206, 86, 0.2)',
							'rgba(75, 192, 192, 0.2)',
							'rgba(153, 102, 255, 0.2)',
							'rgba(255, 159, 64, 0.2)'
						],
						borderColor: [
							'rgba(255,99,132,1)',
							'rgba(54, 162, 235, 1)',
							'rgba(255, 206, 86, 1)',
							'rgba(75, 192, 192, 1)',
							'rgba(153, 102, 255, 1)',
							'rgba(255, 159, 64, 1)'
						],
						borderWidth: 1
					}]
				},
				options: {
					scales: {
						yAxes: [{ticks: {beginAtZero: true}}]  
// beginAtZero ：
true：是y轴从0开始
false：默认值，从指定数据开始，不一定为0
					}
				}
			});	</script>
			
			






