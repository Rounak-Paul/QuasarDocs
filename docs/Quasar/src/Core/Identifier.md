# Identifier
`Quasar`
```
Quasar/src/Core/Identifier.h
```
??? note "Author"
    [Rounak Paul](mailto:paulrounak1999@gmail.com)
    
    Dated: 19th August 2024

!!! abstract
    Identifier provides ID for owner. Here owwner can be any object. 

## Methods

### identifier_aquire_new_id
`QS_API`

```cpp
u32 identifier_aquire_new_id(void* owner)
```

=== "Input"
    owner The owner of the identifier.
=== "Output"
    The new identifier. 
=== "Info"
    Acquires a new identifier for the given owner.

### identifier_release_id
`QS_API`

```cpp
void identifier_release_id(u32 id)
```

=== "Input"
    id The identifier to be released.
=== "Output"
    void 
=== "Info"
    Releases the given identifier, which can then be used again.