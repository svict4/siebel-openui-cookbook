

## # 🛠️🖥️ Siebel OpenUI API Methods cookbook

[![WiP](https://img.shields.io/badge/Stability-Work_in_Progress-Orange.svg)](https://img.shields.io/badge/Stability-Work_in_Progress-Orange.svg) [![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com) 

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

Will return a Node tree, for example:

```
VM712:1   Proxy Node -> o
VM712:1     Proxy Node -> et
VM712:1       Proxy Node -> p
VM712:1       Component Node -> Left Pane Menu Items Applet
VM712:1       Component Node -> Manage Practice Standards Outcome Form Applet
VM712:1       Component Node -> Practice Standards Outcome List Applet
VM712:1       Component Node -> Left Pane Details Form Applet
VM712:1       Component Node -> Portal Practice Standards Header List Applet
VM712:1       Component Node -> Practice Standards Outcome Export List Applet
VM712:1       Component Node -> Application Playbar Applet
VM712:1       Component Node -> Practice Standards Header Export List Applet
VM712:1     Component Node -> Site Container Page
VM712:1     Component Node -> Pages Standalone Applet
VM712:1     Component Node -> Portal Application Practice Standards List View
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

## WCAG Helpers

Depending on your version of OpenUI, you may encounter several WCAG defects. Hopefully these snippets help you zero-in on those defects:

### Find duplicate IDs

```javascript
$(function() {
  $('[id]').each(function() {
    var ids = $('[id="' + this.id + '"]');
    if (ids.length > 1 && ids[0] == this)
      console.warn('Multiple IDs #' + this.id);
  });
})
```
