# x.AGENTS.md

A comprehensive coding style and operational protocol for AI agents. This repository contains the AGENTS protocol — a set of mandatory rules, best practices, and operational guidelines that AI agents must follow when writing code in any language.

## Overview

The AGENTS protocol is designed to produce code that is maintainable, secure, and reliable. It is written in the style of the Linux kernel coding style: concise, direct, and uncompromising about quality. Every line of code must have a reason. Every error must have a message. Every failure must be loud, immediate, and obvious.

The protocol is organized into a core document and language-specific satellite files. The core document establishes universal principles that apply across all languages and domains. The satellite files provide language-specific guidance, including required linters, idiomatic patterns, and common pitfalls to avoid.

## Structure

### Core Protocol

The main document (`AGENTS/AGENTS.md`) contains ten foundational sections:

1. **The Prime Directive: Don't Know — Don't Do** — Unwritten code is better than badly written code. If you do not understand the requirement, stop and ask.
2. **The Operator's Time Is Finite — Act Like It** — Plan the entire task, batch your work, and minimize round-trips with the operator.
3. **Operational Workflow: Plan, Confirm, Execute, Report** — A disciplined workflow that ensures every task is thought through, approved, and completed systematically.
4. **Fast Fail and Hard Fail** — Detect errors early and crash with clear messages. Silent failures are infinitely worse than crashes.
5. **Error Messages Must Be Useful** — Every error message must answer what happened, where it happened, and what the actual vs expected value was.
6. **Linting: No Exceptions, No Suppressions** — If a linter exists for the language, code must pass it cleanly. Suppressions are not acceptable.
7. **Common Agent Mistakes and Delusions** — A catalog of typical errors agents make, including context drift and over-engineering.
8. **The Runpoint Protocol** — How to document incomplete work when execution is interrupted.
9. **The PLAN.md Contract** — How to write atomic, specific plans before touching any code.
10. **Message to a Reviewing Agent** — A template for passing context when delegating review to another agent.

### Satellite Files

Language-specific and topic-specific satellite files extend the core protocol with detailed guidance:

- **Topic-specific**: Secrets & Credentials, Git Discipline, Docker & Containers, SQL & Databases
- **Language-specific**: Python, C, C++, Rust, Java, Kotlin, Go, C# / .NET, Swift, JavaScript / TypeScript, CSS / SCSS, Shell Scripts (Bash/Zsh)
- **Testing**: General principles, testing pyramid (white/grey/black box), and concrete examples

Each satellite file includes:
- Minimum required linters and installation instructions
- Best practices and idiomatic usage
- Common mistakes and pitfalls
- Language-specific operational patterns

## Key Principles

### Code Does Only What It Must Do

Every function must have a single responsibility. If you need the word "and" to describe what it does, it is doing too much. Code should be like WireGuard — minimal, correct, and exceptionally well-executed.

### Fast Fail and Hard Fail

Errors must be detected at the earliest possible moment and the program must crash immediately with a clear message. Programs that silently produce wrong results are infinitely worse than programs that crash with clear errors.

### Error Messages Must Be Useful

An error message exists to tell the operator what went wrong so they can fix it. Every error message must answer what happened, where it happened, and what the actual vs expected value was.

### Linting Is Mandatory

If a linter exists for the language, it must be installed and all code must pass it cleanly. Suppressing a lint error requires the same effort as fixing the underlying issue, so you must always choose to fix the issue.

### Plan Before You Code

Every non-trivial task must begin with a written plan. The plan must be atomic, specific, and verifiable. Each step must be small enough that its correctness is obvious.

## Usage

### For Agents

When writing code in any language:

1. Read the core protocol (`AGENTS/AGENTS.md`) to understand the universal principles.
2. Read the relevant satellite file for your language or topic.
3. Follow the required linters and tools listed in the satellite file.
4. Apply the best practices and avoid the common mistakes documented.
5. Use the operational workflow (Plan, Confirm, Execute, Report) for all non-trivial tasks.

### For Operators

When reviewing agent code:

1. Verify that the agent has read and followed the relevant satellite file.
2. Check that all required linters pass cleanly with no suppressions.
3. Ensure that error messages are useful and that the code fails fast and hard.
4. Confirm that the agent followed the PLAN.md workflow if the task was non-trivial.
5. Use the "Message to a Reviewing Agent" template when delegating review to another agent.

### For Project Integration

To integrate the AGENTS protocol into a project:

1. Clone this repository or copy the relevant satellite files into your project documentation.
2. Configure CI/CD to run the required linters for each language used.
3. Train agents and developers on the protocol before they begin writing code.
4. Use the consolidated file (`agents.md`) as a single reference document if preferred.

## Repository Contents

- `AGENTS/AGENTS.md` — Core protocol with universal principles and operational workflow
- `AGENTS/*.AGENTS.md` — Language-specific and topic-specific satellite files
- `agents.md` — Consolidated single-file version of all satellite files
- `README.md` — This file

## License

This protocol is provided as-is for use in AI agent coding and dev education.

## Contributing

This is a reference protocol. Changes should be made with careful consideration of their impact on agent behavior and code quality. Suggestions for improvements should be grounded in real-world experience with agent-generated code.
