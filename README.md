#  Engineering Project Template (CUI Style)

This README serves as a comprehensive guide for the **Jenkins CNC** project, structured according to the `template-engineering-complex`. This template is designed for large-scale engineering projects, providing a full lifecycle structure from planning through archiving. It emphasizes a structured approach for complex endeavors.

## Project Information

Project Status : <mark style="background-color: green">   COMPLETED  </mark>  
Code Status : <mark style="background-color: green">   GOOD  </mark>  
Development Status : <mark style="background-color: red">   NOT ACTIVE  </mark>  

## General Information

This repository contains the project files for our **Shapeoko 3 XXL**, focused on achieving maximum automation. Our goal was to enhance the Shapeoko 3 with various upgrades to streamline its operation.

**Key Achievements for the Jenkins CNC Project:**
-   Automated Tool Change
-   Manual Tool Change Implementation
-   Integrated Coolant System
-   Tool Z Probe Macro Development
-   Workpiece XYZ Probe Integration
-   Spindle Control Enhancement
-   Achieved High Modularity

## WATCH NOW ON YOUTUBE

Watch the project playlist on YouTube to see the Jenkins CNC in action and learn more about its features and development process.

[![YouTube Project Playlist Thumbnail](http://img.youtube.com/vi/w-qWbZ5-IQw/0.jpg)](https://youtube.com/playlist?list=PLNTKXZ4hgP_jekZOWw05JcJtyseCdSsIV "Jenkins CNC Project Playlist")

## Support

Did this project help you? Consider supporting our work!

Consider Subscribing: https://www.youtube.com/@Jenkins_Robotics <br>
Patreon ➔ https://www.patreon.com/JenkinsRobotics <br>
Venmo ➔ https://venmo.com/u/JenkinsRobotics <br>

## Table of Contents

**[Project File Structure](#project-file-structure)**<br>
**[Installation Instructions](#installation-instructions)**<br>
**[Design Process & Key Files](#design-process-and-key-files)**<br>
**[Next Steps](#next-steps)**<br>
**[Components](#components)**<br>
**[Notes and Miscellaneous](#notes-and-miscellaneous)**<br>
**[Links](#links)**<br>

## Project File Structure

This project follows the `template-engineering-complex` folder structure, providing a robust framework for managing all aspects of a complex engineering endeavor. Each directory is designed to house specific types of project documentation and assets, ensuring clarity and organization throughout the project lifecycle.


```
📁 [PROJECT_NAME]
├── 01_Planning
	├── CONOPS
	├── Risk_Matrix
	└── Schedules_and_Plans
	└── System_Requirements
├── 02_Design
	├── System_Architecture
	├── Mechanical_Design
		├── CAD_Models
		└── Drawings
	├── Electrical_Design
		├── Schematics
		├── PCB_Layouts
		└── Wiring_Designs
	├── Software_Design
		├── Source_Code
		└── Documentation
	└── Simulations_and_Analysis
		├── Mechanical_Simulations
		├── Electrical_Simulations
		├── System_Models
		└── Analysis_Reports
			├── Feasibility_Studies
			├── Performance_Analysis
			└── Failure_Analysis
├── 03_Procurement_and_Manufacturing
	├── BOMs (Bill_of_Materials)
	├── Manufacturing_Quotes
	└── Purchase_Orders_and_Tracking
├── 04_Testing_and_Validation
	├── Test_Plans
	├── Test_Procedures
	├── Test_Results
	└── Test_Reports
├── 05_Reviews_and_Meetings
	├── Meeting_Minutes
		├── Weekly_Tagups
		└── Action_Items
	├── Formal_Reviews
		├── PDR (Preliminary Design Review)
		├── CDR (Critical Design Review)
		├── CRT (Critical Readiness Review)
		└── PTR (Production Readiness Review)
	└── Audit_and_Compliance
├── 06_Deliverables
	└── Project_Closeout_Documentation
└── 99_Archive
	├── Old_Versions
    └── Superseded_Documents
```

## Design Process & Key Files for Jenkins CNC

Within the `03_Design` directory, specific files were crucial for the Jenkins CNC project:

* **`03_Design/Software_Design/Source_Code/JenkinsCNCReprap.cps`**: This is our custom post-processor for Fusion 360. It acts as the critical link between the CAM system and the Duet 3-based CNC machine. It translates CAM instructions (toolpath data, operations, feeds/speeds) into gcode that the CNC machine understands. Our custom post-processor, based on the default RepRap post-processor, rectifies gcode syntax errors and incorporates modular features essential for our automated setup.
    * **Directions for `JenkinsCNCReprap.cps`:**
        * **Uploading to Fusion 360 Cloud Storage [Personal-cloud]:** Within Fusion 360, open the project navigation panel. Under "Libraries," select "Assets," then select or create the "CAMPosts" folder. Upload the custom Post Processor within this folder for cloud storage.
        * **Creating an NC Program:** After designing your CAD model, navigate to the "Manufacturing Tab" in Fusion 360. Complete the "Setup" process and define your desired toolpaths. Create a new "NC Program." Under "Post Configuration / Library," specify the location of the Post Processor File (personal-cloud recommended). Under "Post," select "Jenkins CNC RepRap." Adjust "Post Properties" as desired, then export the gcode.

* **`03_Design/Software_Design/Source_Code/GCODE`**: This directory conceptually corresponds to where various gcode files are stored.
    * **SDCARD Contents**: This sub-section would represent a copy of the files located on our Duet 3 Motherboard SD Card. It includes system drives with subfolders containing gcode and system files. It's recommended to upgrade stock firmware and system files before referencing our custom files. Official Duet 3 releases can be found on GitHub: [RepRap Files](https://github.com/Duet3D "Duet3D").
    * **Macros**: This sub-section contains additional system files needed for the Duet 3, grouped by function.
        * **Directions for Macros:** Upload any desired files. Review and make necessary adjustments to position points and probe/sensor numbers.
    * **Sys**: This sub-section holds important system files for the Duet 3, configuring the machine and providing gcode for processes like tool changes.
        * **Directions for Sys files:** For AutoTool Change, upload `TFree`, `Tpost`, `Tpre`, `ToolZProbe`. For manual tool change, upload `manualtoolchange`, `ToolZProbe`.

* **`05_Documentation/MANUALS/Post Processor Training Guide`**: This file serves as a reference for the Fusion 360 post-processor and contains reference material for different hardware components of the CNC.

> **Note:** Updating the RepRap firmware should be done carefully. Uploading the updated ZIP file could erase custom gcode files. Always back up your custom files before firmware updates.

## Installation Instructions

Detailed installation instructions for the Jenkins CNC project can be found in the linked YouTube video. This video guides you through the process of setting up and configuring the automated CNC system.

### Video link to be updated soon

[![Installation Guide Thumbnail](http://img.youtube.com/vi/w-qWbZ5-IQw/0.jpg)](https://youtube.com/playlist?list=PLNTKXZ4hgP_jekZOWw05JcJtyseCdSsIV "Jenkins CNC Installation Guide")

## Next Steps

This project is now completed. No further development steps are currently planned. We will release bug fixes if any are discovered.

If you require assistance, please join our Discord channel linked below.

## Components

The following is a breakdown of key components and software utilized in the Jenkins CNC project:

| Item        | Function      | Cost  |
| ----------- | :------------: | -----: |
| Fusion 360  | CAD/CAM       | Free |
| VS Code     | Text Editor   | Free |
| Duet 3      | CNC Controller | Varies |
| Shapeoko 3 XXL | CNC Machine   | Varies |

## Notes and Miscellaneous

Disclaimer: Modifying your Shapeoko will void the warranty. Proceed with any modifications at your own risk.

**ENJOY!!**

That’s all folks. We hope this project helps you in some way.
... Consider Supporting Us Down Below.

## Links

SUPPORT US ►

Consider Subscribing: https://www.youtube.com/@Jenkins_Robotics <br>
Patreon ➔ https://www.patreon.com/JenkinsRobotics <br>
Venmo ➔ https://venmo.com/u/JenkinsRobotics <br>

FOLLOW US ►

Discord ➔ https://discord.gg/sAnE5pRVyT <br>
Patreon ➔ https://www.patreon.com/JenkinsRobotics <br>
Twitter ➔ https://twitter.com/j <br>
Instagram ➔ https://www.instagram.com/jenkinsrobotics/ <br>
Facebook ➔ https://www.facebook.com/jenkinsrobotics/ <br>
GitHub ➔ https://jenkinsrobotics.github.io <br>
