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
`public` `static`

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

---

### get_main_window
`public`

```cpp
Window& get_main_window()
```

=== "Input"
    None
=== "Output"
    Reference to the Main window used by singleton Application. 
=== "Info"
    Get reference to the main window used by the Engine.

!!! tip
    Use the macro `QS_MAIN_WINDOW` to get the refence to the window used by main Application.

    ```cpp
    #define QS_MAIN_WINDOW QS_APPLICATION.get_main_window()
    ```

---

### get_app_state
`public`

```cpp
app_state& get_app_state()
```

=== "Input"
    None
=== "Output"
    Reference to the Application state managed by the Engine. 
=== "Info"
    This state is created and passed to the engine at the time of Application creation.

!!! tip
    Use the macro `QS_APP_STATE` to get the refence to the Application state.

    ```cpp
    #define QS_APP_STATE QS_APPLICATION.get_app_state()
    ```

---

### run
`public`

```cpp
void run();
```

=== "Input"
    None
=== "Output"
    Void
=== "Info"
    Hosts the main application loop.