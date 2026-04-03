# Glossary

Plain-English definitions for core amplihack terms.

## Workflow

A Markdown file listing steps for the AI to follow. The AI *should* follow them but technically can skip steps.

**Example**: DEFAULT_WORKFLOW.md — 23 steps for building a feature from specification to code review.

## Recipe

A YAML file that the recipe runner (Rust binary) enforces step-by-step. The AI *cannot* skip steps — the binary controls execution order.

**Example**: smart-orchestrator.yaml

## Agent

A Markdown file that defines a specialized AI role with a specific responsibility (architect, builder, reviewer, etc.)

**Example**: builder.md — writes code from specifications

## Skill

A self-contained capability that activates automatically based on context.

**Example**: PDF skill activates when you mention a PDF file.

## Orchestrator

A component that classifies your request and routes it to the right workflow or agent.

**Example**: dev-orchestrator classifies "fix the login bug" as Development, then invokes DEFAULT_WORKFLOW.

## Command

A reusable CLI invocation defined in `commands/` that can be called from any workflow or agent.

**Example**: `+test` runs unit tests with coverage

## Recipe Runner

The binary (Rust) that enforces recipe execution order.

## Dev Orchestrator

The main router that classifies incoming requests and chooses which workflow or agent to invoke.