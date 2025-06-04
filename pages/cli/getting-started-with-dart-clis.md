# Getting Started with Dart CLIs
## Create a dart cli project

<br>

```bash
[terminal.app]
>>>  dart create -t cli demo-cli
```

This will create you the boilerplate with a bin/main.dart file.

---

# Getting Started with Dart CLIs

## CLI flags

```dart
  [bin/flutter_env.dart]
  [...]
  parser.addFlag('help', 
    abbr: 'h', 
    help: 'Show usage information'
  );
  [...]
```

```bash
[terminal.app]
>>> flutter-env -h

> Flutter Environment Config Generator
> Usage: dart run flutter_env --env=dev
> -e, --env          Environment to generate config for
>                    [dev (default), staging, prod]
> -h, --[no-]help    Show usage
```

---

# Getting Started with Dart CLIs

## Adding Options to the CLI

```dart
[bin/flutter_env.dart]
  ...
  parser.addOption(
    'env',
    abbr: 'e',
    allowed: ['dev', 'staging', 'prod'],
    defaultsTo: 'dev',
    help: 'Environment to generate config for',
  );
```

```bash
[terminal.app]
➜  dart-cli-example flutter-env --env prod

> 🔧 Generating config for prod environment...
> ✅ Generated lib/app_config.dart for prod
> 📄 API URL: https://api.myapp.com
> 🐛 Debug Mode: false
```
