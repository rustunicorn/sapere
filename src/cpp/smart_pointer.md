# Smart Pointer

## Passing Unique Pointer

| **Type**           | **When?**                    |
|--------------------|------------------------------|
| by-value           | consumes T                   |
| by-reference       | will or might reseat pointer |
| by-const-reference | never                        |

## Passing Shared Pointer

| **Type**           | **When?**                      |
|--------------------|--------------------------------|
| by-value           | share - will retain refcounter |
| by-reference       | will or might reseat pointer   |
| by-const-reference | might retaiin recounter        |

## Global `shared_ptr`

```cpp
//global (static or heap) or aliased local
... shared_ptr<Widget> g_p ...

void f(Widget& w) {
    g();
    use(w);
}

void g() {
    g_p = ... // Might release last reference count
}

void my_coide() {
    f(*g_p); // Passing *nonlocal
}
```

<div class="warning">
Don't derefence a nonlocal, possibly unaliased, shared pointer. Instead use the following:

```cpp
void my_code() {
    auto p = g_p; // +1 for whole tree
    f(*p);        // Ok, local *
    p->foo();     // Ok, local ->
}
```
</div>

## `auto` and Polymorphism

```cpp
auto pb = unique_ptr<Base>{ make_unique<Derived>() };
```

