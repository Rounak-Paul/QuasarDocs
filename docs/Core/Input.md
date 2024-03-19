# Input
`Quasar` `class` `QS_API`
```
Quasar/src/Core/Input.h
```
??? note "Author"
    [Rounak Paul](mailto:paulrounak1999@gmail.com)
    
    Dated: 19th March 2024

!!! abstract
    Quasar::Input is the interface for input event handlers. Quasar Engine is using GLFW events to listen to input events.

## Methods

### init
`public` `static`

```cpp
static b8 init()
```

=== "Input"
    None
=== "Output"
    b8: TRUE if input event handlers were set to GLFW Key and Mouse callbacks successfully 
=== "Info"
    Set glfwSetKeyCallback() and glfwSetMouseButtonCallback()

---