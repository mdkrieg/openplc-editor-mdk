3.1 OpenPLC Editor Overview
===========================

 

The OpenPLC Editor is an IEC 61131-3 compliant PLC code editor. It allows you to create, compile and upload your IEC 61131-3 programs to the OpenPLC Runtime.

![](data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%20782%20451'%3E%3C/svg%3E)![](https://autonomylogic.com//wp-content/uploads/2022/06/editor.png)

The editor is very simple to use and supports all five languages defined in the IEC standard. The IEC-61131-3 standard is a normative document provided by the standards organization IEC (International Electrotechnical Commission) describing a standard for designing programmable controllers. The part 3 of this document (commonly named IEC 61131-3) specifies syntax and semantics of the programming language for PLCs. OpenPLC Editor implements all the languages described in this document: Ladder Logic (LD), Function Block Diagram (FBD), Instruction List (IL), Structured Text (ST), and Sequential Function Chart (SFC).

PLC Projects are stored in folders, where the main XML project file follows the PLCopen TC6-XML scheme. PLCopen is a vendor and product-independent worldwide association defining international standards for various topics related to control programming. The goal of the PLCopen sixth technical committee (TC6) is to define a standard file format, based on XML, to store IEC 61131-3 programs. A unified standard allow vendors to be able to import and export PLC programs created on different platforms.