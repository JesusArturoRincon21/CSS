# Catálogo de Productos – Simulador de Entrenamiento

**Programa:** Análisis y desarrollo de software · **Ficha:** 3381732
**Subactividad 1:** Estructurar la jerarquía de estilos (selectores, herencia, cascada y especificidad)

## Contenido del proyecto

- `index.html`: maquetado semántico (`header`, `nav`, `main`, `aside`, `section`, `article`, `footer`).
- `style.css`: herencia desde `body`, selectores combinados y sistema plano de especificidad.

## Cálculo de puntos de especificidad

| Tipo de selector | Puntos |
|------------------|--------|
| Etiqueta (`a`, `p`, `li`) | 1 |
| Clase (`.btn`) | 10 |
| ID (`#btn-destacado`) | 100 |

### Ejemplos usados en el proyecto

| Selector | Cálculo | Total |
|----------|---------|-------|
| `header nav ul li a` | 1+1+1+1+1 | 5 |
| `aside ul li a` | 1+1+1+1 | 4 |
| `footer ul li a` | 1+1+1+1 | 4 |
| `.btn` | 10 | 10 |
| `.comprar` | 10 | 10 |
| `.btn.comprar.destacado` | 10+10+10 | 30 |
| `#btn-destacado` (eliminado) | 100 | 100 |

## Conclusiones

1. **Herencia:** al declarar `font-family` y `color` en `body`, los títulos, párrafos y listas los adoptan sin reglas individuales.
2. **Selectores combinados:** permiten pintar los enlaces según su zona (menú principal, filtros o pie) sin afectar a los demás.
3. **Cascada vs. especificidad:** con reglas de igual peso (`.btn` y `.comprar`) gana la última escrita. Pero un ID (100 pts) vence a cualquier clase aunque esté antes en el código.
4. **Refactorización:** se eliminaron las reglas con `#id` y se reemplazaron por un sistema plano de etiquetas y clases (`.btn.comprar.destacado`), resolviendo la colisión sin usar `!important`.
