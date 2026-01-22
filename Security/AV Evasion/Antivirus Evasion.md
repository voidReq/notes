# Techniques
Renaming/comment removal: Suitable for non-compiled languages (e.g., .ps1, .py)
Loaders: Encrypt the file, and progressively decrypt it while loading it into memory. (NOTE: file should be included in the loader, downloading from internet often flags)
Signing: Getting a valid signature from a CA will bypass most things on totalvirus, & aid in evading windefender
Use DLLs--simply put, detected less
Find a way to inject into another process


# Sandbox evasion
Sleep before execution (maybe the user will get bored)
Check machine resources (Often Sandboxes/VMs have very little)
Check against common sandbox names