# Contributing to backlog

Thanks for your interest in contributing!

## Branching Strategy

This project uses a simple Git Flow-inspired workflow:

```
master (stable releases)
  │
  └── develop (integration branch)
        │
        ├── feature/xxx (new features)
        └── fix/xxx (bug fixes)
```

### Branches

- **`master`** - Stable, released code. Each commit is tagged with a version (e.g., `v0.1.0`). Only merge from `develop` when releasing.
- **`develop`** - Integration branch for ongoing work. All features and fixes merge here first.
- **`feature/*`** - Feature branches (e.g., `feature/add-priority-levels`)
- **`fix/*`** - Bug fix branches (e.g., `fix/crash-on-empty-list`)

### Workflow

1. **Start a feature or fix:**
   ```bash
   git checkout develop
   git pull
   git checkout -b feature/my-feature
   ```

2. **Make your changes, commit often:**
   ```bash
   git add .
   git commit -m "Add cool new feature"
   ```

3. **Push and open a PR to `develop`:**
   ```bash
   git push -u origin feature/my-feature
   # Open PR on GitHub targeting 'develop'
   ```

4. **After review, merge to `develop`**

### Releasing

When `develop` is ready for release:

1. Merge `develop` into `master`
2. Update version in `Cargo.toml`
3. Tag the release: `git tag -a v0.2.0 -m "Release v0.2.0"`
4. Push: `git push origin master --tags`
5. Publish: `cargo publish`

## Versioning

We use [Semantic Versioning](https://semver.org/):

- **MAJOR** (1.0.0) - Breaking changes
- **MINOR** (0.2.0) - New features, backwards compatible
- **PATCH** (0.1.1) - Bug fixes, backwards compatible

## Development

```bash
# Build
cargo build

# Run tests
cargo test

# Run locally
cargo run -- add "test item"
cargo run -- cli

# Install locally for testing
cargo install --path .
```

## Code Style

- Run `cargo fmt` before committing
- Run `cargo clippy` and address warnings
- Keep commits focused and well-described
