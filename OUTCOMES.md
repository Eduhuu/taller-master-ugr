# Exercise Outcomes Submission Template

**Student/Group Name**: Eduardo Suarez, Daniel Lozano DS-01
**Level Completed**: master-of-the-universe  
**Date**: 05/01/2026

---

## 📋 Exercise Summary

### Exercise: Branch Protection Rules and Security Best Practices (GPG Signing & Sensitive Data Management)
**Status**: ✅ Completed

**What we did**:

**Part 1 - Configuración de Branch Protection Rules**: Configuramos reglas de protección para la rama `main` en GitHub, incluyendo la habilitación de pull requests obligatorios, aprobaciones requeridas, revisión de code owners, verificación de status checks, y la exigencia de commits firmados.

**Part 2 - Prueba del Flujo de Trabajo Protegido**: Intentamos hacer push directo a `main` para verificar que las protecciones funcionaban correctamente. Aunque inicialmente pudimos hacer bypass debido a permisos de administrador, documentamos este comportamiento y luego seguimos el flujo correcto creando una rama feature (`feature/protected-workflow`) y preparando un Pull Request siguiendo las mejores prácticas.

**Part 3 - Configuración de GPG para Commits Verificados**: Generamos y configuramos una clave GPG RSA de 4096 bits para firmar commits. Exportamos la clave pública y la agregamos a nuestras cuentas de GitHub. Configuramos Git para usar automáticamente esta clave firmando todos los commits (`commit.gpgsign = true`). Realizamos múltiples commits firmados que ahora muestran el badge "Verified" en GitHub, demostrando la autenticidad de nuestras contribuciones.


**Commands Used**:

**Part 1 - Branch Protection Rules (configuración en GitHub UI)**:
- Configuración realizada a través de la interfaz web de GitHub en Settings → Branches

**Part 2 - Testing Protected Branch Workflow**:
```bash

git checkout master-of-the-universe
git checkout -b feature/protected-workflow
echo "Proper workflow following branch protection" > workflow.txt
git add workflow.txt
git commit -S -m "feat: Add workflow documentation"
git push origin feature/protected-workflow
```

**Part 3 - GPG Commit Signing Setup**:
```bash
# Generar clave GPG RSA 4096 bits
gpg --full-generate-key

# Listar claves GPG secretas
gpg --list-secret-keys --keyid-format=long

# Exportar clave pública para GitHub
gpg --armor --export E99D82DC4689254C

# Configurar Git para usar la clave GPG
git config --global user.signingkey E99D82DC4689254C
git config --global commit.gpgsign true

# Verificar configuración
git config --global --get user.signingkey
git config --global --get commit.gpgsign

# Hacer commits firmados
git commit -S -m "feat: Add signed commit example"

# Verificar firmas en commits
git log --show-signature -5
```

**Part 4 - Sensitive Data Management**:
```bash
# Revisar .gitignore
cat .gitignore

# Buscar patrones sensibles en el repositorio
git log --all --source --full-history -- . | grep -i -E "(password|secret|key|token|api)" || echo "No sensitive patterns found"

# Verificar archivos rastreados
git ls-files
```

**Part 5 - Security Audit**:
```bash
# Verificar commits firmados en el historial
git log --show-signature --all

# Ver configuración de seguridad
git config --global --list | grep -E "(user\.|signing)"

# Verificar ramas y su estado
git branch -a
git log --oneline --graph --all -10
```

**Results/Output**:
- Las reglas fueron configuradas exitosamente en GitHub a través de la interfaz web
- Se observó el comportamiento de bypass cuando se intentó push directo a `main` debido a permisos de administrador
- El commit `8733694` ("Attempting direct push") muestra el intento de push directo que fue bypassed

**Part 3 - GPG Key Configuration**:
```
$ gpg --list-secret-keys --keyid-format=long
/home/eduardo/.gnupg/pubring.kbx
--------------------------------
sec   rsa4096/E99D82DC4689254C 2026-01-05 [SC]
      DF4D8833D6FFCE14B33C9C10E99D82DC4689254C
uid                 [ultimate] Eduardo Suarez (Hola soy Edu) <eduardosuarez.c97@gmail.com>
ssb   rsa4096/F460D33D4E356D50 2026-01-05 [E]

$ git config --global --list | grep -E "(user\.|signing)"
user.email=eduardosuarez.c97@gmail.com
user.name=Eduhuu
user.signingkey=E99D82DC4689254C
```

**Part 3 - Signed Commits Verification**:
```bash
$ git log --show-signature -3
commit 3a32f82ccbfad43f6687d43549f60525260ccf05
gpg: Signature made Mon Jan  5 19:39:34 2026 UTC
gpg:                using RSA key DF4D8833D6FFCE14B33C9C10E99D82DC4689254C
gpg: Good signature from "Eduardo Suarez (Hola soy Edu) <eduardosuarez.c97@gmail.com>" [ultimate]
Author: Eduhuu <eduardosuarez.c97@gmail.com>
Date:   Mon Jan 5 19:39:34 2026 +0000

    asdasd
```

---

## 🎯 Key Learnings

**Main concepts we learned**:
1. **Branch Protection Rules**: Entendimos cómo las reglas de protección de ramas previenen cambios directos a ramas críticas como `main`, forzando el uso de Pull Requests y aprobaciones.

2. **GPG Commit Signing**: Descubrimos la importancia de firmar commits con GPG para verificar la autenticidad de las contribuciones. Aprendimos cómo generar una clave GPG RSA de 4096 bits, exportarla a GitHub, y configurar Git para firmar automáticamente todos los commits.

3. **CODEOWNERS File**: Comprendimos cómo funciona el archivo CODEOWNERS y su integración con las reglas de protección de ramas. Aprendimos que este archivo define quién debe revisar automáticamente los cambios en ciertos archivos o rutas,


**Skills we improved**:
- **Configuración de GPG**: Aprendimos a generar, exportar y configurar claves GPG para firmar commits, algo completamente nuevo para nosotros
- **Configuración de Git para seguridad**: Mejoramos en configurar `user.signingkey` y `commit.gpgsign` para automatizar el proceso de firma de commits
- **Verificación de firmas**: Aprendimos a usar `git log --show-signature` para verificar que los commits están correctamente firmados
- **Navegación de ramas protegidas**: Mejoramos en crear feature branches y entender el flujo de trabajo cuando las ramas están protegidas
- **Uso de GitHub UI para seguridad**: Aprendimos a configurar branch protection rules a través de la interfaz web de GitHub
- **Análisis de seguridad**: Desarrollamos habilidades básicas para identificar y gestionar datos sensibles en repositorios Git

---

## 🚧 Challenges Faced

### Challenge 1: [Brief title]
**Problem**: [Describe the challenge you encountered]

**Solution**: [Explain how you resolved it or what you learned from it]

**Commands/Approach**:
```bash
# Commands or approach used to solve the problem
```

---

### Challenge 2: [Brief title]
**Problem**: [Describe the challenge]

**Solution**: [Your resolution]

---

## 💭 Personal Reflection

**What surprised us**:
[What unexpected things did you discover about Git?]

**What we found most difficult**:
[Which concepts or exercises were most challenging?]

**What we found most useful**:
[Which skills do you think will be most valuable in real projects?]

**How we would apply this in real projects**:
[Describe how you might use these Git skills in professional work]

---

## 📊 Self-Assessment

Rate your confidence level for each topic (1-5, where 5 is very confident):

| Topic | Confidence (1-5) | Notes |
|-------|------------------|-------|
| Basic Git commands | [ ] | |
| Branching & merging | [ ] | |
| Remote operations | [ ] | |
| Conflict resolution | [ ] | |
| History rewriting | [ ] | |
| Git hooks | [ ] | |
| Security practices | [ ] | |

---

## 🔗 Evidence/Artifacts

**Links to branches/commits**:
- Link to your outcome branch: `https://github.com/Eduhuu/taller-master-ugr/tree/group-DS01-outcomes/master-of-the-universe`
- Key commits demonstrating your work:
  - `8733694` - "Attempting direct push": Commit que documenta el intento de push directo a `main`, demostrando el comportamiento de bypass con permisos de administrador
  - `3a32f82` - "asdasd": Commit firmado con GPG que muestra verificación exitosa ("Good signature"), demostrando la configuración correcta de GPG signing
  - `1cfeebf` - "Merge branch 'main' into feature/protected-workflow": Merge de la rama feature protegida, demostrando el flujo correcto de trabajo con ramas protegidas

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
