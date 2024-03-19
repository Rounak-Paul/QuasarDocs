# Application
`Quasar` `class` `QS_API`
```
Quasar/src/Core/Application.h
```

!!! info
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