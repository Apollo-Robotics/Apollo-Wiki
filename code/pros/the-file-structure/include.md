---
description: The include Directory
---

# include

The `/include` directory of the PROS files is where any and all header files should live.

Header files are files that store function declarations, class declarations, and other such declarations. Typically, these are created to share information between source files. These files use the extension `.h` or `.hpp`.

### Includes

On the topic of includes, what to do if you want to include a function from another location?!

In an include file, somewhere, add the function you want to include (to keep yourself organized, you can create a header file with the same name and in the same relative location as your C++ file).

Typically, for functions and variables like `void`, `int`, `double`, most `classes`, etc. you add the keyword `extern` before declaring the function or variable.

Following the definition, either add a `;` for variables, or a `();`for functions with definitions. SInce you've already supposedly defined these pieces of code in a `.cpp` file somwhere, you dont need to re-define them again. \
Here's an example

{% code title="robopt_config.cpp" overflow="wrap" lineNumbers="true" %}
```cpp
#include "main.h"

pros::Motor intake(1);
bool is_intake_spinning = false;
```
{% endcode %}

{% code title="robot_config.hpp" overflow="wrap" lineNumbers="true" %}
```cpp
#pragma once
#include "api.h"

extern pros::Motor intake();
extern bool is_intake_spinning;
```
{% endcode %}

Now simply include the `.hpp` file with your function delcaration in the file you want to use it in

{% code title="main.cpp" overflow="wrap" lineNumbers="true" %}
```cpp
#include "main.h"
#include "robot_config.hpp"

void intake_control(){
    if(is_intake_spinning){
        intake.move_voltage(11000);
        .....
    }
}
```
{% endcode %}

### Notes about includes

When making include files, its important to note a few things.

* You don't nessecarily have to make an include file with the same name as your source file! Most coders do it for simplicity and readability as well as overall organization.
*   In your include file, you should add the line `#pragma once` as added in the examples above. The `#pragma` keyword is a compiler-specific keyword that lets the compiler (in this case PROS) when to and how many times to compile this file, in the event of a drastic code change or state chance, or otherwise.

    We use `#pragma once` to tell PROS to compile a specific file once, and only once when building our code for upload.
* You can 'nest' includes! This is mainly applicable for 2 reasons:
  * When your declarations require the use of a PROS file or other files, such as motor or other device definitions
  * Instead of including all of your files into `main.h` , you can make smaller-sub includes that can be easily added to `main.h` or other files when you dont want to include a bunch of extra files (this is more applicable for larger code templates and project but nonetheless is still a cool use of includes!)
