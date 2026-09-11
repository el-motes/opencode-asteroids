---
description: Crea un git worktree en .worktrees/<nombre>
---

Ejecuta exactamente un comando:

git worktree add .worktrees/<nombre>

<nombre> se deriva de este argumento: "$ARGUMENTS"

Reglas:
- Argumento puede tener espacios. Analízalo y genera nombre corto según su contexto: minúsculas, kebab-case, sin espacios ni acentos (ej: "fix collision bug" → fix-collision-bug).
- Solo ejecuta ese comando. No cambies de directorio, no hagas nada adicional.
