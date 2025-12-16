# Prex 🤖 

༼ つ ◕_◕ ༽つ ----- ("Must fix it")

**Prex** is my github bot that lives in my terminal and makes my life easier by guiding me through github conflicts



### Motivation

Navigating divergent or unresolved github commits is perhaps one of the most frustrating issues that I fall victim to during my programming workflows. I never considered myself the savviest at git maintenace, and to be honest, I've come to terms that I don't really need to be. Whenever I am absorbed in my coding project, the last thing I want is my workflow to be interupted by silly github conflict. I finally grew sick of this and built prex.

### Future Work
The premises of prex actually stems from a more advanced CLI-style triage bot that I intend to develop in greater detail in the future. His name, Prex, is actually an abbreviation of "Pull Request Execution" since his design objective was to utilize github's webhooks to work alongside me in github itself and the terminal to streamline pull request merging and work scheduling. 



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
