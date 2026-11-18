# Frontend Specs — Análisis de Desajustes API

**Propósito:** Documentar, rastrear y resolver inconsistencias entre las especificaciones del PM y la implementación real de la API.

**Estado:** 📋 Análisis completado | 🔧 Remediación propuesta | ⏳ Implementación pendiente

---

## 📚 Documentos en esta Carpeta

### 1. **RESUMEN_EJECUTIVO.md** ⭐ _COMIENZA AQUÍ_
   - **Para:** Decisores y product managers
   - **Duración:** 5 minutos
   - **Contenido:** 
     - Vista de 60 segundos de los desajustes
     - Matriz de desajustes por componente
     - Plan de acción paso a paso
     - Matriz de decisión

### 2. **DESAJUSTES_PM_VS_API.md** 🔍 _ANÁLISIS TÉCNICO_
   - **Para:** Desarrolladores backend y PM
   - **Duración:** 15 minutos
   - **Contenido:**
     - Análisis detallado de cada desajuste
     - Código afectado con línea exacta
     - Impacto en clientes
     - 2 opciones de remediación por desajuste

### 3. **PLAN_REMEDIACION.md** 🛠️ _INSTRUCCIONES_
   - **Para:** Desarrolladores backend
   - **Duración:** 20 minutos
   - **Contenido:**
     - Tabla de cambios propuestos
     - Checklist paso a paso
     - Scripts de verificación manual
     - Commands para tests automatizados
     - Timeline propuesto

### 4. **API_QUIRKS.md** ⚠️ _GUÍA DE WORKAROUNDS_
   - **Para:** Equipo frontend
   - **Duración:** 10 minutos
   - **Contenido:**
     - Comportamientos inesperados actuales
     - Workarounds para usar ahora
     - Matriz de qué funciona y qué no
     - Ejemplos de código JavaScript/TypeScript

### 5. **README.md** (este archivo)
   - Índice y guía de navegación

---

## 🎯 Por Rol de Usuario

### 👨‍💼 Product Manager / Líder de Equipo
1. Lee: **RESUMEN_EJECUTIVO.md** (5 min)
2. Decide: ¿Opción A o B? (2 min)
3. Autoriza: Plan de remediación

### 👨‍💻 Backend Developer
1. Lee: **DESAJUSTES_PM_VS_API.md** (10 min) → entiende qué está roto
2. Consulta: **PLAN_REMEDIACION.md** (5 min) → cómo arreglarlo
3. Implementa: Cambios de código + tests
4. Verifica: Checklist en PLAN_REMEDIACION.md

### 🎨 Frontend Developer
1. Lee: **API_QUIRKS.md** (10 min) → qué comportamientos esperar
2. Usa: Workarounds mientras se reparan desajustes
3. Regresa a: Revisar cuando backend notifique cambios

---

## 📊 Resumen Rápido de Desajustes

| # | Tipo | Severidad | Componente | Tiempo Reparación |
|---|------|-----------|-----------|-------------------|
| 1 | 📋 Doc | 🟡 Menor | MAPEO_ENDPOINTS.md | 2 min |
| 2 | 🐛 Bug | 🔴 Crítico | backend/routes.py:180 | 2 min + test |
| 3 | 📋 Doc | 🔴 Crítico | MAPEO_ENDPOINTS.md | 10 min |
| 4 | 📋 Doc | 🔴 Crítico | MAPEO_ENDPOINTS.md | ↑ incluido |
| 5 | 📋 Doc | 🟡 Menor | MAPEO_ENDPOINTS.md | 5 min |

**Total:** ~25-30 minutos

---

## 🚀 Próximos Pasos

### Ahora (Inmediato)
- [ ] PM/líder: Lee RESUMEN_EJECUTIVO.md
- [ ] Decide: ¿Comenzar reparación ahora o después?
- [ ] Backend dev: Revisa PLAN_REMEDIACION.md

### Esta Semana
- [ ] Implementar cambios de código (si se aprueba)
- [ ] Actualizar especificaciones
- [ ] Ejecutar tests automatizados
- [ ] Comunicar cambios al equipo

### Futuro
- [ ] Mejorar especificación inicial para evitar esto
- [ ] Implementar CI/CD que valide especificación vs código
- [ ] Crear tests de contrato (contract testing)

---

## ❓ Preguntas Frecuentes

**P: ¿Cuál es el impacto en usuarios?**  
R: Bajo por ahora. El desajuste crítico (`category` no filtra) no es usado por frontend todavía. Ver API_QUIRKS.md para workarounds.

**P: ¿Qué endpoints están quebrados?**  
R: Solo `/api/metrics/summary?category=...`. Todos los demás funcionan correctamente.

**P: ¿Puedo comenzar frontend development ahora?**  
R: Sí. Lee API_QUIRKS.md y evita parámetros problemáticos. Se actualizará en 1 semana.

**P: ¿Quién es responsable de cada documento?**  
R: PM creó especificaciones, Backend implementó, Análisis consolidado aquí.

**P: ¿Dónde reporto un nuevo desajuste?**  
R: Crea un issue en GitHub y etiqueta con `api-spec-mismatch`.

---

## 📋 Checklist de Verificación

Antes de considerar este análisis completo:

- [x] Se identificaron todos los desajustes (5 total)
- [x] Se documentó cada desajuste con código exacto
- [x] Se propusieron 2+ opciones de remediación por desajuste
- [x] Se estimó tiempo y esfuerzo
- [x] Se identificaron dependencias
- [x] Se crearon workarounds para frontend
- [x] Se preparó comunicación para todos los roles

---

## 🔗 Referencias Externas

- **Especificación original:** `../../MAPEO_ENDPOINTS.md`
- **Implementación:** `../../backend/app/routes.py`
- **Conexiones proyecto:** `../../MAPA_CONEXIONES.md`
- **Tests backend:** `../../backend/tests/test_routes.py`

---

## 📝 Notas de Archivo

**Documento creado:** 2026-11-18  
**Autor:** Análisis de desajustes (automatizado)  
**Versión:** 1.0  
**Próxima revisión:** Después de implementar remediación  

---

## ✉️ Contacto

Para preguntas o aclaraciones sobre estos documentos:
- Backend Team: Implementación técnica
- PM: Decisiones sobre prioridades
- Frontend Team: Validación de workarounds

