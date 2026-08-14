---
layout: single
title: "How I Designed a Structured AI-Assisted Development Workflow for a Team Side Project"
description: "Lessons from documenting and organizing AI-assisted development for BSideU, a community platform for people who want to build side projects together."
categories: [AI, Development]
tags: [AI-assisted development, AI workflow, agentic AI, team collaboration, BSideU]
search: true
permalink: /bsideu-ai-assisted-development/
---

BSideU is a team side project for people who want to find collaborators and build side projects together. The product is still in progress, but the development process has already taught me an important lesson:

> Using AI effectively is not only about asking an AI tool to write code. It is about giving the tool the right context, constraints, and review process.

For BSideU, my contribution focused on documenting our AI workflows and creating a more structured way for the team to use AI-assisted development.

## Why we needed a workflow

AI coding tools can be helpful during implementation, debugging, and code review. However, the results become inconsistent when every developer uses a different process.

Without shared guidance, common problems appear quickly:

- The same project context is explained repeatedly.
- Generated code may not follow the project architecture.
- Different parts of the application develop different conventions.
- Debugging can become a conversation without a clear starting point.
- Code review focuses on small details instead of the larger design.

Our goal was not to remove developer judgment. The goal was to make that judgment easier to apply consistently.

## My role

I worked on the documentation and structure around AI-assisted development. This included:

- Writing project and development workflow documentation
- Organizing coding guidelines and project conventions
- Describing architecture context that an AI coding agent needs before making changes
- Defining separate workflows for implementation, debugging, and review
- Exploring how tools such as Claude Code and Codex could support the team without replacing engineering decisions

The most important part was treating the workflow as a shared team asset rather than as a collection of personal prompts.

## The workflow

The process can be summarized as:

```text
Project context
      ↓
Coding guidelines and constraints
      ↓
Implementation plan
      ↓
AI-assisted development
      ↓
Testing and debugging
      ↓
Human review and refinement
```

### 1. Start with context

Before asking an AI tool to change code, the workflow provides the relevant context:

- What the feature is supposed to do
- Which part of the application owns the behavior
- Existing patterns that should be followed
- Important data and API relationships
- Constraints that should not be violated

This helps the tool work within the project instead of treating every request as an isolated coding exercise.

### 2. Make guidelines explicit

Rules that exist only in a developer's memory are difficult for both people and AI tools to follow. We documented conventions such as:

- Where new files should be created
- How components and services should be organized
- How errors should be handled
- What should be tested
- Which changes require extra review

The documentation also gives the team a shared vocabulary for discussing implementation choices.

### 3. Separate the workflows

Implementation, debugging, and code review have different goals, so they should not be treated as one large prompt.

For implementation, the focus is understanding the requirement, identifying affected files, and creating a small plan before coding.

For debugging, the focus is reproducing the problem, identifying evidence, testing a hypothesis, and verifying the fix.

For review, the focus is checking behavior, maintainability, edge cases, and whether the change fits the existing architecture.

Separating these activities makes the AI interaction more focused and makes the developer's review responsibility clearer.

## What I learned

### Context is more valuable than clever prompts

An elaborate prompt cannot compensate for missing project information. Clear architecture notes, conventions, and constraints usually produce more useful results than a longer request.

### AI needs boundaries

A good workflow makes it clear when the AI can suggest or implement a change and when a developer must make the final decision. This is especially important for changes that affect data, authentication, APIs, or shared architecture.

### Documentation improves human collaboration too

Although the workflow was designed partly for AI-assisted development, it also made collaboration between team members easier. The same documentation that helps an AI agent understand the project helps a new developer understand it as well.

### Review remains an engineering responsibility

AI can help explore solutions and reduce repetitive work, but the team still needs to verify correctness, security, maintainability, and product behavior. AI assistance is most useful when it increases the quality of the engineering process, not when it removes the process.

## What comes next

Because BSideU is still in progress, the workflow will continue to evolve with the product. The next areas I want to improve are:

- Making project context easier to discover and maintain
- Creating more reusable templates for common development tasks
- Improving the feedback loop between implementation and review
- Documenting examples of successful and unsuccessful AI-assisted changes

This project has reinforced my interest in building practical AI workflows: systems that help teams work with more clarity while keeping developers responsible for the decisions that matter.

