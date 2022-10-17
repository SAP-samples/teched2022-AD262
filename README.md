# AD262 - Compose full stack applications in SAP Business Application Studio

## Description

This repository contains the material for the SAP TechEd 2022 session called D262 - Compose full stack applications in SAP Business Application Studio.  

## Overview

In this session you will learn how to use the SAP SAP Business Application Studio (BAS) to rapidly develop apps on SAP Business 
Technology Platform (SAP BTP). You will learn how to build a full blow CRUD application including backend services and a UI application in a matter of minutes with only visual editors. You will connect the application to an SAP S/4HANA API. Learn how to easily switch to code, work on from there to create additional business logic for your service to finally make the application available on BTP with a "one click deployment"

## The Use Case

In this session we will enable of Capital Expenditures (CAPEX) process. Capital expenditures have a deep effect on the Profit & Loss balance sheet of a company.
CAPEX is about providing budget for buying & maintaining fixed / integral assets (FA/IA). 
CAPEX cost also includes upgrades or repairs of assets to improve the life span of “useful assets” (e.g. vehicles, laptops, phones).

So, normally users would register for such an expenditure by filling out and submitting a form with the details for the intended purchase or the repairs and the expected costs. 
This will then start a workflow where a manager can decide to approve or reject the CAPEX request. This is what we will develop in this session.

To achieve this, we will create a new backend service using the Cloud Application Programming Model (CAP), and a web application based on Fiori elements with which users can create CAPEX requests as well as list all the CAPEX requests. Other parts of the process, a workflow for the approval process including a task UI based on the Mobile Development Kit (MDK) are not in the scope of this tuorial for time reasons, but it can be done with LCAP in Business Application Studio as well.

## Requirements

The requirements to follow the exercises in this repository can be found in the [Getting Started](exercises/ex0/) section below.

## Exercises

- [Getting Started - Preparation](exercises/ex0/README.md)
- [Exercise 1 - Create a data model with the SAP Business Application Studio ](exercises/ex1/README.md)
- [Exercise 1.5 - Reference an S/4 HANA CLoud Service in your eata model ](exercises/ex1.5/README.md)
- [Exercise 2 - Add some sample data ](exercises/ex2/README.md)
- [Exercise 3 - Create a service ](exercises/ex3/README.md)
- [Exercise 4 - Create a list report UI application ](exercises/ex4/README.md)
- [Exercise 5 - Preview your service and application ](exercises/ex5/README.md)
- [Exercise 6 - Add application logic to the application ](exercises/ex6/README.md)
- [Exercise 7 - Deploy your service and application ](exercises/ex7/README.md)


Start the exercises [here](exercises/ex0/README.md).

## How to obtain support

Support for the content in this repository is available during the actual time of the online session for which this content has been designed. Otherwise, you may request support via the [Issues](../../issues) tab.

## License
Copyright (c) 2022 SAP SE or an SAP affiliate company. All rights reserved. This project is licensed under the Apache Software License, version 2.0 except as noted otherwise in the [LICENSE](LICENSES/Apache-2.0.txt) file.
