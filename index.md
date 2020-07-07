## Welcome to GitHub Pages
<html>
  <head>
    <script type="text/javascript" src="https://www.gstatic.com/charts/loader.js"></script>
    <script type="text/javascript">
      google.charts.load('current', {'packages':['corechart', 'controls']});
      google.charts.setOnLoadCallback(drawStuff);

      function drawStuff() {

        var dashboard = new google.visualization.Dashboard(
          document.getElementById('programmatic_dashboard_div'));

        // We omit "var" so that programmaticSlider is visible to changeRange.
        var programmaticSlider = new google.visualization.ControlWrapper({
          'controlType': 'NumberRangeFilter',
          'containerId': 'programmatic_control_div',
          'options': {
            'filterColumnLabel': 'Donuts eaten',
            'ui': {'labelStacking': 'vertical'}
          }
        });

        var programmaticChart  = new google.visualization.ChartWrapper({
          'chartType': 'PieChart',
          'containerId': 'programmatic_chart_div',
          'options': {
            'width': 300,
            'height': 300,
            'legend': 'none',
            'chartArea': {'left': 15, 'top': 15, 'right': 0, 'bottom': 0},
            'pieSliceText': 'value'
          }
        });

        var data = google.visualization.arrayToDataTable([
          ['Name', 'Donuts eaten'],
          ['Michael' , 5],
          ['Elisa', 7],
          ['Robert', 3],
          ['John', 2],
          ['Jessica', 6],
          ['Aaron', 1],
          ['Margareth', 8]
        ]);

        dashboard.bind(programmaticSlider, programmaticChart);
        dashboard.draw(data);

        changeRange = function() {
          programmaticSlider.setState({'lowValue': 2, 'highValue': 5});
          programmaticSlider.draw();
        };

        changeOptions = function() {
          programmaticChart.setOption('is3D', true);
          programmaticChart.draw();
        };
      }

    </script>
  </head>
  <body>
    <div id="programmatic_dashboard_div" style="border: 1px solid #ccc">
      <table class="columns">
        <tr>
          <td>
            <div id="programmatic_control_div" style="padding-left: 2em; min-width: 250px"></div>
            <div>
              <button style="margin: 1em 1em 1em 2em" onclick="changeRange();">
                Select range [2, 5]
              </button><br />
              <button style="margin: 1em 1em 1em 2em" onclick="changeOptions();">
                Make the pie chart 3D
              </button>
            </div>
          </td>
          <td>
            <div id="programmatic_chart_div"></div>
          </td>
        </tr>
      </table>
    </div>
  </body>
</html>

<html>
  <head>
    <!--Load the AJAX API-->
    <script type="text/javascript" src="https://www.gstatic.com/charts/loader.js"></script>
    <script type="text/javascript">

      // Load the Visualization API and the corechart package.
      google.charts.load('current', {'packages':['corechart']});

      // Set a callback to run when the Google Visualization API is loaded.
      google.charts.setOnLoadCallback(drawChart);

      // Callback that creates and populates a data table,
      // instantiates the pie chart, passes in the data and
      // draws it.
      function drawChart() {

        // Create the data table.
        var data = new google.visualization.DataTable();
        data.addColumn('string', 'Topping');
        data.addColumn('number', 'Slices');
        data.addRows([
          ['Mushrooms', 3],
          ['Onions', 1],
          ['Olives', 1],
          ['Zucchini', 1],
          ['Pepperoni', 2]
        ]);

        // Set chart options
        var options = {'title':'How Much Pizza I Ate Last Night',
                       'width':400,
                       'height':300};

        // Instantiate and draw our chart, passing in some options.
        var chart = new google.visualization.PieChart(document.getElementById('chart_div'));
        chart.draw(data, options);
      }
    </script>
  </head>

  <body>
    <!--Div that will hold the pie chart-->
    <div id="chart_div"></div>
  </body>
</html>
<iframe width="600" height="371" seamless frameborder="0" scrolling="no" src="https://docs.google.com/spreadsheets/d/e/2PACX-1vRHu8XNyNkIQ9TIptW2JPEafZ17U1B2Qo760PA7noA1oAiMGafaAkGYXlgMr7z-5yxgFO7NcRVQeB_4/pubchart?oid=162509870&amp;format=interactive"></iframe>
<iframe src="https://trinket.io/embed/python3/f2333dfa63?runOption=console" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

You can use the [editor on GitHub](https://github.com/richjriley/richjriley.github.io/edit/master/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/richjriley/richjriley.github.io/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
