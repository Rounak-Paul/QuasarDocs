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

### get_instance
`public` `static`

```cpp
static Input& get_instance()
```

=== "Input"
    None
=== "Output"
    Input instance reference. 
=== "Info"
    Get reference to the Input system maintained by Quasar Engine.

!!! tip
    Use the macro `QS_INPUT` to get the refence to the Input system instance.

    ```cpp
    #define QS_INPUT Input::get_instance()
    ```

---

### is_key_pressed
`private` `static`

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
`private` `static`

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

### get_key_state
`public` `static`

```cpp
static inline b32 get_key_state(KeyCode key)
```

=== "Input"
    KeyCode: Quasar KeyCode enumaration value.

=== "Output"
    State of the key(maintained by the engine). Returns b32 value.
    `0` -> key not pressed
    `1` -> key pressed
    `2` -> key is held down

=== "Info"
    Get the Keyboard Key State from the engine. Input events are resolved immidiately and updated to the engine key_state. 

---

### get_mbtn_state
`public` `static`

```cpp
static inline b32 get_mbtn_state(MouseCode btn)
```

=== "Input"
    MouseCode: Quasar MouseButton enumaration value.

=== "Output"
    State of the button(maintained by the engine). Returns b32 value.
    `0` -> key not pressed
    `1` -> key pressed

    !!! note
        No spearate output value is provided for mouse button held down.

=== "Info"
    Get the Mouse Button State from the engine. Input events are resolved immidiately and updated to the engine mouse_state. 

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