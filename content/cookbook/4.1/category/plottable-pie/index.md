---
Title: Pie - ScottPlot 4.1 Cookbook
Description: Plottable - Pie recipes
Source: https://github.com/ScottPlot/ScottPlot/tree/master/src/cookbook
---

## Pie Chart

A pie chart illustrates numerical proportions as slices of a circle.

```cs
var plt = new ScottPlot.Plot(600, 400);

double[] values = { 778, 283, 184, 76, 43 };
plt.AddPie(values);

plt.SaveFig("pie_quickstart.png");
```

<div class='text-center'>
<a href='../../images/pie_quickstart.png'><img src='../../images/pie_quickstart.png' /></a>
</div>


<div class='m-2'>&nbsp;</div>

## Exploded Pie Chart

Exploded pie charts have a bit of space between their slices.

```cs
var plt = new ScottPlot.Plot(600, 400);

double[] values = { 778, 283, 184, 76, 43 };
var pie = plt.AddPie(values);
pie.Explode = true;

plt.SaveFig("pie_exploded.png");
```

<div class='text-center'>
<a href='../../images/pie_exploded.png'><img src='../../images/pie_exploded.png' /></a>
</div>


<div class='m-2'>&nbsp;</div>

## Donut Chart

Donut plots are pie charts with a hollow center.

```cs
var plt = new ScottPlot.Plot(600, 400);

double[] values = { 778, 283, 184, 76, 43 };
var pie = plt.AddPie(values);
pie.Explode = true;
pie.DonutSize = .6;

plt.SaveFig("pie_donut.png");
```

<div class='text-center'>
<a href='../../images/pie_donut.png'><img src='../../images/pie_donut.png' /></a>
</div>


<div class='m-2'>&nbsp;</div>

## Donut with Text

Custom text can be displayed in the center of a donut chart. Notice too how the colors of each slice are customized in this example.

```cs
var plt = new ScottPlot.Plot(600, 400);

double[] values = { 779, 586 };
string centerText = $"{values[0] / values.Sum() * 100:00.0}%";
Color color1 = Color.FromArgb(255, 0, 150, 200);
Color color2 = Color.FromArgb(100, 0, 150, 200);

var pie = plt.AddPie(values);
pie.DonutSize = .6;
pie.DonutLabel = centerText;
pie.CenterFont.Color = color1;
pie.OutlineSize = 2;
pie.SliceFillColors = new Color[] { color1, color2 };

plt.SaveFig("pie_donutText.png");
```

<div class='text-center'>
<a href='../../images/pie_donuttext.png'><img src='../../images/pie_donuttext.png' /></a>
</div>


<div class='m-2'>&nbsp;</div>

## Slice Values

The value of each slice can be displayed at its center.

```cs
var plt = new ScottPlot.Plot(600, 400);

double[] values = { 778, 43, 283, 76, 184 };
var pie = plt.AddPie(values);
pie.ShowValues = true;

plt.SaveFig("pie_showValues.png");
```

<div class='text-center'>
<a href='../../images/pie_showvalues.png'><img src='../../images/pie_showvalues.png' /></a>
</div>


<div class='m-2'>&nbsp;</div>

## Slice Percentages

The percentage of each slice can be displayed at its center.

```cs
var plt = new ScottPlot.Plot(600, 400);

double[] values = { 778, 43, 283, 76, 184 };
var pie = plt.AddPie(values);
pie.ShowPercentages = true;

plt.SaveFig("pie_showPercentage.png");
```

<div class='text-center'>
<a href='../../images/pie_showpercentage.png'><img src='../../images/pie_showpercentage.png' /></a>
</div>


<div class='m-2'>&nbsp;</div>

## Customize Pie Colors

Colors for pie slices and labels can be customized.

```cs
var plt = new ScottPlot.Plot(600, 400);

double[] values = { 778, 43, 283, 76, 184 };
string[] labels = { "C#", "JAVA", "Python", "F#", "PHP" };

// Language colors from https://github.com/ozh/github-colors
Color[] sliceColors =
{
    ColorTranslator.FromHtml("#178600"),
    ColorTranslator.FromHtml("#B07219"),
    ColorTranslator.FromHtml("#3572A5"),
    ColorTranslator.FromHtml("#B845FC"),
    ColorTranslator.FromHtml("#4F5D95"),
};

// Show labels using different transparencies
Color[] labelColors =
    new Color[] {
    Color.FromArgb(255, Color.White),
    Color.FromArgb(100, Color.White),
    Color.FromArgb(250, Color.White),
    Color.FromArgb(150, Color.White),
    Color.FromArgb(200, Color.White),
};

var pie = plt.AddPie(values);
pie.SliceLabels = labels;
pie.ShowLabels = true;
pie.SliceFillColors = sliceColors;
pie.SliceLabelColors = labelColors;

plt.SaveFig("pie_customColors.png");
```

<div class='text-center'>
<a href='../../images/pie_customcolors.png'><img src='../../images/pie_customcolors.png' /></a>
</div>


<div class='m-2'>&nbsp;</div>

## Slices in Legend

Slices can be labeled in the legend.

```cs
var plt = new ScottPlot.Plot(600, 400);

double[] values = { 778, 43, 283, 76, 184 };
string[] labels = { "C#", "JAVA", "Python", "F#", "PHP" };
var pie = plt.AddPie(values);
pie.SliceLabels = labels;
plt.Legend();

plt.SaveFig("pie_legend.png");
```

<div class='text-center'>
<a href='../../images/pie_legend.png'><img src='../../images/pie_legend.png' /></a>
</div>


<div class='m-2'>&nbsp;</div>

## Label Everything

Slices can labeled with values, percentages, and lables, with a legend.

```cs
var plt = new ScottPlot.Plot(600, 400);

double[] values = { 778, 43, 283, 76, 184 };
string[] labels = { "C#", "JAVA", "Python", "F#", "PHP" };
var pie = plt.AddPie(values);
pie.SliceLabels = labels;
pie.ShowPercentages = true;
pie.ShowValues = true;
pie.ShowLabels = true;
plt.Legend();

plt.SaveFig("pie_showEverything.png");
```

<div class='text-center'>
<a href='../../images/pie_showeverything.png'><img src='../../images/pie_showeverything.png' /></a>
</div>


<div class='m-2'>&nbsp;</div>

## Custom Slice Labels

Custom slice labels can be used to display values using custom formats

```cs
var plt = new ScottPlot.Plot(600, 400);

double[] values = { 778, 43, 283, 76, 184 };
string[] labels = { "C#", "JAVA", "Python", "F#", "PHP" };

// modify labels to include a custom formatted value
labels = Enumerable.Range(0, values.Length)
       .Select(i => $"{labels[i]}\n({values[i]})")
       .ToArray();

var pie = plt.AddPie(values);
pie.SliceLabels = labels;
pie.ShowLabels = true;

plt.SaveFig("pie_customLabels.png");
```

<div class='text-center'>
<a href='../../images/pie_customlabels.png'><img src='../../images/pie_customlabels.png' /></a>
</div>
