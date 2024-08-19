# EntryPoint
`Quasar` `class` `QS_API`
```
Quasar/Include/EntryPoint.h
```
??? note "Author"
    [Rounak Paul](mailto:paulrounak1999@gmail.com)
    
    Dated: 19th August 2024

!!! abstract
    Hosts the main() function. The extern function CreateApplication() is called to create an app and call its run() function. 

## Methods

### main
`main`

```cpp
int main(int argc, char** argv)
```

=== "Input"
    cpp main application inputs
=== "Output"
    error code of the application run 
=== "Info"
    the entrry point for the cpp program

!!! tip

    ```cpp
    int main(int argc, char** argv) {
        auto app = Quasar::CreateApplication(); // allocates and returns new application
        app->run();
        delete app;

        return 0;
    }
    ```
---
