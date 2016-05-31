---
title: "Overriding CLI defaults"
order: 300
---

The following files may be used to override CLI defaults:

- `.convox/app`
    The contents of this file will be used as the default app name.

    Example file contents: `myapp`

    <div class="block-callout block-show-callout type-info" markdown="1">
    Convox will use this value instead of inferring the app name from the current directory name.
    </div>

- `.convox/sync`
    Synchronize local file changes into the running containers.

    Valid options: `true`, `false`

