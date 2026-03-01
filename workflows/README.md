# ⚙️ Centro de Automatización Global (CI/CD)

Este directorio centraliza los **Workflows Reutilizables** para esta EdTech. Al ser este repositorio público, se deben seguir estrictas normas de seguridad y diseño.

## 🛡️ Reglas de Seguridad (Repositorio Público)

1. **PROHIBIDO Hardcodear Secretos**: Nunca incluyas tokens, contraseñas o claves API directamente en el código YAML. Usa `secrets: inherit` o define inputs de secretos.
2. **Lógica Genérica**: Los workflows aquí deben ser "blueprints" (plantillas). No deben contener nombres de servidores específicos, IPs privadas o rutas internas críticas del negocio.
3. **Uso de `workflow_call`**: La función principal es alojar procesos que los repositorios privados de esta EdTech llaman, manteniendo la lógica centralizada.

## 🏗️ Workflows Sugeridos para Centralizar

- **Linter & Formatting**: Validar que el código siga las guías de estilo globales.
- **Security Scanners**: Ejecutar herramientas de análisis estático (SAST).
- **Compliance Checks**: Verificar que se sigan las guías de contribución de esta EdTech.
