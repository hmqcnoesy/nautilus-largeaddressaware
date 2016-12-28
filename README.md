# Nautilus: largeaddressaware
Instructions on how to make a large address aware copy of Nautilus, for use with extensions with large RAM requirements.

Assuming Visual Studio 2015 installed:

Copy the files (no need to copy any folders) from original installation location 
(e.g. `c:\program files (x86)\thermo\nautilus`) into new location (e.g. `c:\app\nautilus`).

Clear the read-only flag on new nautilus.exe (this is important – editbin.exe 
will fail if exe is read-only).

Open cmd as administrator

Run command:  `"C:\Program Files (x86)\Microsoft Visual Studio 11.0\VC\bin\vcvars32.bat"`

Run command: 

```
"C:\Program Files (x86)\Microsoft Visual Studio 11.0\VC\bin\editbin.exe" /largeaddressaware E:\app\nautilus\nautilus.exe
```

(optional) Verify using `dumpbin.exe /headers` that the new nautilus.exe shows “Application can handle large (>2GB) addresses” 

Run the edited copy of Nautilus from new location.
