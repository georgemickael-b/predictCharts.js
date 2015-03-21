<h1>predictcharts.js</h1>
Charting library which predicts and graphs based on known input data (regression).

##Setup
<ol>
  <li>Download <a href="http://d3js.org/" target="_blank">d3.js</a> and predictCharts.js</li> 
  <li>
    Include the libraries.<br>
    <code>
      &lt;script src="path/to/d3.min.js"&gt;&lt;/script&gt; 
    </code><br>
    <code>
      &lt;script src="path/to/predictCharts.js"&gt;&lt;/script&gt;
    </code>
  </li>
  <li>
    Make a div for the chart.<br>
    <code> &lt;div id="predictChart" style="height:500px;width:600px;"&gt;&lt;/div&gt;</code>
  </li>
</ol>

##An Example
```
<div id="predictChart" style="height:500px;width:600px;"></div>
<script>

		var data={
					x:['xData',1,2,3,4,5,6],
					y:['yData',
						['data1', 30, 200, 100, 400, 150, 250],
						['data2', 50, 20, 10, 40, 15, 25]
					],
					predict:[7,8,9],
					secondAxis:false,
					type:'bar',
					//types:{'data2':'spline'},
					groups: [
								['data1', 'data2']
					]
		};
	predictCharts("#predictChart",data);
</script>
```
##Calling predictCharts
`predictCharts("#id-of-the-chart-div",data);`
##Preparing Data
 Data should be json that contains the follwing key-value pairs.
<table>
  <tr>
      <td>x:['axis-name',val1,val2,...] </td><td>Array of independent variable's values with first element as name of       axis.</td>
  </tr>
  <tr>
      <td>y:['axis-name',['variable-1-name',val1,val2,...],[...],...] </td><td>Array of dependent values with first element as name and rest as arrays,each corresponding to one dependent variable. </td>
  </tr>
  <tr>
     <td> predict:[val1,val2,...] </td><td>Array of independent values for which dependent values ahouls be found.</td>
  </tr>
  <tr>
    <td>type:'bar'|'line'|'spline'|'area'|'area-spline'|'scatter'</td><td></td>
  </tr>
  <tr>
    <td>type:{'variable-1-name':'type','variable-2-name':'type',..} </td><td>Incase you want different types for different variables.Key value pairs, where 'type' can be any one of the above types.</td>
  </tr>
  <tr>
    <td>secondAxis:true/false </td><td> Optional.Can be set in case of multiple dependent variables.</td>
  </tr>
 <tr>
    <td>groups:[['varible-1-name','varible-2-name',...],[...],...] </td><td>Array of arrays , where each array conatins the variabes that need to be grouped together.Many groups can be formed.Used mainly for stacked bar charts.</td>
 </tr>
</table>
