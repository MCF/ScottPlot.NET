---
Title: Grid Customization - ScottPlot 5.0 Cookbook
Description: Grid lines can be customized. Custom grid systems can be created to give developers full control of grid rendering, but the default grid can be interacted with to customize its appearance.
URL: /cookbook/5.0/CustomizingGrids/GridCustom/
BreadcrumbNames: ["ScottPlot 5.0 Cookbook", "Customizing Grids", "Grid Customization"]
BreadcrumbUrls: ["/cookbook/5.0/", "/cookbook/5.0/CustomizingGrids", "/cookbook/5.0/CustomizingGrids/GridCustom"]
Date: 2024-01-08
Version: ScottPlot 5.0.11-beta
Version: ScottPlot 5.0.11-beta
SearchUrl: "/cookbook/5.0/search/"
---

# Grid Customization



<div class='alert alert-warning' role='alert'><h4 class='alert-heading py-0 my-0'>⚠️ ScottPlot 5.0.11-beta is a preview package</h4><hr /><p class='mb-0'><span class='fw-semibold'>This page describes a beta release of ScottPlot.</span> It is available on NuGet as a preview package, but its API is not stable and it is not recommended for production use. See the <a href='https://scottplot.net/versions/'>ScottPlot Versions</a> page for more information. </p></div>



Grid lines can be customized. Custom grid systems can be created to give developers full control of grid rendering, but the default grid can be interacted with to customize its appearance.

[![](/cookbook/5.0/images/GridCustom.png)](/cookbook/5.0/images/GridCustom.png)

```cs
ScottPlot.Version.ShouldBe(5, 0, 11);
ScottPlot.Plot myPlot = new();

myPlot.Add.Signal(ScottPlot.Generate.Sin(51));
myPlot.Add.Signal(ScottPlot.Generate.Cos(51));

ScottPlot.Grids.DefaultGrid grid = myPlot.GetDefaultGrid();

grid.MajorLineStyle.Color = Colors.Green.WithOpacity(.5);
grid.MinorLineStyle.Color = Colors.Green.WithOpacity(.1);
grid.MinorLineStyle.Width = 1;

myPlot.SavePng("demo.png");

```
