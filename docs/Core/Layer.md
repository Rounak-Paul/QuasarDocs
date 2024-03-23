# Input
`Quasar` `class` `QS_API`
```
Quasar/src/Core/Layer.h
```
??? note "Author"
    [Rounak Paul](mailto:paulrounak1999@gmail.com)
    
    Dated: 23rd March 2024

!!! abstract
    Quasar::Layer is the pure virtual class to be used in the user application layer. The layers are managed and layer methods are executed by the Quasar Engine. This virtual class is the intended way to inject functionality in the Engine from user space.

## Methods

### Layer
`public` `constructor`

```cpp
Layer(const std::string& name = "Layer")
```

=== "Input"
    * const std::string& name - provided name if the layer, default value "Layer".
=== "Output"
    N/A
=== "Info"
    constructor of the virtual class Layer. 

---

### attach
`public` `virtual`

```cpp
virtual void attach()
```

=== "Input"
    None
=== "Output"
    void
=== "Info"
    This method is called with Application::push_layer(Layer* layer) call. Overwrite this method's contents to initilize the user defined Layer.

---

### detach
`public` `virtual`

```cpp
virtual void detach() 
```

=== "Input"
    None
=== "Output"
    void
=== "Info"
    This method is called with the destructor of Quasar::LayerStack. Use can call this method anytime to detach a layer from the layerStack maintained by the engine.

---

### update
`public` `virtual`

```cpp
virtual void update(f32 dt) 
```

=== "Input"
    * f32 dt - delta time between frames, calculated by the Quasar Engine.
=== "Output"
    void
=== "Info"
    This method is called at every frame of the Application::run() loop. Update functionality to be injected to the engine by user application. 

---

### late_update
`public` `virtual`

```cpp
virtual void post_update() 
```

=== "Input"
    None
=== "Output"
    void
=== "Info"
    This method is called at every frame of the Application::run() loop. To update the calculated values this method is called after Layer::update() and main render task .

---