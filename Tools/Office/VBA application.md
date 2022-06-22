20220622

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
