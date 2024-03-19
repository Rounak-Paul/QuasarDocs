# Application
`Quasar` `class` `QS_API`
```
Quasar/src/Core/Application.h
```

!!! abstract
    Quasar::Application is the `singleton` object responsible for the following:
    
    * Init Quasar Engine and maintain states of various components, eg. Window, Renderer etc.
    * Hosts the main application loop. This is where the main event poling is done. 
    * Shutdown the Quasar Engine on exit. Issue commands to release memory, physical decice and safely shutdown the engine.

## Methods

### get_instance

```cpp
static Application& get_instance()
```

=== "Input"
    None
=== "Output"
    Application instance reference. 
=== "Info"
    Get reference to the singleton Quasar Application instance

!!! tip
    Use the macro `QS_APPLICATION` to get the refence to the singleton Application instance.

    ```cpp
    #define QS_APPLICATION Application::get_instance()
    ```