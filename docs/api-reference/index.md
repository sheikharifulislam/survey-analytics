---
title: Classes and Interfaces
product: Dashboard
---

# SurveyJS Dashboard API Reference

## Classes

- [`VisualizerBase`](https://surveyjs.io/dashboard/documentation/api-reference/visualizerbase.md) — A base object for all visualizers.
- [`VisualizationPanel`](https://surveyjs.io/dashboard/documentation/api-reference/visualizationpanel.md) — An object that visualizes survey results and allows users to analyze them.
- [`VisualizationManager`](https://surveyjs.io/dashboard/documentation/api-reference/visualizationmanager.md) — An object with methods used to register and unregister visualizers for individual question types.
- [`LayoutEngine`](https://surveyjs.io/dashboard/documentation/api-reference/layoutengine.md) — A base class used to implement custom layout engines or integrate third-party layout engines with SurveyJS Dashboard.
- [`VisualizerFactory`](https://surveyjs.io/dashboard/documentation/api-reference/visualizerfactory.md) — An object that allows you to create individual visualizers without creating a visualization panel.

## Interfaces

- [`IVisualizationPanelOptions`](https://surveyjs.io/dashboard/documentation/api-reference/ivisualizationpaneloptions.md) — Visualization Panel configuration.
- [`IVisualizerPanelElement`](https://surveyjs.io/dashboard/documentation/api-reference/ivisualizerpanelelement.md) — An interface that describes a visualization item (chart, gauge, etc.).
