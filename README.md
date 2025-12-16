# prex

Git helper bot for resolving rebase conflicts.

## Commands

| Command | Description |
|---------|-------------|
| `prex` | Show status |
| `prex repair` | Fetch, rebase onto origin, resolve conflicts, push |
| `prex reconnect` | Disconnect and reconnect remote origin |
| `prex abort` | Abort rebase in progress |

## Workflow

```
prex repair
    │
    ├── Fetch origin
    │
    ├── Rebase onto origin/branch
    │       │
    │       └── If conflict:
    │               ├── Open file in vim
    │               ├── You fix and :wq
    │               ├── Stage file
    │               └── Repeat until clean
    │
    ├── Push to origin
    │
    └── Done
```

## Typical Use Case

You edited a file on GitHub, forgot to pull, made local commits. Now `git push` fails.

```bash
prex repair
```

Fix any conflicts in vim, save, and prex handles the rest.

