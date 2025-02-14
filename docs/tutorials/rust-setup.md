# Setting up a dev container for Rust
* Primary author: [Shanyu Gowdu](https://github.com/gowdu0)
* Reviewer: [Chris Zou](https://github.com/chzou123)

## Prerequisites
- VS Code with Dev Containers extension
- Docker installed and running
- Git installed
- Basic terminal knowledge

## Step 1: Project Initialization
```bash
# Create project directory
mkdir comp423-rust
cd comp423-rust

# Initialize Git repository
git init
```

## Step 2: Dev Container Configuration
1. Create `.devcontainer/devcontainer.json`:
```json
{
    "name": "COMP423 Rust Environment",
    "image": "mcr.microsoft.com/devcontainers/rust:latest",
    "customizations": {
        "vscode": {
            "extensions": ["rust-lang.rust-analyzer"]
        }
    }
}
```

Key configuration elements:
- Uses Microsoft's official Rust development container
- Installs rust-analyzer for IDE features
- Includes latest stable Rust toolchain

## Step 3: Create Rust Project
```bash
# Create binary project without automatic Git init
cargo new hello-comp423 --bin --vcs none

# Add files to Git
git add .
git commit -m "Initial project setup"
```

## Step 4: Implement Hello World
1. Edit `src/main.rs`:
```rust
fn main() {
    println!("Hello COMP423!");
}
```

## Step 5: Build and Run
```bash

# Navigate to project root
cd /workspaces/RustSetup/comp423-rust/hello-comp423

# Build project (creates target/debug/hello-comp423)
cargo build

# Run directly from build output
./target/debug/hello-comp423

# Or build and run in one step
cargo run
```

Expected output:
```text
Hello COMP423!
```

## Workflow Explanation
```bash
# Full development workflow
cargo new <project-name> --bin --vcs none  # Project creation
cargo build                               # Compilation
cargo run                                 # Executions
cargo check                               # Quick compile check
```

## Verification Checklist
- [ ] Dev Container starts successfully
- [ ] `rustc --version` shows recent version
- [ ] `cargo run` outputs "Hello COMP423!"
- [ ] Project committed to Git repository
```
