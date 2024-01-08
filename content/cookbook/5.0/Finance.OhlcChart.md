---
Title: OHLC Chart - ScottPlot 5.0 Cookbook
Description: OHLC charts use symbols to display price data (open, high, low, and close) for specific time ranges.
URL: /cookbook/5.0/Finance/OhlcChart/
BreadcrumbNames: ["ScottPlot 5.0 Cookbook", "Financial Plot", "OHLC Chart"]
BreadcrumbUrls: ["/cookbook/5.0/", "/cookbook/5.0/Finance", "/cookbook/5.0/Finance/OhlcChart"]
Date: 2024-01-08
Version: ScottPlot 5.0.11-beta
Version: ScottPlot 5.0.11-beta
SearchUrl: "/cookbook/5.0/search/"
---

# OHLC Chart



<div class='alert alert-warning' role='alert'><h4 class='alert-heading py-0 my-0'>⚠️ ScottPlot 5.0.11-beta is a preview package</h4><hr /><p class='mb-0'><span class='fw-semibold'>This page describes a beta release of ScottPlot.</span> It is available on NuGet as a preview package, but its API is not stable and it is not recommended for production use. See the <a href='https://scottplot.net/versions/'>ScottPlot Versions</a> page for more information. </p></div>



OHLC charts use symbols to display price data (open, high, low, and close) for specific time ranges.

[![](/cookbook/5.0/images/OhlcChart.png)](/cookbook/5.0/images/OhlcChart.png)

```cs
ScottPlot.Version.ShouldBe(5, 0, 11);
ScottPlot.Plot myPlot = new();

var prices = Generate.RandomOHLCs(30);
myPlot.Add.OHLC(prices);
myPlot.Axes.DateTimeTicks(Edge.Bottom);

myPlot.SavePng("demo.png");

```
