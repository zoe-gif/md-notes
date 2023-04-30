---
title: VBA Application
date: 2022-06-10
update: 2022-06-15
categories: 
- CS
tags: VBA
description: 
---

## Decrypt Protected Excel

VBA module and run:

~~~
Sub DeletePW()
ActiveSheet.Protect DrawingObjects:=True, Contents:=True, AllowFiltering:=True
ActiveSheet.Protect DrawingObjects:=False, Contents:=True, AllowFiltering:=True
ActiveSheet.Protect DrawingObjects:=True, Contents:=True, AllowFiltering:=True
ActiveSheet.Protect DrawingObjects:=False, Contents:=True, AllowFiltering:=True
ActiveSheet.Unprotect
End Sub
~~~
