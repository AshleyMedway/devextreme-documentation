---
id: dxDiagram.Options.edges.toExpr
type: String | function(data, value)
default: 'to'
---
---
##### shortDescription
Specifies the name of a data source field or an expression that returns an edge's end node key.

##### param(data): any
The current edge's data object.

##### return: any
An edge's end node key.

##### param(value): any
When the function is called as a setter, returns the edge's new end node key value; when the function is called as a getter, returns `undefined`.

---
Specify this property if you use ([node and edge](/concepts/05%20UI%20Components/Diagram/10%20Data%20Binding/10%20Node%20and%20Edge%20Arrays.md '/Documentation/Guide/UI_Components/Diagram/Data_Binding/#Node_and_Edge_Arrays')) data sources.

#include common-demobutton with {
    url: "https://js.devexpress.com/Demos/WidgetsGallery/Demo/Diagram/NodesAndEdgesArrays/"
}

    <!-- tab: index.js -->
    $(function() {
        $("#diagram").dxDiagram({
            nodes: {
                dataSource: orgItems
            },
            edges: {
                dataSource: orgLinks,
                fromExpr: "from",
                toExpr: "to"
            },
        });
    });
    
    <!-- tab: data.js -->
    var orgItems = [
        {  
            "id":"106",
            "text":"Development",
            "type":2
        },
        {  
            "id":"108",
            "text":"WPF\nTeam",
            "type":2
        },
        {  
            "id":"109",
            "text":"Javascript\nTeam",
            "type":2
        },
        // ...
    ];

    var orgLinks = [  
        {  
            "id":"124",
            "from":"106",
            "to":"108",
        },
        {  
            "id":"125",
            "from":"106",
            "to":"109",
        },
        // ...
    ];