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

### is_key_pressed
`public` `static`

```cpp
static void is_key_pressed(GLFWwindow* window, int key, int scancode, int action, int mods)
```

=== "Input"
    * GLFWwindow* window - Pointer to the Main GLFW window object
    * int key - keycode of the keyboard key press event
    * int scancode - N/A
    * int action - N/A
    * int mods - N/A

=== "Output"
    void 

=== "Info"
    sets `context.data.u16[0] = key` and Executes event `QS_EVENT.Execute(action ? EVENT_CODE_KEY_PRESSED : EVENT_CODE_KEY_RELEASED, 0, context)`  with the context.

---

### is_mousebtn_pressed
`public` `static`

```cpp
static void is_mousebtn_pressed(GLFWwindow* window, int button, int action, int mods);
```

=== "Input"
    * GLFWwindow* window - Pointer to the Main GLFW window object
    * int button - mouse button of the mouse key press event
    * int action - N/A
    * int mods - N/A

=== "Output"
    void 

=== "Info"
    sets `context.data.u16[0] = button` and Executes event `QS_EVENT.Execute(action ? EVENT_CODE_BUTTON_PRESSED : EVENT_CODE_BUTTON_RELEASED, 0, context)`  with the context.

---

### get_mouse_position
`public` `static`

```cpp
static glm::vec2 get_mouse_position()
```

=== "Input"
    None

=== "Output"
    glm::vec2 of (x, y) positions of mouse relative to the Window 

=== "Info"
    Get MouseX and MouseY relative to the top left corner of the Main window 

---

### get_mouseX
`public` `static`

```cpp
static f32 get_mouseX()
```

=== "Input"
    None

=== "Output"
    float MouseX 

=== "Info"
    Calls get_mouse_position() to get MouseX

---

### get_mouseY
`public` `static`

```cpp
static f32 get_mouseY()
```

=== "Input"
    None

=== "Output"
    float MouseY 

=== "Info"
    Calls get_mouse_position() to get MouseY