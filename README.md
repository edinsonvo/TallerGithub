# Taller Git-flow — Ejercicio práctico de regresión

Bienvenido/a. En este ejercicio vas a practicar el flujo completo de Git-flow: crear tu rama, entrenar un modelo de regresión, y abrir tu Pull Request — igual que lo haría un equipo real de Data Science.

**Dataset:** [California Housing](https://scikit-learn.org/stable/datasets/real_world.html#california-housing-dataset) (viene incluido en scikit-learn, no hay que descargar nada aparte).
**Problema:** predecir el precio medio de una vivienda a partir de variables como ingreso promedio de la zona, número de habitaciones, ubicación, etc.

---

## Modelos disponibles

Cada participante trabaja con **un solo modelo**. Tu profesor/a te va a asignar uno de estos (o puedes elegir si no hay asignación):

| Nombre de tu rama | Modelo |
|---|---|
| `feature/regresion-lineal` | Regresión Lineal |
| `feature/ridge` | Ridge |
| `feature/arbol-decision` | Árbol de Decisión |
| `feature/random-forest` | Random Forest |
| `feature/knn` | K-Nearest Neighbors |

---

## Pasos a seguir

### 1. Preparar el entorno

```bash
pip install -r requirements.txt
```

### 2. Ubicarte en develop y traer los últimos cambios

```bash
git checkout develop
git pull origin develop
```

### 3. Crear tu rama

Reemplaza `tu-modelo` por el que te fue asignado (ver tabla arriba, sin el prefijo `feature/`):

```bash
git checkout -b feature/tu-modelo
```

### 4. Trabajar en el notebook

Abre `notebooks/plantilla_modelo.ipynb` con Jupyter:

```bash
jupyter notebook notebooks/plantilla_modelo.ipynb
```

Dentro del notebook:
- **No modifiques** las celdas marcadas como "NO MODIFICAR" (carga de datos, split, cálculo de métricas). Todos los participantes deben partir del mismo split para que la comparación sea justa.
- Cambia `NOMBRE_MODELO` por el nombre de tu modelo (el mismo que usaste en el nombre de tu rama, sin `feature/`).
- Completa la celda de entrenamiento con tu modelo (hay ejemplos comentados para cada uno).
- Corre todas las celdas de principio a fin. La última celda guarda automáticamente tu resultado en `resultados/metricas.csv`.

### 5. Subir tu trabajo

```bash
git add .
git commit -m "Agrega modelo de regresion lineal"
git push origin feature/tu-modelo
```

(cambia el mensaje del commit según tu modelo)

### 6. Crear el Pull Request

1. Entra a GitHub → pestaña **Pull requests** → **New pull request**.
2. Base: `develop` — Compare: `feature/tu-modelo`.
3. Escribe un título claro, por ejemplo: "Agrega modelo Random Forest para predicción de precios".
4. Asigna un revisor (un compañero).
5. Cuando esté aprobado, haz **Merge**.

---

## Estructura del repositorio

```
taller-gitflow-regresion/
├── README.md
├── requirements.txt
├── notebooks/
│   └── plantilla_modelo.ipynb
└── resultados/
    └── metricas.csv
```

## Errores comunes a evitar

- Crear tu rama desde `main` en vez de `develop`.
- Olvidar el `git pull origin develop` antes de crear tu rama (trabajarías con una versión desactualizada).
- Modificar la celda del split de datos — rompe la comparación justa entre modelos.
- Mensajes de commit poco descriptivos como "cambios" o "fix".
