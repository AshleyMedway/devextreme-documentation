---
id: dxDiagram.Options.nodes.itemsExpr
type: String | function(data, value)
default: undefined
---
---
##### shortDescription
Specifies the name of a data source field or an expression that returns a node's child items.

##### param(data): any
The current node's data object.

##### return: any
A node's child items.

##### param(value): any
When the function is called as a setter, returns the node's child items; when the function is called as a getter, returns `undefined`.

---
Specify this property when your source data has a [hierarchical structure](/concepts/05%20UI%20Components/Diagram/10%20Data%20Binding/30%20Hierarchical%20Array.md '/Documentation/Guide/UI_Components/Diagram/Data_Binding/#Hierarchical_Array').

#include common-demobutton with {
    url: "https://js.devexpress.com/Demos/WidgetsGallery/Demo/Diagram/NodesArrayHierarchicalStructure/"
}

    <!-- tab: index.js -->
    $(function() {
        $("#diagram").dxDiagram({
            nodes: {
                dataSource: new DevExpress.data.ArrayStore({
                    key: "this",
                    data: employees
                }),
                textExpr: "Title",
                itemsExpr: "Items"
            },
        });
    });
    
    <!-- tab: data.js -->
    var employees = [{
        "Full_Name": "John Heart",
        "Title": "CEO",
        "Items": [{
            "Full_Name": "Arthur Miller",
            "Title": "CTO",
            "Items": [{
                "Full_Name": "Brett Wade",
                "Title": "IT Manager",
            }, {
                "Full_Name": "Barb Banks",
                "Title": "Support Manager",
            }]
        }, {
            "Full_Name": "Robert Reagan",
            "Title": "CMO",
            "Items": [{
                "Full_Name": "Ed Holmes",
                "Title": "Sales Manager",
            }]
        }]
    }];
