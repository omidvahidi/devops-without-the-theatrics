# DevOps Without the Theatrics (Companion Repository)
This repository accompanies the book *DevOps Without the Theatrics: How Real Organisations Build, Secure, and Run Systems*.

The examples here are intentionally small and incomplete. They exist to illustrate system boundaries, failure modes, and design intent discussed in the book, not to serve as production-ready templates.

## What this repo is for
- Minimal examples that anchor concepts from the book
- Clear separation of responsibilities between Git, CI/CD, configuration management, and IaC
- Recovery-oriented scenarios (how to get unstuck calmly)

## What this repo is not for
- A full lab environment
- A reference implementation
- A training course or step-by-step tutorial
- Vendor-specific best practice templates

## How to use it
Read the files like you read the book: to understand intent and boundaries.
If you run anything, do so only in a disposable sandbox.

## Map to book chapters
- `git/` supports Chapters 6 and 7
- `ci-cd/github-actions/` supports Chapters 8 and 9
- `config-management/ansible/` supports Chapters 11 and 12
- `infrastructure/terraform/` supports Chapters 13 to 15
- `observability/` supports Chapters 16 and 17

## License
Choose a license if you intend others to reuse this. Otherwise, keep it "all rights reserved" by omitting a license file.
