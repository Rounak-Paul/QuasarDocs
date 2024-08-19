# class QS_API SystemManager
`Quasar` `class` `QS_API`
```
Quasar/src/Core/SystemManager.h
```
??? note "Author"
    [Rounak Paul](mailto:paulrounak1999@gmail.com)
    
    Dated: 19th August 2024

!!! abstract
    Quasar::SystemManager is the `singleton` object responsible for the following:
    
    * Create and manage all system's states in Quasar Engine
    * Register system to a state array, Unregister system with id
    * Provide access to the system states with defines

## Methods

### init
`public` `static`

```cpp
static b8 init()
```

=== "Input"
    None
=== "Output"
    true if the system manager is successfully initialized 
=== "Info"
    gurentees the SystemManager is a singleton class
    allocates the state array

---

### shutdown
`public`

```cpp
void shutdown()
```

=== "Input"
    None
=== "Output"
    void 
=== "Info"
    cleans up any remaining registered systems and free the state array

---

### get_instance
`public` `static`

```cpp
static SystemManager& get_instance()
```

=== "Input"
    None
=== "Output"
    reference to the SystemManager instance 
=== "Info"
    ...

!!! tip
    Use the macro `QS_SYSTEM_MANAGER` to get the refence to the singleton SystemManager instance.

    ```cpp
    #define QS_SYSTEM_MANAGER SystemManager::get_instance()
    ```

---

## Systems & Defines

System manager provides `defines` to access the Systems managed by it. 

```cpp
#define QS_EVENT (*(Event*)QS_SYSTEM_MANAGER.get_system(SYSTEM_EVENT))
```
```cpp
#define QS_INPUT (*(Input*)QS_SYSTEM_MANAGER.get_system(SYSTEM_INPUT))
```
```cpp
#define QS_RESOURCE_SYSTEM (*(ResourceSystem*)QS_SYSTEM_MANAGER.get_system(SYSTEM_RESOURCE))
```
```cpp
#define QS_SHADER_SYSTEM (*(ShaderSystem*)QS_SYSTEM_MANAGER.get_system(SYSTEM_SHADER))
```
```cpp
#define QS_RENDERER_API (*(Renderer::API*)QS_SYSTEM_MANAGER.get_system(SYSTEM_RENDERER))
```
```cpp
#define QS_JOB_SYSTEM (*(JobSystem*)QS_SYSTEM_MANAGER.get_system(SYSTEM_JOB))
```
```cpp
#define QS_TEXTURE_SYSTEM (*(TextureSystem*)QS_SYSTEM_MANAGER.get_system(SYSTEM_TEXTURE))
```
```cpp
#define QS_FONT_SYSTEM (*(FontSystem*)QS_SYSTEM_MANAGER.get_system(SYSTEM_FONT))
```
```cpp
#define QS_MATERIAL_SYSTEM (*(MaterialSystem*)QS_SYSTEM_MANAGER.get_system(SYSTEM_MATERIAL))
```
```cpp
#define QS_RENDER_VIEW_SYSTEM (*(RenderViewSystem*)QS_SYSTEM_MANAGER.get_system(SYSTEM_RENDER_VIEW))
```
```cpp
#define QS_GEOMETRY_SYSTEM (*(GeometrySystem*)QS_SYSTEM_MANAGER.get_system(SYSTEM_GEOMETRY))
```
```cpp
#define QS_WATCH_SYSTEM (*(Watcher*)QS_SYSTEM_MANAGER.get_system(SYSTEM_WATCHER))
```
```cpp
#define QS_LIGHT_SYSTEM (*(LightSystem*)QS_SYSTEM_MANAGER.get_system(SYSTEM_LIGHT))
```

