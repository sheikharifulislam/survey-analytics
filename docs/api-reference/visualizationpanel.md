---
title: VisualizationPanel
product: Dashboard
api-type: class
description: An object that visualizes survey results and allows users to analyze them.
source: https://surveyjs.io/dashboard/documentation/api-reference/visualizationpanel
---

# `VisualizationPanel`

An object that visualizes survey results and allows users to analyze them.

Constructor parameters:

- `questions`: Array\<[`Question`](https://surveyjs.io/form-library/documentation/api-reference/question)\>\
Survey questions to visualize. Call `SurveyModel`'s [`getAllQuestions()`](https://surveyjs.io/form-library/documentation/api-reference/survey-data-model#getQuestionByName) method to access all survey questions and pass its result as the `questions` parameter.
- `data`: `Array<any>`\
Survey results.
- `vizPanelOptions`: [`IVisualizationPanelOptions`](https://surveyjs.io/dashboard/documentation/api-reference/ivisualizationpaneloptions)\
Visualization Panel configuration.

[View Demo](https://surveyjs.io/dashboard/examples/interactive-survey-data-dashboard/ (linkStyle))

## Inheritance

[`VisualizerBase`](https://surveyjs.io/dashboard/documentation/api-reference/visualizerbase.md) &rarr; `VisualizationPanel`

## Properties

### `allowDragDrop`

**Type**: `boolean`

Returns the [`allowDragDrop`](https://surveyjs.io/dashboard/documentation/api-reference/ivisualizationpaneloptions#allowDragDrop) property value of the [`IVisualizationPanelOptions`](https://surveyjs.io/dashboard/documentation/api-reference/ivisualizationpaneloptions) object.

### `allowDynamicLayout`

**Type**: `boolean`

Returns the [`allowDynamicLayout`](https://surveyjs.io/dashboard/documentation/api-reference/ivisualizationpaneloptions#allowDynamicLayout) property value of the [`IVisualizationPanelOptions`](https://surveyjs.io/dashboard/documentation/api-reference/ivisualizationpaneloptions) object.

### `allowHideQuestions`

**Type**: `boolean`

Returns the [`allowHideQuestions`](https://surveyjs.io/dashboard/documentation/api-reference/ivisualizationpaneloptions#allowHideQuestions) property value of the [`IVisualizationPanelOptions`](https://surveyjs.io/dashboard/documentation/api-reference/ivisualizationpaneloptions) object.

### `hiddenElements`

**Type**: `any`

Returns an array of [`IVisualizerPanelElement`](https://surveyjs.io/dashboard/documentation/api-reference/ivisualizerpanelelement) objects with information about currently hidden visualization items.

If you want to disallow users to hide visualization items, set the [`allowHideQuestions`](https://surveyjs.io/dashboard/documentation/api-reference/ivisualizationpaneloptions#allowHideQuestions) property to `false`.

**Related APIs:** [`visibleElements`](#visibleElements), [`getElements`](#getElements)

### `layoutEngine`

**Type**: `LayoutEngine`

Returns a [`LayoutEngine`](https://surveyjs.io/dashboard/documentation/api-reference/layoutengine) instance used to arrange visualization items on `VisualizationPanel`.

### `state`

**Type**: `IState`

The state of `VisualizationPanel`. Includes information about the visualized elements and current locale.

[View Demo](https://surveyjs.io/dashboard/examples/save-dashboard-state-to-local-storage/ (linkStyle))

**Related APIs:** [`onStateChanged`](#onStateChanged)

### `visibleElements`

**Type**: `any`

Returns an array of [`IVisualizerPanelElement`](https://surveyjs.io/dashboard/documentation/api-reference/ivisualizerpanelelement) objects with information about currently visible visualization items.

If you want to disallow users to hide visualization items, set the [`allowHideQuestions`](https://surveyjs.io/dashboard/documentation/api-reference/ivisualizationpaneloptions#allowHideQuestions) property to `false`.

**Related APIs:** [`hiddenElements`](#hiddenElements), [`getElements`](#getElements)

## Methods

### `getElement()`

**Return value:** `any`

Returns a visualization item with a specified question name.

**Parameters:**

| Name | Type | Description |
| ---- | ---- | ----------- |
| `questionName` | `string` |  |

### `getElements()`

**Return value:** `Array<IVisualizerPanelElement>`

Returns an array of [`IVisualizerPanelElement`](https://surveyjs.io/dashboard/documentation/api-reference/ivisualizerpanelelement) objects with information about visualization items.

**Parameters:**

| Name | Type | Description |
| ---- | ---- | ----------- |
| `questionNames` | `Array<string>` | Question [names](https://surveyjs.io/form-library/documentation/api-reference/question#name). Do not specify this parameter to get an array of all visualization items. |

**Related APIs:** [`visibleElements`](#visibleElements), [`hiddenElements`](#hiddenElements)

### `getVisualizer()`

**Return value:** `any`

Returns a [visualizer](https://surveyjs.io/dashboard/documentation/api-reference/visualizerbase) that visualizes a specified survey question.

**Parameters:**

| Name | Type | Description |
| ---- | ---- | ----------- |
| `questionName` | `string` | A question [name](https://surveyjs.io/form-library/documentation/api-reference/question#name). |

### `hideAllElements()`

Hides all panel elements. Users can select the elements they want to show from a drop-down menu.

**Related APIs:** [`showAllElements`](#showAllElements), [`allowHideQuestions`](#allowHideQuestions)

### `refresh()`

Redraws the `VisualizationPanel` and all its content.

### `setFilter()`

Filters visualized data based on a specified question name and value. This method is called when a user clicks a chart point.

**Parameters:**

| Name | Type | Description |
| ---- | ---- | ----------- |
| `questionName` | `string` | A question [name](https://surveyjs.io/form-library/documentation/api-reference/question#name). |
| `selectedValue` | `any` |  |

**Related APIs:** [`IVisualizationPanelOptions.allowSelection`](#IVisualizationPanelOptions.allowSelection)

### `showAllElements()`

Shows all panel elements if they are hidden to a drop-down menu.

**Related APIs:** [`hideAllElements`](#hideAllElements), [`allowHideQuestions`](#allowHideQuestions)

## Events

### `onAlternativeVisualizerChanged`

An event that is raised when a user selects a different visualizer type from the Type drop-down menu.

Parameters:

- `sender`: `AlternativeVisualizersWrapper`\
An object that controls altenative visualizers.

- `options.visualizer`: `VisualizerBase`\
An applied visualizer.

### `onElementHidden`

An event that is raised when users [hide a visualization item](https://surveyjs.io/dashboard/documentation/api-reference/ivisualizationpaneloptions#allowHideQuestions).

Parameters:

- `sender`: [`VisualizationPanel`](https://surveyjs.io/dashboard/documentation/api-reference/visualizationpanel)\
A `VisualizationPanel` that raised the event.

- `options.elements`: Array\<[`IVisualizerPanelElement`](https://surveyjs.io/dashboard/documentation/api-reference/ivisualizerpanelelement)\>\
Information about all visualization items rendered by this `VisualizationPanel`.

- `options.element`: [`IVisualizerPanelElement`](https://surveyjs.io/dashboard/documentation/api-reference/ivisualizerpanelelement)\
A visualization item that has been hidden.

### `onElementMoved`

An event that is raised when users [move a visualization item](https://surveyjs.io/dashboard/documentation/api-reference/ivisualizationpaneloptions#allowDynamicLayout).

Parameters:

- `sender`: [`VisualizationPanel`](https://surveyjs.io/dashboard/documentation/api-reference/visualizationpanel)\
A `VisualizationPanel` that raised the event.

- `options.elements`: Array\<[`IVisualizerPanelElement`](https://surveyjs.io/dashboard/documentation/api-reference/ivisualizerpanelelement)\>\
Information about all visualization items rendered by this `VisualizationPanel`.

- `options.element`: [`IVisualizerPanelElement`](https://surveyjs.io/dashboard/documentation/api-reference/ivisualizerpanelelement)\
A visualization item that has been moved.

### `onElementShown`

An event that is raised when users [show a visualization item](https://surveyjs.io/dashboard/documentation/api-reference/ivisualizationpaneloptions#allowHideQuestions).

Parameters:

- `sender`: [`VisualizationPanel`](https://surveyjs.io/dashboard/documentation/api-reference/visualizationpanel)\
A `VisualizationPanel` that raised the event.

- `options.elements`: Array\<[`IVisualizerPanelElement`](https://surveyjs.io/dashboard/documentation/api-reference/ivisualizerpanelelement)\>\
Information about all visualization items rendered by this `VisualizationPanel`.

- `options.element`: [`IVisualizerPanelElement`](https://surveyjs.io/dashboard/documentation/api-reference/ivisualizerpanelelement)\
A visualization item that has been shown.
