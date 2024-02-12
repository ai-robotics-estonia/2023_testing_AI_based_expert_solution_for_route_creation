*This is a template repository for this organization. Start by replacing the placeholder for the project name with it's actual title.*

# Testing of artificial intelligence-based expert solution for route creation


## Summary

| Company name | [Tiksoja Puidugrupp AS](https://www.tiksoja.eu/) |
| :--- | :--- |
| Development Team Lead Name | [Eduard Ševtšenko](https://profile.link) |
| Development Team Lead e-mail | [eduard.sevtsenko@ut.ee](https://profile.link) |
| Objectives of the Demonstration Project | Artificial intelligence-based solution - expert system for automating the creation of the production routes with operational times  |

# Each project has an alternative:

- *a) To fill in the description [below](https://github.com/ai-robotics-estonia/_project_template_/edit/main/README.md#implementation-details)*
*Tiksoja Puidugrupp manufactures furniture for children and adults. The company's product range includes around 1000 products sold to large B2B buyers all over Europe
The goal of this project is to develop an (artificial intelligence-based) solution - an expert system that allows automating the creation of a route, recipe and BoM, and later creating an ERP entry based on them.


## Objectives of the Demonstration Project
*Artificial intelligence-based solution - expert system for automating the creation of the production routes with operational times.*


## Activities and results of demonstration project
*Challenge addressed (i.e. whether and how the initial challenge was changed during the project, for which investment the demonstration project was provided)*
- a) The modification of todays working routine in product design process to provide Input parameters required for Product Management Information (PMI) generation.
- b) Implementation of standard features library
- c) The development of algorithm required for production route generation. (Non written rules)
- d) The quality of data for AI model training.
- e) The validity of created alternative production routes*



*Data sources (which data was used for the technological solution)*
- a) Solidworks files
- b) Data from company ERP
- c) TPT (Advanced Scheduling and  Planning Software)
- d) Norm Production times in Excel

*Description and justifictaion of used AI technology*
- a) AI is able to generate alternative routes based on predefined algorithms. The input is PMI data of product and historical manufacturing data.

*Results of testing and validating technological solution*
-  a)The AI was able to predict the operational time for generated alternative rules. The accuracy of data was validated by historical data. The AI generates the visual of alternative production routes and selects the best (shortest) one.

*Technical architecture (presented graphically, where can also be seen how the technical solution integrates with the existing system)*

<img width="576" alt="TechicalArchitecture" src="https://github.com/ai-robotics-estonia/expert_solution_for_route_creation/assets/154315695/b35ab7eb-811d-48a8-ae51-9f621707993d">

*Potential areas of use of technical solution*
- In theory, the solution is not limited to the furniture industry, but applicable to a wide range of manufacturing companies.


*Lessons learned (i.e. assessment whether the technological solution actually solved the initial challenge)*
- a) The Project scope can change and it should be regularly monitored.
- b)The BA analyst should be available until the Project is finished.
- c) The team of AI engineers should be available from the beginning of the project.*

### Description of User Interface 
*(i.e. How does the client 'see' the technical result, whether a separate user interface was developed, command line script was developed, was it validated as an experiment, can the results be seen in ERP or are they integrated into work process)*
-  a) PMI (Product Manufacturing Information) is created during the design process. It is recorded in the Solidworks CAD files and database records. This is the entirety of the data that defines the product geometry and all its required properties. A manufacturing process is designed that will produce the desired product. Traditionally the main interface to the PMI is a product drawing that is interpreted by an engineer. Automated process design procedure needs direct access to the PMI.  Fully automated solution is a very complicated one. 
The practical solution is streamlining the product design methods in a way that relevant part of the PMI is automatically extracted that will allow to automate making of most of the main production decisions. There are many built in design automation features available in Solidworks. There are also commercially available add-on modules for facilitating the PMI information exchange with downstream database tools. Several such tools and methods were analysed and tested for practical relevance. As a result, several design tools and best practices were implemented, which results in a file structure that is better suited for automatic PMI data extraction. An Add-on program Customtools was purchased and implemented by the company. This satisfies most needs for the data transfer. All the automatically transferable information is saved in the CAD files as custom file properties. Such information is directly referenced both in drawings and in the data transfer files. Customtools module has a report builder function that allows to flexibly organize such data and pass it on to any ERP or AI prototype. This is enough for automating the data transfer on the level that was used in Tiksoja before the current project. However, if the company wants to further automate the manufacturing process design, more information is needed in richer data format that can be easily handled via Custom Property method.  For example, number, size, and position of various drilled holes. Or type, number, and position of chamfered edges. Or the type and position of the surfaces with different surface treatment requirements.  A data format has been developed to aggregate such information and make it available to the rule engine that builds manufacturing routes. The consolidated variable length data will also be recorded as Custom File Properties and /or directly in the transition file that is filled out in the Customtools report generator. Automatic gathering and consolidation such variable length data is possible by writing special custom commands using Solidworks API (Application Programming Interface). Sample programs were written for gathering the hole data and end chamfering information.

- See sample data transfer file. https://www.dropbox.com/scl/fi/voqrsc1lw5sm3dnyubngf/NR02-spets.csv?rlkey=i0ews6kx0czzd8h45thwxvicq&dl=0
- See sample code for Solidworks hole and chamfer information gathering. https://www.dropbox.com/scl/fi/gx1t5kvvq8mguijcdl08u/PMIExport.swp?rlkey=8zv4cxr5ffagcidnbiq1xh5ee&dl=0
The generated production routes will be imported to the ERP and used for production planning process.
The aim of the practical solution is to identify the best route and confirm it in the ERP system. In addition to time selection, the algorithm may, in the future, assess the quantity of errors made at a particular workstation and operation in the past. These errors are associated with the route as a configuration. This approach allows avoiding products that are quickly produced based on the route but have a high error rate. This enables greater sustainability, as there is no longer a need to process the same detail multiple times, to fix the mistakes. Those mistakes could be made through the wrong drilling sizes or drilling to the wrong place. 


## Custom agreement with the AIRE team

*If you have a unique project or specific requirements that don't fit neatly into the Docker file or description template options, we welcome custom agreements with our AIRE team. This option allows flexibility in collaborating with us to ensure your project's needs are met effectively.*

*To explore this option, please contact our demonstration projects service manager via katre.eljas@taltech.ee with the subject line "Demonstration Project Custom Agreement Request - [Your Project Name]." In your email, briefly describe your project and your specific documentation or collaboration needs. Our team will promptly respond to initiate a conversation about tailoring a solution that aligns with your project goals.*



