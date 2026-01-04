# Exercise Outcomes Submission Template

**Student/Group Name**: Eduardo Suarez, Daniel Lozano Grupo DS-01  
**Level Completed**: newbie
**Date**: 04/01/2026

---

## 📋 Exercise Summary

### Exercise: Newbie Level Exercise
**Status**: ✅ Completed

**What I did**:
Se pusieron a prueba los comandos de git: add, checkout, push, pull y log

**Commands Used**:

### Parte 1: Repository Setup and Basic Commands

```bash
# Configurar nombre
git config --global user.name

# Configurar email
git config --global user.email

# Verificar estado del repositorio
git status

# Añadir archivo al staging area
git add hello.txt

# Crear commit con mensaje descriptivo
git commit -m "Add hello.txt with my name"

# Ver historial de commits
git log

# Ver todas las ramas (locales y remotas)
git branch -a
```

### Parte 2: Branches and Remote Operations

```bash
# Crear nueva rama y cambiar a ella (comando combinado)
git checkout -b feature/my-info

# Alternativa: crear rama y cambiar por separado
# git branch feature/my-info
# git checkout feature/my-info

# Ver ramas locales
git branch

# Añadir archivo y hacer commit en la nueva rama
git add my-info.txt
git commit -m "Add personal information"

# Enviar rama al repositorio remoto
git push origin feature/my-info

# Cambiar de vuelta a la rama newbie
git checkout newbie

# Obtener cambios del repositorio remoto
git pull origin newbie

# Ver historial completo con gráfico de ramas
git log --oneline --graph --all
```

**Results/Output**:
```
# Paste relevant command outputs, git log, or status messages
# Example:
$ git log --oneline -5
abc1234 feat: Add new feature
def5678 fix: Resolve merge conflict
```

**Screenshots** (if applicable):
- Screenshot 1: imagen donde se muestra el nombre y el email configurado
- Screenshot 2: imagen donde se muestra el log de git mostrando el commit de la rama de feature/my-info

---

## 🎯 Key Learnings

**Main concepts I learned**:
1. **La arquitectura de tres árboles de Git**: Entendí la diferencia entre el working directory (donde trabajo con mis archivos), el staging area (donde preparo los cambios con `git add`), y el repository (donde se guardan permanentemente con `git commit`). Esto me ayudó a comprender por qué necesito hacer `add` antes de `commit`.

2. **Creación y navegación entre ramas**: Aprendí cómo crear ramas con `git checkout -b` o separando los comandos `git branch` y `git checkout`, y cómo cambiar entre diferentes ramas. Esto es fundamental para trabajar en features separadas sin afectar el código principal.

3. **Diferencia entre repositorios locales y remotos**: Comprendí que el repositorio local está en mi máquina y puedo trabajar sin conexión, mientras que el remoto (origin) está en GitHub y permite colaborar con otros. Los comandos `push` y `pull` sincronizan cambios entre ambos.

**Skills I improved**:
- **Uso de comandos básicos de Git**: Me familiaricé con `git status` para ver el estado de mi repositorio, `git add` para preparar cambios, `git commit` para guardarlos, y `git log` para revisar el historial.

- **Operaciones con ramas**: Aprendí a crear ramas, cambiar entre ellas, y visualizar todas las ramas locales y remotas con `git branch -a` y `git log --oneline --graph --all`.

- **Operaciones remotas**: Mejoré mi comprensión de cómo enviar cambios al remoto con `git push` y obtener cambios del remoto con `git pull`, entendiendo la importancia de especificar la rama y el remoto (origin).

---

## 🚧 Challenges Faced

No se encontraron problemas significativos durante la realización de este ejercicio. Todos los comandos funcionaron correctamente y el flujo de trabajo fue fluido.

---

## 💭 Personal Reflection

**What surprised me**:
Aunque ya conocía estos comandos básicos de Git, fue interesante ver cómo la práctica estructurada me ayudó a entender mejor la arquitectura interna de Git y el flujo completo de trabajo.

**What I found most difficult**:
No encontré dificultades significativas, ya que estos son comandos que había utilizado anteriormente. Sin embargo, fue útil repasar la sintaxis exacta y las mejores prácticas.

**What I found most useful**:
Reafirmar el conocimiento sobre el flujo básico de Git (add, commit, push, pull) y la gestión de ramas. Estos son fundamentos que uso constantemente en proyectos reales.

**How I would apply this in real projects**:
Estos comandos son la base de mi flujo de trabajo diario con Git.

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
  - Commit hash: [Short description]
  - Commit hash: [Short description]

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

**Submission Date**: [Date]  
**Ready for Review**: ✅ Yes / ❌ No
