---
-api-id: M:Windows.Security.EnterpriseData.FileRevocationManager.CopyProtectionAsync(Windows.Storage.IStorageItem,Windows.Storage.IStorageItem)
-api-type: winrt method
---

<!-- Method syntax
public Windows.Foundation.IAsyncOperation<bool> CopyProtectionAsync(Windows.Storage.IStorageItem sourceStorageItem, Windows.Storage.IStorageItem targetStorageItem)
-->

# Windows.Security.EnterpriseData.FileRevocationManager.CopyProtectionAsync

## -description
> [!NOTE]
> [FileRevocationManager](filerevocationmanager.md) may be unavailable for releases after Windows 10. Instead, use [FileProtectionManager](fileprotectionmanager.md).



> [!NOTE]
> Windows Information Protection (WIP) policy cannot be applied on Windows 10, version 1511 (build 10586) or earlier.

Copy the selective wipe protection state of a file or folder to a new file or folder.

## -parameters
### -param sourceStorageItem
The source item to copy the selective wipe protection status from.

### -param targetStorageItem
The target item to copy the selective wipe protection status to.

## -returns
True if the copy operation was successful; otherwise false.

## -remarks
If you save a new copy of a file as the result of a "save as" operation, the selective wipe protection status is not copied with the file. To protect the file, you must call the CopyProtectionAsync method to copy the existing protection status to the new file. If you copy a protected file using the [CopyAsync](../windows.storage/istoragefile_copyasync_1709017142.md) or [CopyAndReplaceAsync](../windows.storage/istoragefile_copyandreplaceasync_177558079.md) methods, the selective wipe protection status is copied with the file and you do not need to call the CopyProtectionAsync method. 



[!code-csharp[_CopyProtection](../windows.security.enterprisedata/code/SelectiveWipeSnippets/cs/MainPage.xaml.cs#Snippet_CopyProtection)]

[!code-js[_CopyProtection_JS](../windows.security.enterprisedata/code/SelectiveWipeSnippets/js/default.js#Snippet_CopyProtection_JS)]



The CopyProtectionAsync method requires exclusive access to the file or folder being encrypted, and will fail if another process is using has a handle open to the file or folder.

## -examples

## -see-also
[FileRevocationManager sample](http://code.msdn.microsoft.com/windowsapps/File-Revocation-Manager-0d529428), [How to protect files with Selective Wipe  (C#/VB/C++)](https://docs.microsoft.com/previous-versions/windows/apps/dn456782(v=win.10)), [How to protect files with Selective Wipe (JavaScript)](https://docs.microsoft.com/previous-versions/windows/apps/dn456781(v=win.10))
