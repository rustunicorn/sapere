# Conventional Commits

## Template

```bash
<type>[optional scope in ()]: <description>

[optional body]

[optional footer(s)]
```

## Types

| **Type** | **Description**                                                                          |
|----------|------------------------------------------------------------------------------------------|
| build    | build-related components (build tools, dependencies, project version etc.)               |
| chore    | miscellaneuous commits like infrastracture, deployment, backup, recovery procedures etc. |
| ci       |                                                                                          |
| docs     | affects only documentation                                                               |
| feat     | introduce a new feature                                                                  |
| fix      | patches a bug that was introduced with feat                                              |
| perf     | improves performance                                                                     |
| refactor | rewrites or restructures code without altering API or UI behavior                        |
| style    | addresses code style                                                                     |
| test     | adds missing tests or correct existing ones                                              |

## Examples

### Build

```bash
build: remove -fpermissive and fix related warnigns
```

```bash
build(deps): upgrade external-header from v1 to v3
```

```bash
build(makefile): add support for MinGW-w64 in make

Refs: #123
Fixes: jira-1234
```

### Chore

```bash
chore: init
```

```bash
chore: update .gitignore
```

### CI

```bash
ci: configure Jenkins pipeline for integration tests
```

### Documentation

```bash
docs: correct spelling of CHANGELOG
```

### Fix

```bash
fix(compiler): resolve -fpermissive compiler warning in MyClass
```

```bash
fix: resolve compiler warning for unused variable
```

```bash
fix(types): correct type mismatch causing -fpmerissive warning
```

```bash
fix: add <cstdint> include for uint32_t usage
```

In this case we were relying on indirect includes and the fix made it to conform
to the C++ Standard.

### Refactor

```bash
refactor: rename variable x to y
```
### Revert

```bash
revert: "fix null pointer handling"

Refs: <hash_1>, <hash_2>
```

### Style

```bash
style: change indentation from 2 to 4 spaces
```

