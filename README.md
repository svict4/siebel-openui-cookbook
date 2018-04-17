# 🛠️🖥️ Siebel OpenUI API Methods cookbook

[![WiP](https://img.shields.io/badge/Stability-Work_in_Progress-Orange.svg)](https://img.shields.io/badge/Stability-Work_in_Progress-Orange.svg)

An awesome *collection* [(not curation)](https://github.com/sindresorhus/awesome/blob/master/awesome.md) of helpful Siebel OpenUI API Methods to help you debug your OpenUI application.

NB: Siebel may or may not be awesome.

### Get Current View Name:

Clicking on a component/list/applet and running the below JS will return the View Name, which you can then lookup in `🛠️ Siebel Tools`

```javascript
SiebelApp.S_App.GetActiveView().GetName()
```

### Get Component Tree:

```javascript
SiebelAppFacade.ComponentMgr.DisplayTree()
```
    
### Get Current List of Applets within Active View:

```javascript
SiebelApp.S_App.GetActiveView().GetAppletMap()
```

### Get Component:
   
```javascript
SiebelAppFacade.ComponentMgr.FindComponent(/*SiebelApp.S_App.GetActiveView().GetName()*/)
```

#### and it's PM (Presentation Model) object which is an abstraction of the metadata for each UI piece

```javascript
SiebelAppFacade.ComponentMgr.FindComponent(/*SiebelApp.S_App.GetActiveView().GetName()*/).GetPM()
```

#### and it's PR (Physical Renderer) that binds to the PM to generate/render the actual HTML

```javascript
SiebelAppFacade.ComponentMgr.FindComponent(/*SiebelApp.S_App.GetActiveView().GetName()*/).GetPR().constructor
```
