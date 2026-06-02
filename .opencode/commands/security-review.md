---
description: Run a security-focused review for the active phase
agent: build
---

Review the repository using `docs/security-model.md` and the current phase file.

Focus on:

- filesystem boundaries
- shell execution
- permission defaults
- secret handling
- logging and trace payload redaction
- unsafe dependency choices

Do not modify files unless the user asks for fixes after the review.
