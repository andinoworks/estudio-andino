# ¿Local o en GitHub/la nube?

| | En la PC (actual) | GitHub Actions gratis | Nube con GPU |
|---|---|---|---|
| GPU para voz clonada y Blender | ✅ | ❌ (solo CPU) | ✅ |
| Render de un largo de 10 min | 1–2 h | 6–10 h+ (límite 6 h por trabajo) | < 1 h |
| Costo | luz | gratis con límites | pago por hora |
| Sesiones de redes (TikTok por navegador) | ✅ estables | ❌ se bloquean por IP de datacenter | ⚠️ |
| Claves | quedan en la máquina | secretos del repo | en el servidor |
| Depende de que la PC esté prendida | sí | no | no |

**Decisión:** la producción sigue local. GitHub sirve para:
1. **Respaldo privado** del código (repositorio privado, sin claves) — evita perder todo si falla el disco.
2. **Esta ficha pública** para mostrar el sistema sin regalarlo.
3. Tareas livianas en el futuro (por ejemplo, recolectar estadísticas o publicar algo ya renderizado) si hiciera falta que
   funcionen con la PC apagada.
