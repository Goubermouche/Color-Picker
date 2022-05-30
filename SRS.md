# Software Requirements Specification
## Color Format Translator

Version 0.1  
Prepared by Simon Tupý 3.C  
SSPŠaG  
May 30, 2022

Table of Contents
================
* 1 [Introduction](#1-introduction)
  * 1.1 [Product Purpose](#11-product-purpose)
  * 1.2 [Product Scope](#12-product-scope)
  * 1.3 [Definitions, Acronyms and Abbreviations](#13-definitions-acronyms-and-abbreviations)
  * 1.4 [References](#14-references)
  * 1.5 [Document Overview](#15-document-overview)
* 2 [Product Overview](#2-product-overview)
  * 2.1 [Product Perspective](#21-product-perspective)
  * 2.2 [Product Functions](#22-product-functions)
  * 2.3 [Product Constraints](#23-product-constraints)
  * 2.4 [User Characteristics](#24-user-characteristics)
  * 2.5 [Assumptions and Dependencies](#25-assumptions-and-dependencies)
  * 2.6 [Apportioning of Requirements](#26-apportioning-of-requirements)
* 3 [Requirements](#3-requirements)
  * 3.1 [External Interfaces](#31-external-interfaces)

## 1. Introduction  
  ### 1.1 Product Purpose
The purpose of this document is to present a detailed description of the Color Format Translator. It will explain the purposes and features of the translator, the interface of the translator, what the translater and its accompanying systems will do and how the system will react to the user's input. This document is intended for both stakeholders and the developers of the translator.

### 1.2 Product Scope
This piece of software will be a Color Format Translator specifically designed with graphics programmers in mind, however other parties, such as web developers, may find it to be useful too. The application will be designed to maximaze the user's productivity by making use of shortcuts and on-demand color translation. The application will make heavy use of modern standards & will be built with extensibility in mind. 

### 1.3 Definitions, Acronyms and Abbreviations
| Term | Definition    |
| ---- | ------- |
| Software Requirements Specification  |  A document that completely describes all of the functions of a proposed system and the constraints under which it must operate. For example, this document.       |
|      |         |

### 1.4 References
Microsfot PowerToys *Microsoft* https://docs.microsoft.com/en-us/windows/powertoys/color-picker December 3, 2019

### 1.5 Document Overview
The next chapter, the Product overview section, of this document gives an overview of the functionality of the product. It describes the informal requirements and is used to establish a context for the technical requirements specification in the next chapter. The third chapter, Requirement specification section, of this document is written primarily for developers and describes in technical terms the details of the functionality of this product. Both of these sections of the document descibe the same software product in its entirety, but are intended for different audienced and thus use different languages and terms.

## 2. Product Overview
The Color Format Translator has two main modes: a global, window-wide color picker mode, where the user can use a specified keybinding to enter this mode and sample the color of the currently hovered pixel, the format of this color will be automatically translated into the user's preferred color format (HEX, VEC4, RGB etc.). Upon leaving this mode the latest color value will be copied to the clipboard. The second mode will provide an interface that allows the user to convert (translate) various colors into other formats. 

### 2.1 Product Perspective
The Product is intended to replace an already existing system - the Power Toys color picker. 

### 2.2 Product Functions

### 2.3 Product Constraints

### 2.4 User Characteristics

### 2.5 Assumptions and Dependencies

### 2.6 Apportioning of Requirements

## 3. Requirements

### 3.1 External Interfaces

#### 3.1.1 User interfaces

#### 3.1.2 Hardware interfaces

#### 3.1.3 Software interfaces

### 3.2 Functional

### 3.3 Quality of Service

#### 3.3.1 Performance

#### 3.3.2 Security

#### 3.3.3 Reliability

#### 3.3.4 Availability

### 3.4 Compliance

### 3.5 Design and Implementation

#### 3.5.1 Installation

#### 3.5.2 Distribution

#### 3.5.3 Maintainability

#### 3.5.4 Reusability

#### 3.5.5 Portability

#### 3.5.6 Cost

#### 3.5.7 Deadline

#### 3.5.8 Proof of Concept
