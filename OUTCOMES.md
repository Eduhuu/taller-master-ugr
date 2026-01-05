# Exercise Outcomes Submission Template

**Student/Group Name**: Eduardo Suarez, Daniel Lozano, grupo DS-01
**Level Completed**: intermediate
**Date**: 04/01/2026

---

## 📋 Exercise Summary

### Exercise: [Exercise Title]
**Status**: ✅ Completed

**What I did**:
Se practicaron los conceptos de merge, conflictos y como resolverlos. Tambien se trabajaron con etiquetas y como poder hacer versiones utilizandolas

**Commands Used**:
```bash
# Parte 1 - Merging & Conflicts
# Crear ramas desde intermediate
git checkout intermediate
git checkout -b feature/header
git checkout intermediate
git checkout -b feature/footer

# Trabajar en feature/header
git checkout feature/header
git add page.html
git commit -m "Add header to page"

# Trabajar en feature/footer
git checkout feature/footer
git add page.html
git commit -m "Add footer to page"

# Merge de ambas ramas en intermediate
git checkout intermediate
git merge feature/header
git merge feature/footer  # Esto crea un conflicto

# Resolver el conflicto
git add page.html
git commit -m "Merge footer with resolved conflicts"

# Ver el historial con gráfico
git log

# Parte 2 - Tags
# Crear tag annotated
git tag -a v1.0 -m "First stable version with merged features"

# Listar todos los tags
git tag

# Ver información del tag annotated
git show v1.0

# Subir el tag al remoto
git push origin v1.0

# Crear tag lightweight
git tag v1.0-test

# Comparar ambos tipos de tags
git show v1.0
git show v1.0-test
```

**Results/Output**:
```
commit efc7ec25147b88b136a1359ba8a1adce2f56def4 (HEAD -> intermediate)
Merge: 0fc2cec 3019c44
Author: Eduhuu <eduardosuarez.c97@gmail.com>
Date:   Sun Jan 4 20:21:49 2026 +0000

    Merge branch 'feature/footer' into intermediate

commit 3019c4419accd84325b383a5562c2da93490ec77 (feature/footer)
Author: Eduhuu <eduardosuarez.c97@gmail.com>
Date:   Sun Jan 4 20:20:39 2026 +0000

    Add footer to page

commit 0fc2cec7e0ca034acd7430c484f107a6ed87f1b6 (feature/header)
Author: Eduhuu <eduardosuarez.c97@gmail.com>
Date:   Sun Jan 4 20:19:54 2026 +0000

    Add header to page


Aqui el grafo utilizando: `git log --graph --oneline --all`


eduardo@Eduardo:~/Master/DS/taller-master-ugr (group-DS01-outcomes/intermediate)$ git log --graph --oneline --all
*   efc7ec2 (HEAD -> group-DS01-outcomes/intermediate, tag: v1.0-test, tag: v1.0, intermediate) Merge branch 'feature/footer' into intermediate
|\  
| * 3019c44 (feature/footer) Add footer to page
* | 0fc2cec (feature/header) Add header to page
|/  
```

**Screenshots** (if applicable):
- [Screenshot 1: Description]
- [Screenshot 2: Description]

---

## 🎯 Key Learnings

**Main concepts I learned**:
1. **Cómo funciona el merge de ramas y cuándo se producen conflictos**: Aprendí que cuando dos ramas modifican las mismas líneas de un archivo, Git no puede fusionar automáticamente y requiere intervención manual para resolver el conflicto.

2. **Comprensión de los marcadores de conflicto**: Entendí cómo leer e interpretar los marcadores `<<<<<<<`, `=======`, y `>>>>>>>` que Git inserta en los archivos cuando detecta conflictos, identificando qué cambios vienen de cada rama.

3. **Diferencia entre tags annotated y lightweight**: Comprendí que los tags annotated (`-a`) almacenan información completa (autor, fecha, mensaje) y son objetos Git completos, mientras que los tags lightweight son simplemente punteros a commits específicos.

4. **Cuándo usar tags vs. branches**: Aprendí que los tags se usan para marcar puntos importantes en el historial (como releases), mientras que las ramas son para desarrollo activo que puede cambiar.

**Skills I improved**:
- **Resolución de conflictos de merge**: Mejoré mi habilidad para identificar conflictos, entender qué cambios mantener de cada rama, y resolverlos manualmente editando los archivos.

- **Lectura e interpretación de Git logs**: Desarrollé la capacidad de leer y entender el historial de commits, especialmente usando `git log --graph` para visualizar la estructura de ramas y merges.

- **Gestión de tags para versionado**: Adquirí experiencia en crear, listar, visualizar y subir tags al repositorio remoto, entendiendo su uso práctico para el control de versiones.

- **Trabajo colaborativo con ramas**: Mejoré mi comprensión del flujo de trabajo con múltiples ramas de características y cómo integrarlas de manera segura.

---

## 🚧 Challenges Faced

Durante esta práctica no enfrentamos problemas significativos. El ejercicio se desarrolló de manera fluida siguiendo las instrucciones paso a paso:

- **Merge de ramas**: El proceso de crear las ramas `feature/header` y `feature/footer` y hacer merge fue directo y sin complicaciones.

- **Resolución de conflictos**: Los marcadores de conflicto (`<<<<<<<`, `=======`, `>>>>>>>`) fueron fáciles de identificar y entender. La resolución consistió simplemente en mantener ambas secciones (header y footer) en el archivo `page.html`.

- **Tags**: La creación de tags annotated y lightweight fue sencilla siguiendo la documentación. La diferencia entre ambos tipos quedó clara al comparar sus outputs con `git show`.

El ejercicio nos permitió practicar los conceptos de manera controlada y sin obstáculos, lo cual facilitó el aprendizaje de los fundamentos de merge, conflictos y tags en Git.

---

## 💭 Personal Reflection
Nada mas que agregar a esta sección.

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
- Link to your outcome branch: `https://github.com/Eduhuu/taller-master-ugr/tree/group-DS01-outcomes/intermediate`
- Key commits demonstrating your work:
  - Commit hash: efc7ec25147b88b136a1359ba8a1adce2f56def4. Commit donde se hizo el merge con los conflictos

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
