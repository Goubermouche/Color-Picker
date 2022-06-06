# Functional Specification
## Color Picker

Version 0.1  
Prepared by Simon Tupý 3.C  
SSPŠaG  
June 6, 2022

Table of Contents
================
* 1 [Introduction](#1-introduction)
   * 1.1 [Document Purpose](#11-document-purpose)
   * 1.2 [Definitions, Acronyms and Abbreviations](#12-definitions-acronyms-and-abbreviations)
   * 1.3 [Target Audience](#13-target-audience)
   * 1.4 [References](#14-references)
* 2 [Scenarios](#2-scenarios)
   * 2.1 [Usecases](#21-usecases)
   * 2.2 [Personas](#22-personas)
   * 2.3 [Details, Motivation and Live Examples](#23-details-motivation-and-live-examples)
   * 2.4 [Product Scope](#24-product-scope)
   * 2.5 [Unimportant Functions and Properties](#25-unimportant-functions-and-properties)
* 3 [Architecture Overview](#3-architecture-overview)
   * 3.1 [Work Flow](#31-work-flow)
   * 3.2 [Main Modules](#32-main-modules)
   * 3.3 [Details](#33-details)
   * 3.4 [Possible Program Flows](#34-possible-program-flows)

## 1. Introduction  
  ### 1.1 Document Purpose
  The purpose of this document is to present a description of the functions and interfaces of the application. Furthermore it will introduce commonly used concepts, interfaces and usecases, including a basic overview of the application's structure.
  ### 1.2 Definitions, Acronyms and Abbreviations
| Term | Definition    |
| ---- | ------- |
| Software Requirements Specification  |  A document that completely describes all of the functions of a proposed system and the constraints under which it must operate. For example, this document.       |
| <kbd>Key</kbd> | A keyboard key declaration. |
  ### 1.3 Target Audience
This document is intended mainly for testers, developers, the marketing department, and other parties that may be involved. 
  ### 1.4 References
* Software Requirement Specification *Šimon Tupý* https://github.com/Goubermouche/Color-Picker/blob/main/SRS.md    
* PowerToys *Microsoft* https://docs.microsoft.com/en-us/windows/powertoys/color-picker December 3, 2019   
## 2. Scenarios
  ### 2.1 Usecases
The main use case of the product is fast color picking of colors in various formats from the user's display. This feature may be, for example, used in software development for faster prototyping. 
  ### 2.2 Personas
The products target audience mainly consists of programmers and other software developers (ie. graphics programmers, web developers, etc.), however the product offers utility to other groups aswell.
  ### 2.3 Details, Motivation and Live Examples
 This project was inspired by the PowerToys which already provides a native color picker for windows, this color picker, however, offers limited control over color formats while active (the user can only switch them after opening the complimentary PowerToys application), which can get tiresome after having to switch between color formats more often. This application aims to fix this issue by using additional global shortcuts that give the user the ability to switch color formats on the fly. 
  ### 2.4 Product Scope
Due to the limit timeframe the scale of this project is limited to just the bare essentials - that is a basic color picker that enables users to pick any color from their display at will. 
  ### 2.5 Unimportant Functions and Properties
The aforementioned scale of the project allows us to focus on every aspect of the application at a decently high level, as such, no functions or properties will be left ignored.

## 3. Architecture Overview
  ### 3.1 Work Flow
  When the user first launches the application it is completely invisible (no presence apart from a background process will be visible). If the user activates the predefined shortcut (default being <kbd>Shift</kbd> + <kbd>C</kbd>) the application launches and the user will see a swatch next to his cursor - this swatch displays a preview of the hovered color and the selected color format. If the application is currently in its active state and the users clicks the <kbd>LMB</kbd> the currently hovered color gets copied to the clipboard and the application returns to its dormant state. Additionally the user can switch between color formats using the <kbd>UP</kbd> and <kbd>DOWN</kbd> keys.
  ### 3.2 Main Modules
  Due to the overall simplicity of the solution the application only consists of one module: the color picker itself. 
  ### 3.3 Details
  The application will dynamically respond to display scale. Additionally the application will support both multiple, and single monitor configurations natively. 
  ### 3.4 Possible Program Flows
  The application has two main states: active and dormant. In its dormant state the application consumes minimal resources (target being < 0% on normal systems) and only listens to a predefined keyboard shortcut (default being <kbd>Shift</kbd> + <kbd>C</kbd>). If and when the shortcut gets triggered the application awakens and the color picker functionality is enabled, allowing the user to use sample display colors.