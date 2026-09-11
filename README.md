# Asteroids

Clon del clásico arcade **Asteroids** implementado en canvas HTML5 puro, sin dependencias ni bundler.

## Descripción

Nave espacial en un campo de asteroides con envolvimiento de bordes (el espacio es toroidal). Destruye asteroides para sumar puntos: los grandes se parten en medianos, los medianos en pequeños. Los asteroides destruidos pueden soltar los power-ups **Velocidad** (duplica la propulsión durante 5 segundos) o **Triple** (dispara tres balas en abanico estrecho durante 5 segundos).

## Tecnologías

- **HTML5 Canvas** — renderizado 2D
- **JavaScript (ES6+)** — lógica del juego en un solo archivo `game.js`
- Sin frameworks, sin bundler, sin dependencias

## Cómo correr

Abre `index.html` directamente en el navegador (doble clic), o usa un servidor local:

```bash
npx serve .
```

Luego visita `http://localhost:3000`.

## Controles

| Tecla     | Acción     |
| --------- | ---------- |
| `←` `→`   | Rotar nave |
| `↑`       | Propulsar  |
| `Espacio` | Disparar   |

## Puntuación

| Asteroide | Puntos |
| --------- | ------ |
| Grande    | 20     |
| Mediano   | 50     |
| Pequeño   | 100    |

## Características

- 3 vidas con invencibilidad temporal al reaparecer (parpadeo)
- Asteroides se parten en fragmentos más pequeños al ser destruidos
- Partículas de explosión al destruir asteroides
- Power-ups: 12% de probabilidad al destruir un asteroide (tercios iguales); indicador de tiempo restante en el HUD
  - **Velocidad** ('V', dorado): la nave se propulsa al doble durante 5 segundos
  - **Escudo** ('E', cian): un campo cian rodea la nave durante 5 segundos y destruye cualquier asteroide o estrella fugaz que la toque, sin recibir daño
  - **Triple** ('T', cian claro): cada disparo lanza tres balas en abanico estrecho durante 5 segundos
- **Estrella Fugaz**: asteroide dorado que cruza la pantalla a gran velocidad; aparece cada 8–15 s, otorga 500 puntos al destruirla y se desvanece sola tras 7 s
