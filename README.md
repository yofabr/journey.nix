# journey.nix

A personal learning log for my Nix journey.

This repository is my sandbox for exploring the Nix ecosystem in small, practical steps. Instead of trying to learn everything at once, I keep focused experiments here and document what each one teaches me.

---

## Why this repo exists

I created this repo to:

- Learn Nix by building and running real examples.
- Capture working patterns I can reuse in future projects.
- Keep my Nix knowledge in one place as a reference.

If you're also learning Nix, you can treat this repository as a lightweight notebook of experiments.

---

## What is Nix (in simple words)?

Nix is both:

1. **A package manager** — it can install tools in isolated, reproducible ways.
2. **A language** — used to describe environments, packages, and systems declaratively.

The main benefit is **reproducibility**: when something works on one machine, the same configuration should work the same way elsewhere.

---

## Repo structure

```text
.
├── README.md
└── intro/
    ├── flake.nix
    ├── flake.lock
    ├── go.mod
    └── main.go
```

### `intro/`

The `intro` folder contains an early experiment using a Nix flake with a simple Go program. It demonstrates how Nix can define and run a project environment with pinned dependencies.

---

## Getting started

### Prerequisites

- [Nix](https://nixos.org/download/) installed
- Flakes enabled (`nix --extra-experimental-features "nix-command flakes" ...`)

### Run the intro example

From the repository root:

```bash
cd intro
nix run
```

If everything is set up correctly, Nix will build/run the Go app declared by the flake.

---

## My learning journey (so far)

- **Step 1:** Set up a minimal flake.
- **Step 2:** Connected that flake to a tiny Go app.
- **Step 3:** Started using lock files (`flake.lock`) to keep inputs pinned and reproducible.
- **Step 4 (next):** Expand into dev shells, package outputs, and more multi-project patterns.

I plan to keep adding folders as I learn new Nix concepts.

---

## Nix concepts this repo is helping me understand

- **Flakes:** Project entry points with explicit inputs/outputs.
- **Locking inputs:** Repeatable builds via `flake.lock`.
- **Declarative environments:** Describe tools and dependencies in code.
- **Portable workflows:** Reduce “works on my machine” issues.

---

## Commands I use often

From inside `intro/`:

```bash
# Run the flake output
nix run

# Enter the development shell (if defined in flake.nix)
nix develop

# Show available outputs
nix flake show

# Update flake inputs
nix flake update
```

---

## Notes

This repo is intentionally simple and iterative. The goal is not perfection; it is consistent progress while learning Nix in public.

If you spot better patterns, feel free to open an issue or PR.
