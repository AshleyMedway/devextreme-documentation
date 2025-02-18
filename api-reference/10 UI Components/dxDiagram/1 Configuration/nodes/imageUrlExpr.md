---
id: dxDiagram.Options.nodes.imageUrlExpr
type: String | function(data, value)
default: undefined
---
---
##### shortDescription
Specifies the name of a data source field or an expression that returns an image URL or Base64 encoded image for a node.

##### param(data): any
The current node's data object.

##### return: any
An image URL or Base64 encoded image for a node.

##### param(value): any
When the function is called as a setter, returns an image URL or Base64 encoded image for the node; when the function is called as a getter, returns `undefined`.

---
This property is in effect for nodes of the `"cardWithImageOnLeft"`, `"cardWithImageOnTop"`, or `"cardWithImageOnRight"` [type](/concepts/05%20UI%20Components/Diagram/40%20Shape%20Types.md '/Documentation/Guide/UI_Components/Diagram/Shape_Types/').

    <!-- tab: index.js -->
        $(function() {
            $("#diagram").dxDiagram({
                nodes: {
                    dataSource: new DevExpress.data.ArrayStore({
                        key: "this",
                        data: orgItems
                    }),
                    imageUrlExpr: "picture",
                },
                edges: {
                    dataSource: new DevExpress.data.ArrayStore({
                        key: "this",
                        data: orgLinks
                    })
                },
            });
        });
    
    <!-- tab: data.js -->
    var orgItems = [
        {  
            "id":"110",
            "text":"ASP.NET\nTeam",
            "type": "ellipse"
        },
        {  
            "id":"112",
            "text":"Ken Samuelson",
            "type": "cardWithImageOnLeft",
            "picture": "images/employees/32.png"
        },
        {  
            "id":"113",
            "text":"Terry Bradley",
            "type": "cardWithImageOnLeft",
            "picture": "images/employees/33.png"
        },
    ];

    var orgLinks = [  
        {  
            "id":"129",
            "from":"110",
            "to":"112",
        },
        {  
            "id":"130",
            "from":"110",
            "to":"113",
        }
    ];

![Diagram - Data Binding Options](/images/diagram/image-url-expr.png)