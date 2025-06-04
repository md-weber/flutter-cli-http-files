# Activate the CLI

## Global activiation should be done to enable the CLI

```bash
[terminal.app]
>>> dart pub global activate --source path .

...
>>> flutter-env -h
>>> flutter-env --env dev
>>> flutter-env --env staging
>>> flutter-env --env prod
```

--- 

# Build an Executable
## Superpower for your performance 

<br>

```bash
>>> dart compile exe bin/flutter_env.dart -o flutter_env

>>> ./flutter_env
```

<br>

**<tabler-tool/> Pro Tip:** Add this file now to your PATH env to use it globally

---

# Demo Time! <tabler-rocket />
## Real world examples from sevdesk (sevmcli)

<div grid="~ cols-2">
<div class=p-4>
    <ul>
      <li>Dependency Graph generation</li>
      <li>Upgrade DCM</li>
      <li>Update Versions before release</li>
      <li>Create invoices in Bulk</li>
    </ul>
  </div>
  <div class="p-4">
    <img class="rounded-xl" src="../../assets/img/demo-time.png" width=250 />
  </div>
</div>

---

# Best Practices: CLI Development

<div grid="~ cols-2 gap-4">
<div>

## Code Organization
- Single responsibility per CLI
- Modular command structure  
- Reusable utility functions
- Clear error handling
- Comprehensive logging

</div>
<div>

## User Experience
- Helpful error messages
- Progress indicators
- Colored output
- Interactive prompts
- Documentation

</div>
</div>

---

# Recap

## Dart CLIs are for you!

<br>

- Platform independent
- Super flexible for any use case you can think of
- Same programming language as the project makes support easy

