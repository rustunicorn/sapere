# Move Semantics

## Setter

Problem:

```cpp
// 100% alloc if long enough
void MyClass::set_str(string s) {
    m_str = std::move(s); // capacity will always be copied
}
```

Better: Overload as follows:

```cpp
// No alloc
void MyClass::set_str(string&& s) {
    m_str = move(s);
}

// <<50% alloc
void MyClass::set_str(const string& s) {
    m_str = s; // capacity will be the bigger one
}
```

