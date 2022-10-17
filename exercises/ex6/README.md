# Exercise 6 - Add Application Logic to the Application

## The addtional scenario

While we already have a running CRUD application, we want to improve it now. 
We would like to get a visual hint that the criticality of a request is high depending on the total cost of the request. This sholoud be shown in the list of Capex requirements like this:

![](/exercises/ex6/images/LCAP_60.png)

In order to do achieve this, we need to do several things, most prominently to add some application logic to the project.

## The Code behind the Scenes

To create the project up to this point you have not seen any code, everything was built using visual editors. However, under the hood code is created using the technologies that are part of the low code perspective of the Business Application Studio. In this project it is CAP and Fiori elements. There is also the Mobile Development Kit (MDK) and the BTP Workflow that are not covered in this hands on.

For all these technolgies whenever you change something in the visual editors code is created. The code that is created is very much the code that a developer could have written in the same way using just text editors.

In fact you can see the code. And what's more you can decide at any point in the project that from now on you'd rather carry on with textual editors adding more code / changing the generated code. With this is becomes possible not only to use the low code tools to create complete applications but also to jump start any kind of development that involves CAP, Fiori elements, MDK or the workflow. You can use the visual tools to a certain point and then switch to the code. Get the straight forward things done really easily and fast and if the editors do not provide enough functionality to do the final 20% of the resulting applications, one can switch to the code editors and finish it there.

How do switch to the code? Let's do this now.

Press the button in the left sidebar at the very top, then choose **View** and **Explorer** as entries

![](/exercises/ex6/images/LCAP_61.png) 

Now a new side pane opens at the left and it contains the file structure of our project. You can see a **db** and a **srv** folder there, both are standard CAP folders that hold the data models and the services respectively. There is also the **app** folder which holds our Fiori elements UI application, if there are more than one and additional MDK applications you can also find them in this folder.

![](/exercises/ex6/images/LCAP_62.png) 

Let's open the file **schema.cds** in the **db** folder. You can now see a text file which reflects the data models for Capex and Category that we have created using the graphical modeler. This is code in the Core Data Service (CDS) format and you could now edit it and enhance it. For CDS files this even works in both directions. You can either change the CDS file and the change is reflected in the graphical modeler and vice versa. Being able to edit in both direction doesn't work for all file types (e.g. not for Javascript files) but as a general rule you can always at any point leave the graphical editors, switch to the file structure and from then on code in text editors.

![](/exercises/ex6/images/LCAP_63.png)
![](/exercises/ex6/images/LCAP_64.png)
![](/exercises/ex6/images/LCAP_65.png)
![](/exercises/ex6/images/LCAP_66.png)
![](/exercises/ex6/images/LCAP_67.png)
![](/exercises/ex6/images/LCAP_68.png)
![](/exercises/ex6/images/LCAP_69.png)

```Javascript
const cds = require('@sap/cds')
/**
* Implementation 
 */
module.exports = cds.service.impl(async function() {
    this.after('READ', 'Capex', capexData => {
        const capexs = Array.isArray(capexData) ? capexData : [capexData];
        capexs.forEach(capex => {
            if (capex.totalcost > 200) {
                capex.criticality = 1;
            } else {
                capex.criticality = 2;
            }
        });
    });
});

```



## Summary
We have now added application logic to the application.

Continue to - [Exercise 7](../ex7/README.md)