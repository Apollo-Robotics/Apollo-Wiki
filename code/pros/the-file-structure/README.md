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

Most folders and files are left untouched but others can be edited by the user for basic project settings.&#x20;

The following pages go into more detail about what each of these folders and files do, as well as how to use them!
