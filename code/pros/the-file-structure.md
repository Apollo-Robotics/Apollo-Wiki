# The File Structure

Since PROS uses the C++ language, it follows C++'s suggested project structure:

```
project_name/
├── CMakeLists.txt
├── include/
│ ├── project_name/ 
│ │ ├── header1.h 
│ │ └── header2.h
│ └── other_headers/
│ ├── header3.h
│ └── header4.h
├── src/
│ ├── main.cpp
│ └── other_source_files.cpp
├── test/
│ ├── test1.cpp
│ └── test2.cpp
└── README.md
```

The PROS Project File structure is similar to the above but has some additions:

<pre><code>project_name/
├── .d/
├── .vscode/
├── bin/
├── firmware/
├── include/
│ ├── libvgl/ 
│ ├── okapi/ 
│ ├── pros/ 
│ ├── api.h
<strong>│ └── main.h
</strong>├── src/
│ └── main.cpp
├── .gitignore
├── common.mk
├── compille_commands.json
├── Makefile
└── project.pros
</code></pre>

Most folders and files are left untouched but others can be edited by the user for basic project settings

## project.pros

project.pros is the user-configurable part of the project. It modifies the project name that's displayed on the brain and during compiles, the slot number, the project icon that's displayed on the brain, etc.

<figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

When opened in VSCode, the PROS Extension generates a more user-friendly interface for changing these settings. Sometimes the extensions gets finnicky and it becomes difficult to edit these settings, but just be patient!

More advanced PROS users can also choose to edit the file in text form, which can be done by right-clicking on the file in the explorer tab, and selecting `Open With`. VSCode will prompt you to choose between the default PROS extension or it's own built-in text editor

<div align="center" data-full-width="true">

<figure><img src="../../.gitbook/assets/image (5).png" alt="" width="404"><figcaption></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/image (6).png" alt="" width="563"><figcaption></figcaption></figure>

</div>

When editing the text version of this file, its important that you know what you are doing and dont change anything else unless need be!

\
I usually edit these settings at the beginning and ends of the file

<figure><img src="../../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>
