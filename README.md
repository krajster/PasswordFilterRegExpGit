# PasswordFilter for windows
special thank's Yevgeny Menaker http://www.devx.com/security/Article/21522

Requirements:
               Visual C++ Redistributable for Visual Studio 2015 (https://goo.gl/tfO8xB)

[Install and register a Windows password filter DLL:](https://msdn.microsoft.com/en-us/library/windows/desktop/ms721766%28v=vs.85%29.aspx)

  1. Copy the PasswordFilterRegExp.dll to the Windows installation directory on the domain controller or local computer. On           standard   installations, the default folder is \Windows\System32. Make sure that you create a 32-bit password filter DLL        for 32-bit computers and a 64-bit password filter DLL for 64-bit computers, and then copy them to the appropriate location.
  2. To register the password filter, update the following system registry key:
    ```   
      HKEY_LOCAL_MACHINE\
        SYSTEM\
          CurrentControlSet\
            Control\
              Lsa\ 
                Notification Packages
    ```
      * If the Notification Packages subkey exists, add the name of your PasswordFilterRegExp.dll to the existing value data. Do not overwrite the existing values, and do not include the .dll extension.
      * If the Notification Packages subkey does not exist, add it, and then specify the name of the DLL for the value data. Do not include the .dll extension.
      * The Notification Packages subkey can add multiple packages.
  
