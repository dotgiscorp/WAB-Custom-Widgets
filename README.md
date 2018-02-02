# Web App Builder Custom Widgets

Adrián Pérez Beneito Web App builder Custom Widget List


## Bar Chart Cedar :bar_chart: [live demo](https://adrisolid.github.io/CedarWidget/)
See [Cedar.js](https://esri.github.io/cedar/tutorial/) and how to create charts using ArcGIS Geoservices. Pre-coded Web App Builder 2.6 Chart Widget doesn't allow you to create charts on the fly. You can select the available layers in the Web Map. Choose, for the 'x' axis, the field you want to show information, repeat the procedure for the 'y' axis. Select the type of graphic, bars or horizontal bars. The widget is ready to filter the data by extension (by activating the check button). Inside the container of the widget, the graphic will be updated being this responsive.

![.](http://adri2c.maps.arcgis.com/sharing/rest/content/items/25a901a69bc3449a9658ddd1386bb444/data)

Don't forget to add the [Cedar dependencies](https://github.com/esri/cedar#loading-cedar). [How to add other libraries to WAB?](https://developers.arcgis.com/web-appbuilder/sample-code/add-a-third-party-library.htm)

**Version 1.2**, pending improvements. All suggestions for improvement will be welcome.

**List of the latest enhancements and changes:**
- Added a new class => select the layers ids from the Web Map (Dojo Select) => geometry icon


***

## IntroJS ft WAB :dizzy: [live demo](https://adrisolid.github.io/IntroJS/)
### Why using [intro.js](https://introjs.com/)?
When new users visit your website or product you should demonstrate your product features using a step-by-step guide. Even when you develop and add a new feature to your product, you should be able to represent them to your users using a user-friendly solution. Intro.js is developed to enable web and mobile developers to create a step-by-step introduction easily.

![.](http://adri2c.maps.arcgis.com/sharing/rest/content/items/486a97c81a394212b4a059c80667f275/data)

### Integration with a Web App Builder app

**Add [intro.js dependencies](https://github.com/usablica/intro.js/#introjs-v290)**

**Create the configuration js file and refer to it in the application in the file 'index.html'**
Explore and get with the console the id/classes names of the containers to which you want to add as a step. Fill the 'intro' and 'position' options:
```
function getNode(node){
    //Getting ids or classes cleanly
    return document.querySelector(node);
}

function initIntro(){
    introJs().setOptions({
        steps: [{
                intro: "Hello Web App Builder, I'm IntroJS, wanna join me? :)"
            },
            {
                element: getNode('#widgets_Search_Widget_3'),
                intro: "The Search widget enables end users to find locations or search features on the map.",
                position: 'bottom'
            }
            .
            .
            .
        ]
    }).start();
}
```
**Call the 'initIntro' function**
Simply add a button that calls the function. For example, go to the 'HeaderController' widget:

- Add the button at the container (Widget.html):

```
<div class="container-section jimu-float-leading" data-dojo-attach-point="containerNode">
    <button data-dojo-attach-point="executeIntroJS" type="button"></button>
</div>
```

- Add a new function for contain the button and call it at 'startup' (Widget.js):

```
startup: function() {
  this.inherited(arguments);
  this.resize();
  setTimeout(lang.hitch(this, this.resize), 100);
  this.IntroJS();
},

IntroJS: function(){
  new Button({
      label: "INTRO JS",
      style: "position:absolute;top:5px;left:400px;",
      onClick: () => {
        initIntro()
      }
  }, this.executeIntroJS).startup();
},

```




                    
                    
                    
                    


