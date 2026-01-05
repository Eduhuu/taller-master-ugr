# Exercise Outcomes Submission Template

**Student/Group Name**: [Your name or group identifier, e.g., "Group A"]  
**Level Completed**: [newbie / intermediate / master / master-of-the-universe]  
**Date**: [Submission date]

---

## 📋 Exercise Summary

### Exercise: [Exercise Title]
**Status**: ✅ Completed / ⏳ In Progress / ❌ Not Completed

**What I did**:

**Part 1 - Amending Commits**: Creé el archivo `config.txt` inicialmente con la versión, y luego utilicé `git commit --amend` para agregar la configuración de entorno sin crear un commit adicional.

**Part 2 - Interactive Rebase**: Implementé un rebase interactivo para limpiar el historial de commits. Creé múltiples commits (feature A, feature B, y un fix de typo), y luego usé `git rebase -i HEAD~3` para combinar el commit de corrección con el commit original de feature A usando la operación `fixup`, resultando en un historial más limpio.

**Part 3 - Rebasing a Branch**: Creé una rama (`feature/awesome-feature`) con commits propios, luego simulé avances en la rama master y rebaseé mi rama feature sobre master usando `git rebase master`, obteniendo un historial lineal sin commits de merge innecesarios.


**Commands Used**:
```bash
# Part 1 - Amending Commits
git add config.txt
git commit -m "Add configuration file"
git add config.txt
git commit --amend -m "Add complete configuration file"
git log --oneline -n 3

# Part 2 - Interactive Rebase
git add featureA.txt
git commit -m "Add feature A"
git add featureB.txt
git commit -m "Add feature B"
git add featureA.txt
git commit -m "Fix typo"
git rebase -i HEAD~3
# En el editor interactivo: cambié 'pick' a 'fixup' para el commit de typo
git log --oneline -n 5

# Part 3 - Rebasing a Branch
git checkout -b feature/awesome-feature
git add awesome.txt
git commit -m "Add awesome feature"
git checkout master
git add master-update.txt
git commit -m "Update on master branch"
git checkout feature/awesome-feature
git rebase master
git log --graph --oneline --all -n 10
```

**Results/Output**:

**Part 1 - After Amending Commits**:
```bash
$ git log --oneline -n 3
779991e Add complete configuration file
b5d8eb6 refactor: consolidate master exercises into single comprehensive exercise on history rewriting
960a0a6 docs: Add submission instructions to master level
```
*Nota: Solo aparece un commit para config.txt, confirmando que `--amend` consolidó ambos cambios sin crear un commit adicional.*

**Part 2 - After Interactive Rebase**:
```bash
$ git log --oneline -n 5
7b28da3 Add feature A
779991e Add complete configuration file
b5d8eb6 refactor: consolidate master exercises into single comprehensive exercise on history rewriting
960a0a6 docs: Add submission instructions to master level
f0055a0 Update README for master level exercises
```
*Nota: El commit "Fix typo" fue combinado con "Add feature A" usando `fixup`, resultando en un historial más limpio. El commit de feature B también fue procesado durante el rebase interactivo.*

**Part 3 - After Rebasing Feature Branch**:
```bash
$ git log --graph --oneline --all -n 10
* dcb2fcd Add awesome feature
* cc8331b Update on master branch
* 7b28da3 Add feature A
* 779991e Add complete configuration file
* b5d8eb6 refactor: consolidate master exercises into single comprehensive exercise on history rewriting
* 960a0a6 docs: Add submission instructions to master level
* f0055a0 Update README for master level exercises
| * 1c21a8b feat: Add comprehensive exercise outcomes template for Git practice
| *   efc7ec2 Merge branch 'feature/footer' into intermediate
| |\  
| | * 3019c44 Add footer to page

```

**Screenshots** (if applicable):
- rebase.png: Muestra el rebase luego de haber emulado que master avanzaba y que se tenia que combinar con la rama de trabajo, donde no aparece el commit del merge
- interactive_rebase.png: muestra el resultado del rebase donde se hizo squash

---

## 🎯 Key Learnings

**Main concepts I learned**:
1. **Amending Commits**: Cómo usar `git commit --amend` para modificar el último commit sin crear uno nuevo, manteniendo un historial más limpio y profesional. 

2. **Interactive Rebase**: Cómo usar `git rebase -i` para reescribir el historial de commits mediante operaciones como `pick` y `fixup`, permitiendo crear historiales profesionales y organizados antes de hacer merge a la rama principal.

3. **Rebase vs Merge**: La diferencia fundamental entre rebase y merge: rebase crea un historial lineal reaplicando commits sobre una nueva base, mientras que merge crea un commit de merge que preserva el historial completo de ambas ramas.

4. **History Rewriting Risks**: Cómo las operaciones de rebase y amend cambian los SHAs de los commits, reescribiendo efectivamente el historial. Comprendí por qué es peligroso reescribir historial en ramas públicas o compartidas: puede causar conflictos de sincronización, pérdida de trabajo, ruptura de CI/CD, y problemas de trazabilidad.

5. **Safe History Rewriting Practices**: Cuándo es seguro reescribir historial (solo en ramas privadas/locales).

**Skills I improved**:
- Uso de rebase interactivo para limpiar y organizar el historial de commits antes de hacer merge.
- Toma de decisiones informadas sobre cuándo usar rebase vs merge según el contexto del proyecto.
- Uso efectivo de `git commit --amend` para corregir errores en el último commit sin contaminar el historial con commits de "fix typo" o similares

---

## 🚧 Challenges Faced

### Challenge 1: Familiarización con comandos nuevos
**Problem**: No se conocían previamente algunos comandos avanzados de Git utilizados en esta práctica, específicamente `git commit --amend` y `git rebase -i` (rebase interactivo). Estos comandos no formaban parte del conocimiento previo sobre Git.

**Solution**: Se investigó y consultó la documentación oficial de Git y recursos adicionales para comprender cómo funcionan estos comandos, sus parámetros, y las operaciones disponibles en el rebase interactivo (como `pick`, `fixup`, `squash`, `reword`). Una vez entendidos los conceptos, la ejecución de los ejercicios fue directa.

**Commands/Approach**:
```bash
# Consulta de documentación y experimentación con los comandos
git commit --amend --help
git rebase -i --help
# Práctica con ejemplos simples antes de aplicarlos al ejercicio completo
```

---

## 💭 Personal Reflection

**What surprised me**:
No esperaba que se buscara y se predicara tanto mantener un git log tan pulcro y organizado. Me sorprendió descubrir que mantener historiales de commits limpios es una práctica estándar en proyectos profesionales.

**What I found most difficult**:
No encontré dificultades significativas. Una vez comprendidos los conceptos de rebase interactivo y amend, la ejecución fue directa.

**What I found most useful**:
La operación de squash mediante rebase interactivo para comprimir múltiples commits en uno solo. Esto me permite trabajar libremente haciendo commits frecuentes sin preocuparme por la cantidad, sabiendo que puedo consolidarlos después en commits más significativos.

**How I would apply this in real projects**:
Utilizar squash para combinar commits pequeños en uno solo más descriptivo, preservando un git log más legible y profesional para la organización y facilitando la revisión de código y el seguimiento de cambios.

---

## 📊 Self-Assessment

Rate your confidence level for each topic (1-5, where 5 is very confident):

| Topic | Confidence (1-5) | Notes |
|-------|------------------|-------|
| Basic Git commands | [ ] | 5 |
| Branching & merging | [ ] |4|
| Remote operations | [ ] |3|
| Conflict resolution | [ ] | 4|
| History rewriting | [ ] | 2|
| Git hooks | [ ] | 1|
| Security practices | [ ] | 1|

---

## 🔗 Evidence/Artifacts

**Links to branches/commits**:
- Link to your outcome branch: `https://github.com/miguel-oltra/taller-master-ugr/tree/group-X-outcomes/[level]`
- Key commits demonstrating your work:
  - 7b28da3754b822ef39c232b649ca44d7833d32ff: commit donde se hizo el rebase interactivo
  - 779991e41fa95051fb0981f9df5b52219084bc05: commit donde se hizo el commit con ament

**Additional files created** (if any):
- File 1: [Description]
- File 2: [Description]

---

## ✅ Completion Checklist

Before submitting, ensure you have:
- [ ] Completed the exercise for your chosen level (including all parts)
- [ ] Documented all commands used with their outputs
- [ ] Described challenges and how you resolved them
- [ ] Provided a thoughtful reflection on your learning
- [ ] Self-assessed your confidence in each topic
- [ ] Pushed your outcome branch to the remote repository
- [ ] Created a Pull Request (if required by your instructor)

---

## 📝 Additional Comments

[Any additional thoughts, questions, or feedback about the exercises]

---

**Submission Date**: [01/05/2026]  
**Ready for Review**: ✅ Yes
