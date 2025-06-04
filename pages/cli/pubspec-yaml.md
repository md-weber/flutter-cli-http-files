
# Essential Dependencies

## pubspec.yaml Setup

```yaml
name: flutter_cli_tools
description: Custom CLI tools for Flutter project

environment:
  sdk: '>=3.0.0 <4.0.0'

dependencies:
  args: ^2.4.2
  path: ^1.8.3
  yaml: ^3.1.2
  http: ^1.1.0

executables:
  flutter-env: flutter_env
  api-test: api_test
  code-gen: code_generator
```

---

# Essential Dependencies

## Dependencies

```yaml{7-11}
name: flutter_cli_tools
description: Custom CLI tools for Flutter project

environment:
  sdk: '>=3.0.0 <4.0.0'

dependencies:
  args: ^2.4.2
  path: ^1.8.3
  yaml: ^3.1.2
  http: ^1.1.0

executables:
  flutter-env: flutter_env
  api-test: api_test
  code-gen: code_generator
```
---

# Essential Dependencies

## Executables

```yaml{13-16}
name: flutter_cli_tools
description: Custom CLI tools for Flutter project

environment:
  sdk: '>=3.0.0 <4.0.0'

dependencies:
  args: ^2.4.2
  path: ^1.8.3
  yaml: ^3.1.2
  http: ^1.1.0

executables:
  flutter-env: flutter_env
  api-test: api_test
  code-gen: code_generator
```

**<tabler-tool/> Pro Tip:** Use `executables` to create global commands accessible from anywhere
