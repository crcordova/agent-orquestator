# CLI Tool

## Architecture Patterns
- Command → subcommand → flags/args pattern
- Input validation at the boundary
- Separation: parsing → business logic → output formatting
- Exit codes for machine consumption
- Stdout for data, stderr for messages

## Key Decisions
- [ ] Language (Go, Rust, Node.js, Python, Deno)
- [ ] CLI framework (Cobra, Clap, Commander, Click, Typer, Oclif)
- [ ] Config file location and format
- [ ] Output format (text, JSON, table, YAML)
- [ ] Distribution method (binary, npm, pip, brew)
- [ ] Auto-update mechanism

## Standard Slices
1. Project scaffolding and CLI framework setup
2. Command structure and argument parsing
3. Configuration loading (env, config file, flags)
4. Core business logic
5. Output formatting
6. Error handling and exit codes
7. Help text and documentation
8. Shell completions
9. Testing
10. Packaging and distribution

## CLI Design
```
mytool <command> [subcommand] [flags] [args]

Commands:
  init        Initialize a new project
  build       Build the project
  deploy      Deploy to target environment
  config      Manage configuration

Flags:
  --verbose, -v    Enable verbose output
  --json           Output as JSON
  --config, -c     Config file path
  --help, -h       Show help
  --version        Show version
```

## Exit Codes
| Code | Meaning |
|------|---------|
| 0 | Success |
| 1 | General error |
| 2 | Invalid usage/args |
| 3 | Configuration error |
| 4 | Network error |

## Testing Strategy
- Unit tests for business logic
- Snapshot tests for output formatting
- Integration tests for command execution
- Fixture-based tests for file operations
