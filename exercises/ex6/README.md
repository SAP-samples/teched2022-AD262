# Exercise 6 - Add Application Logic to the Application

## The addtional Scenario

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

## Add a new Property to the Data Model

In order to control the crtiticality of a Capex registration entry on the UI, we need a new property. To get it, on the **Home** page, under **Data Model** press on the **Capex** entry. In the Data Modeler, by pressing on the header area of the **Capex** entity, bring up the menu and press the pencil like icon to be able to add the properties of the entity. Add a property called **criticality** of type **Integer** to the data model: 

![](/exercises/ex6/images/LCAP_63.png)

Press **Update** to save the change. The property is now added to the data model and because our **Capex** service entity also projects from the **Capex** data model 1:1 it is also automatically part of the service entity.

Note, we have added the new property to our data base. As the property is only needed to control the UI and as you will see in a later step is calculated at runtim, there is really no need to add it to the data base. There are also options to add it as a calculation field to a service only, but for simplicity reasons we still add it to the data base.

![](/exercises/ex6/images/LCAP_64.png)

## Add an Application Logic Handler to the project

Now we need to add the logic part. For this for the first time we have to code in a text editor. Using the file explorer (if not still expanded, expand it via Hamburger menu->View->Explorer), look for the **srv** folder and expand it. This is where the graphical modelers has created our service, it is in the **service.cds** file. We don't need to look into it, but we need to know it is in there. Our service, as mentioned before, is based on CAP. In CAP one can create a new file, with the same name as the file for the service, just with an extension "js" for JavaScirpt. If the CAP interpreter find such a file, it will automatically look for custome handlers for the service. This is what we need now. 

Select the **srv** folder and with a right mouse click invoke **New File**. Enter **service.js** as a name:

![](/exercises/ex6/images/LCAP_65.png)

Press **Ok**.

Now a new empty text file is openend. Add the following code to the file:

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

Save the file.

Let's have a look what happens in the code. It defines a handler that is invoked after (**this.after**) the was a **READ** request for the **Capex** entity. The request could for example be created as an OData GET request from the broswer. The CAP framework invokes our custom handler and passes the data into it, that it has just retireved from the data base. It might be one or more entities. Our code looks into the data, it looks whether **totalcost** is greater than 200, if so, it sets our new **criticality** property to 1 otherwise to 2.

So, with this, the criticality is set according to the total cost of our Capex express.

## Adjust the UI based on the Application Logic

![](/exercises/ex6/images/LCAP_66.png)
![](/exercises/ex6/images/LCAP_67.png)
![](/exercises/ex6/images/LCAP_68.png)
![](/exercises/ex6/images/LCAP_69.png)





## Summary
We have now added application logic to the application.

Continue to - [Exercise 7](../ex7/README.md)