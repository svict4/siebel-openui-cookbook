# 🛠️🖥️ Awesome Siebel OpenUI Methods

[![WiP](https://img.shields.io/badge/Stability-Work_in_Progress-Orange.svg)](https://img.shields.io/badge/Stability-Work_in_Progress-Orange.svg)

An awesome *collection* [(not curation)](https://github.com/sindresorhus/awesome/blob/master/awesome.md) of helpful Siebel OpenUI API Methods to help you debug your OpenUI application.

NB: Siebel may or may not be awesome.

### Get Current View Name:

```SiebelApp.S_App.GetActiveView().GetName()```

### Get Component Tree:

```SiebelAppFacade.ComponentMgr.DisplayTree()```
    
### Get Current List of Applets within Active View:

```SiebelApp.S_App.GetActiveView().GetAppletMap()```

### Get Component:
   
```SiebelAppFacade.ComponentMgr.FindComponent(/*SiebelApp.S_App.GetActiveView().GetName()*/)```

#### and it's PM (Presentation Model) object which is an abstraction of the metadata for each UI piece

```SiebelAppFacade.ComponentMgr.FindComponent(/*SiebelApp.S_App.GetActiveView().GetName()*/).GetPM()```

#### and it's PR (Physical Renderer) that binds to the PM to generate/render the actual HTML

```SiebelAppFacade.ComponentMgr.FindComponent(/*SiebelApp.S_App.GetActiveView().GetName()*/).GetPR().constructor```




