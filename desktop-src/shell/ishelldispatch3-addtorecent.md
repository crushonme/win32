---
Description: Adds a file to the most recently used (MRU) list.
ms.assetid: aa5aef31-7f3f-4cc4-949d-1484de243ef3
title: IShellDispatch3.AddToRecent method
ms.topic: reference
ms.date: 05/31/2018
topic_type: 
- APIRef
- kbSyntax
api_name: 
- IShellDispatch3.AddToRecent
api_type: 
- COM
api_location: 
- Shell32.dll
---

# IShellDispatch3.AddToRecent method

Adds a file to the most recently used (MRU) list.

## Syntax


```JScript
IShellDispatch3.AddToRecent(
  varFile,
  [ bstrCategory ]
)
```


```VB

IShellDispatch3.AddToRecent( _
  ByVal varFile As Variant, _
  [ ByVal bstrCategory As BSTR ] _
)
```





## Parameters

<dl> <dt>

*varFile* \[in\]
</dt> <dd>

Type: **Variant**

A **String** that contains the path of the file to add to the list of recently used documents.

**Windows Vista**: Set this parameter to **null** to clear the recent documents folder.

</dd> <dt>

*bstrCategory* \[in, optional\]
</dt> <dd>

Type: **[**BSTR**](https://msdn.microsoft.com/en-us/library/ms221069(v=VS.71).aspx)**

A **String** that contains the name of the category in which to place the file.

</dd> </dl>

## Return value

### JScript

This method does not return a value.

### VB

This method does not return a value.

## Examples

The following examples show the use of **AddToRecent** for JScript, VBScript, and Visual Basic.

JScript:


```JScript
<script language="JScript">
    function fnIShellDispatch3AddToRecentJ()
    {
        var objShell = new ActiveXObject("shell.application");
        var ssfWINDOWS = 36;
        var objFolder;
        
        objFolder = objShell.NameSpace(ssfWINDOWS);
        if (objFolder != null)
        {
            var objFolderItem;
            
            objFolderItem = objFolder.ParseName("system.ini");
            if (objFolderItem != null)
            {
                objShell.AddToRecent(objFolderItem.Path);
            }
        }
    }
</script>
```



VBScript:


```VB
<script language="VBScript">
     function fnIShellDispatch3AddToRecentVB()
        dim objShell
        
        set objShell = CreateObject("shell.application")
        if (not objShell is nothing) then
            dim objFolder
            dim ssfWINDOWS
            
            ssfWINDOWS = 36
            set objFolder = objShell.NameSpace(ssfWINDOWS)
            if (not objFolder is nothing) then
                dim objFolderItem
                        
                set objFolderItem = objFolder.ParseName("system.ini")
                if (not objFolderItem is nothing) then
                    objShell.AddToRecent (objFolderItem.Path)
                end if
                set objFolderItem = nothing
            end if
            set objFolder = nothing
        end if
        set objShell = nothing
    end function
 </script>
```



Visual Basic:


```VB
Private Sub fnIShellDispatch3AddToRecent()
    Dim objShell  As Shell
    Dim objFolder As Folder
    Dim ssfWINDOWS As Long

    ssfWINDOWS = 36
    Set objShell = New Shell
    Set objFolder = objShell.NameSpace(ssfWINDOWS)
    If (Not objFolder Is Nothing) Then
        Dim objFolderItem As FolderItem

        Set objFolderItem = objFolder.ParseName("system.ini")
        If (Not objFolderItem Is Nothing) Then
            objShell.AddToRecent (objFolderItem.Path)
        End If
        Set objFolderItem = Nothing
    End If
    Set objFolder = Nothing
    Set objShell = Nothing
End Sub
```



## Requirements



|                                     |                                                                                                               |
|-------------------------------------|---------------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows XP \[desktop apps only\]<br/>                                                                   |
| Minimum supported server<br/> | Windows Server 2003 \[desktop apps only\]<br/>                                                          |
| Header<br/>                   | <dl> <dt>Shldisp.h</dt> </dl>                          |
| IDL<br/>                      | <dl> <dt>Shldisp.idl</dt> </dl>                        |
| DLL<br/>                      | <dl> <dt>Shell32.dll (version 6.0 or later)</dt> </dl> |



 

 




