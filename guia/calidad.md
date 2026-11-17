# Control de calidad

Objetivo: que nunca salga un video con textos encimados, cosas cortadas, voz cortada o animaciones pobres.

| Control | Qué detecta |
|---|---|
| QA de composición | Renderiza un cuadro cada N segundos y mide el DOM: **PISA** (dos textos se superponen > 18 %), **CORTE** (texto fuera del cuadro), **CHICO** (letra ilegible en celular). Si hay PISA o CORTE, el render se cancela. |
| Zonas seguras | Zonas fijas para 16:9 y 9:16; el texto se achica solo para entrar; nunca dos elementos a la vez en una zona. |
| QA del MP4 | Negro al inicio, tramos negros, imagen congelada, silencios, volumen y picos, duración válida para Reels. |
| Ritmo | Cortes por cada 10 s, duración media de plano y cantidad de movimiento, comparados con videos virales de referencia. |
| Retención | Panel con promedio visto, % que sigue a los 3 s y % que llega al final, por video y por red. |

## Lo que aprendimos de los datos
- El gancho casi nunca es el problema: > 90 % de la audiencia sigue a los 3 segundos.
- Lo que separa un video de 50.000 vistas de uno de 300 es **cuánto aguantan en el medio**: giros visuales cada pocos
  segundos y remates absurdos pero con datos reales.
- Planos ≤ 3,5 s en Shorts.
