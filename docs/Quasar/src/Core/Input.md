# class QS_API Input : public System
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
`public`

```cpp
virtual b8 init(void* config) override
```

=== "Input"
    None
=== "Output"
    true if input event handlers were set to GLFW Key and Mouse callbacks successfully 
=== "Info"
    Set glfwSetKeyCallback() and glfwSetMouseButtonCallback()

---

### shutdown
`public`

```cpp
virtual void shutdown() override
```

=== "Input"
    None
=== "Output"
    void 
=== "Info"
    Does nothing currently

---

### get_key_state
`public`

```cpp
QS_INLINE b32 get_key_state(KeyCode key)
```

=== "Input"
    key KeyCode for the key's state
=== "Output"
    0: key is released
    1: key is pressed
    2: key is held down
=== "Info"
    Index into the Input System's keys array to get the current state of the KeyCode

---

### get_mbtn_state
`public`

```cpp
QS_INLINE b32 get_mbtn_state(MouseCode btn)
```

=== "Input"
    btn MouseCode for the Mouse btn's state
=== "Output"
    0: key is released
    1: key is pressed
    2: key is held down (this may not be working currently)
=== "Info"
    Index into the Input System's mouse_state to get the current state of the MouseCode

---

### get_mouseX
`public`

```cpp
f64 get_mouseX()
```

=== "Input"
    None

=== "Output"
    float MouseX 

=== "Info"
    position of the mouse cursor in a coordinate system originating from the top left of the window, right is positive X axis

---

### get_mouseY
`public`

```cpp
f64 get_mouseY()
```

=== "Input"
    None

=== "Output"
    float MouseY 

=== "Info"
    position of the mouse cursor in a coordinate system originating from the top left of the window, bottom is positive Y axis

---

### get_mouseXDT
`public`

```cpp
f64 get_mouseXDT()
```

=== "Input"
    None

=== "Output"
    float delta MouseX since last frame 

=== "Info"
    holds previous mouse pos and calculates delta

---

### get_mouseYDT
`public`

```cpp
f64 get_mouseYDT()
```

=== "Input"
    None

=== "Output"
    float delta MouseY since last frame  

=== "Info"
    holds previous mouse pos and calculates delta

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
    glfw callback function
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
    glfw callback function
    sets `context.data.u16[0] = button` and Executes event `QS_EVENT.Execute(action ? EVENT_CODE_BUTTON_PRESSED : EVENT_CODE_BUTTON_RELEASED, 0, context)`  with the context.

---