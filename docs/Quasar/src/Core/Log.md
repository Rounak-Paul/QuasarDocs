# Log
`Quasar` `class` `QS_API`
```
Quasar/src/Core/Log.h
```

??? note "Author"
    [Rounak Paul](mailto:paulrounak1999@gmail.com)
    
    Dated: 19th March 2024

!!! abstract
    Quasar::Log is the logging pipeline for Quasar Engine and Any application using this Engine.
    Logging has been enabled via some `defines` to easily be able to put logs to this pipeline. 
    This generates a Log file in the root directory of the runtime. This log is also displayed in the Editor's UI

## Defines

---

### Quasar Core Logger

!!! info 
    Core logger is to be used in the devlopment of Quasar Engine Dynamic Library.

!!! example "usage examples"

    * QS_CORE_FATAL
        ```cpp
        QS_CORE_FATAL("fatal event! code %d", fatal_code)
        ```

    * QS_CORE_ERROR
        ```cpp
        QS_CORE_ERROR("error event! code %s", __line__)
        ```

    * QS_CORE_WARN
        ```cpp
        QS_CORE_WARN("warning event! value %d not expected", value) 
        ```

    * QS_CORE_INFO
        ```cpp
        QS_CORE_INFO("Vulkan supported GPUs found %d", device_count)
        ```

    * QS_CORE_DEBUG
        ```cpp
        QS_CORE_DEBUG("Created main window!")
        ```

    * QS_CORE_TRACE
        ```cpp
        QS_CORE_TRACE("FPS: %f", 1/dt)
        ```

---

### Quasar Application Logger

!!! info 
    App logger is to be used in the devlopment of editor or any games created with Quasar Engine.

!!! example "usage examples"

    * QS_APP_FATAL
        ```cpp
        QS_APP_FATAL("fatal event! code %d", fatal_code)
        ```

    * QS_APP_ERROR
        ```cpp
        QS_APP_ERROR("error event! code %s", __line__)
        ```

    * QS_APP_WARN
        ```cpp
        QS_APP_WARN("warning event! value %d not expected", value) 
        ```

    * QS_APP_INFO
        ```cpp
        QS_APP_INFO("Vulkan supported GPUs found %d", device_count)
        ```

    * QS_APP_DEBUG
        ```cpp
        QS_APP_DEBUG("Created main window!")
        ```

    * QS_APP_TRACE
        ```cpp
        QS_APP_TRACE("FPS: %f", 1/dt)
        ```