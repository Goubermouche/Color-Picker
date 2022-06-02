# Software Requirements Specification
## Color Picker

Version 0.1  
Prepared by Simon Tupý 3.C  
SSPŠaG  
May 30, 2022

Table of Contents
================
* 1 [Introduction](#1-introduction)
   * 1.1 [Product Purpose](#11-product-purpose)
   * 1.2 [Definitions, Acronyms and Abbreviations](#12-definitions-acronyms-and-abbreviations)
   * 1.3 [Target Audience](#13-target-audience)
   * 1.4 [Additional Information](#14-additional-information)
   * 1.5 [Contacts Information](#15-contacts)
   * 1.6 [References](#16-references)
* 2 [Product Overview](#2-product-overview)
   * 2.1 [Product Perspective](#21-product-perspective)
   * 2.2 [Product Functions](#22-product-functions)
   * 2.3 [User Groups](#23-user-groups)
   * 2.4 [Product Enviroment](#24-product-enviroment)
   * 2.5 [User enviroment](#25-user-enviroment)
   * 2.6 [Limitations, Implementation Details](#26-limitations-implementation-details)
   * 2.7 [Assumptions, Dependencies](#27-assumptions-dependencies)
* 3 [Interface Requirements](#3-interface-requirements)
   * 3.1 [User Interface](#31-user-interface)
   * 3.2 [Hardware Interface](#32-hardware-interface)
   * 3.3 [Software Interface](#33-software-interface)
* 4 [System properties](#4-system-properties)
   * 4.1 [Color Picking](#41-color-picking)
     * 4.1.1 [Description and Importance](#411-desciption-and-importance)
     * 4.1.2 [Inputs, Outputs](#412-inputs-outputs)
     * 4.1.3 [Function Specification](#413-function-specification)
   * 4.2 [Color Picker Cursor](#42-color-picker-cursor)
     * 4.2.1 [Description and Importance](#421-desciption-and-importance)
     * 4.2.2 [Inputs, Outputs](#422-inputs-outputs)
     * 4.2.3 [Function Specification](#413-function-specification)
* 5 [Non-Functional Requirements](#5-non-functional-requirements)
   * 5.1 [Performance](#51-performance)
   * 5.2 [Security](#52-security)
   * 5.3 [Reliability](#53-reliability)
   * 5.4 [Project Documentation](#54-project-documentation)
   * 5.5 [User Documentation](#55-user-documentation)


## 1. Introduction  
  ### 1.1 Product Purpose
The purpose of this document is to present a detailed description of a Color Picker application. It will explain the purposes and features of the Color Picker, and its interface, what the application and its accompanying systems will do and how the system will react to the user's input.
  ### 1.2 Definitions, Acronyms and Abbreviations
| Term | Definition    |
| ---- | ------- |
| Software Requirements Specification  |  A document that completely describes all of the functions of a proposed system and the constraints under which it must operate. For example, this document.       |
  ### 1.3 Target Audience
This document is intended for both stakeholders and the developers of the application.
  ### 1.4 Additional Information
  ### 1.5 Contacts
tupy.si.2019@skola.ssps.cz

  ### 1.6 References
Microsfot PowerToys *Microsoft* https://docs.microsoft.com/en-us/windows/powertoys/color-picker December 3, 2019



## 2. Product Overview
  ### 2.1 Product Perspective
This piece of software will be a Color Picker specifically designed with graphics programmers in mind, however other parties, such as web developers, may find it to be useful too. The application will be designed to maximaze the user's productivity by making use of shortcuts and on-demand color picking. The application will make heavy use of modern standards & will be built with extensibility in mind. 
  ### 2.2 Product Functions
The Color Picker will run as a lightweight background task when not needed, however, when the user activates the specified shortcut (default being <kbd>Shift</kbd> + <kbd>C</kbd>) the application will launch and immediately give the user the ability to hover over any pixel on the screen and, after clicking the <kbd>LMB</kbd>, copy the pixel's color to the clipboard. The application will support multiple color formats such as HEX, VEC3, RGB and others, the user will be able to switch between them on-the-fly by scrolling while the application is active.
  ### 2.3 User Groups
As stated before the application is made specifically for grahics programmers & other parties whom might find such a tool useful (ie. web developers).
  ### 2.4 Product Environment
The software will run on any version of Windows released after (and including) Windows 8.1 - for more information see WPF compatibility statistics.
  ### 2.5 User enviroment
The application will run as a lightweight background process and listen for the user activating a specific shortcut to activate the color picker, upon activation the application will immediately start and provide the user with an intuitive mouse color picker. After the user hovers over the desired pixel he can simply click and the hovered pixel's color will be copied to the clipboard and the application will go back into a dormant state.
  ### 2.6 Limitations, Implementation Details
The application itself will make heavy use of the user32 DLL for global key and mouse hooks, getting the global mouse position and pixel color and, as such, is only limited by the capabilites of this API.
  ### 2.7 Assumptions, Dependencies
It is assumed that the target user has atleast some basic knowledge of programming, furthermore it is assumed that the application will be run on a machine running the Windows operating system in accordance with [section 2.4](#24-product-enviroment) of this document.

## 3. Interface Requirements
  ### 3.1 User Interface
The application's user interface will be minimalistic, since we don't want to introduce visual clutter while the user is picking a color, furthermore, UI design will not be a focus since the application is supposed to be a utility tool with minimal slowdowns for the user.
  ### 3.2 Hardware Interface
The application, in its current state, will require a working keyboard and/or a device serving the same purpose. Additionally the target system will have to meet the basic hardware requirements of the active Windows version. 
  ### 3.3 Software Interface
The application will interact with the user32 Windows API and the WPF interace (CWPFI).

## 4. System properties
  ### 4.1 Color Picking
  #### 4.1.1 Description and Importance
This feature is of vital importance, it is, in essence, the core of the application. This property enables the user to hover a pixel on the screen and convert it to the selected color format and afterwards copy it to the clipboard.
  #### 4.1.2 Inputs, Outputs
The mouse position, keyboard hook and display reference will be supplied, and, as a result the color can be sampled. The sampled color will then go through a color formatter and be copied to the clipboard - the final output.
  #### 4.1.3 Function Specification
A formatted color has to be copied to the clipboard and no errors can be thrown.
  ### 4.2 Color Picker Cursor
  #### 4.2.1 Description and Importance
This feature is of secondary importance since it only provides a visualization of the hovered color and the selected color format - the feature is essentially a window that is position next to the user's mouse cursor and displays the color and the formatted color string.
  #### 4.2.2 Inputs, Outputs
The only inputs this property receives are the current mouse position and the application's current state (active/inactive). If the application is inactive nothing happens, on the other hand, when the application is active, the window containing color data is displayed and followingly positioned next to the mouse cursor. The only output here is visual - the window itself. 
  #### 4.2.3 Function Specification
The window has to behave in accordance to the current application state and follow the cursor without issue.

## 5. Non-Functional Requirements
  ### 5.1 Performance
The application should use minimal system resources - especially in its inactive state. In its active state the resource usage should also be minimal, however, due to the window being repositioned constantly and being redrawn due to the content updating, this may be difficult to achieve.
  ### 5.2 Security
The application currently has no security concerns since it uses native API's, WPF, and does not store nor access any potentially resky data.
  ### 5.3 Reliability
The application has to work reliably without being a hassle to work with, it has to copy the hovered color accurately and should copy it to the clipboard every time without issue.
  ### 5.4 Project Documentation
The codebase will contain thorough documentation for most classes, functions and variables in the form of comments (regular + XML based).
  ### 5.5 User Documentation
The GitHub repository, where this project will be accessible from, will contained a short & simple guide to get users started and acquaint them with the basic workings of the application.