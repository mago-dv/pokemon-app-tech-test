# pokemon-app-tech-test

# 🚀 Examen Técnico: Aplicación Pokémon con Angular  
**Tecnologías:** Angular, PokeAPI, RxJS, Angular Material.  

---

## 🎯 Objetivo  
Desarrollar una aplicación que consuma la **PokeAPI** y demuestre habilidades en:  
✔️ **Manejo de datos** (transformación,agrupamiento, ordenamiento, filtros).  
✔️ **Estructuras de código** reutilizables y mantenibles.  
✔️ **Manejo de errores** robusto (API, usuario, red).  
✔️ **Documentación** de funciones claves explicado por palabras propias.  

---

## 📋 Requisitos Técnicos  
### 1. Funcionalidades Obligatorias  
- **Listado de Pokémon:**  
  - Muestra 20 Pokémon por página.
    - Imagen  
    - **Nombre y color principal** (ej: "Pikachu - Amarillo")  
    - Tipos (ej: Eléctrico, Volador) etc...
  - **Ordenamiento** por nombre, HP, o ataque.  
  - **Paginación** (client-side o server-side).  
- **Búsqueda Avanzada:**  
  - Filtrar por tipo (ej: "Fuego") y nombre.  
- **Detalle de Pokémon:**  
  - Stats en gráfico de radar (usar [Chart.js](https://www.chartjs.org/) o similar).  
  - Mostrar cadena de evolución (ej: Charmander → Charmeleon → Charizard).  

### 2. Manejo de Datos  
- **Transformar datos de la API:**  
  - Crear interfaz `Pokemon` con campos: `id`, `name`, `stats`, `types`.  
  - Unificar datos de endpoints `/pokemon` y `/evolution-chain`.  
- **Client-side Sorting:**  
  - Ordenar Pokémon por nombre (A-Z) o stat (ej: mayor ataque primero).
  - Definir una estructura de datos que sea organizada y mantenible a largo plazo.  

### 3. Manejo de Errores  
- **Escenarios cubiertos:**  
  - API no responde → Mensaje de error genérico.  
  - Pokémon no encontrado → Mensaje amigable en la UI.  
  - Datos incompletos → ej: imagen no disponible → mostrar placeholder.  
- **Implementación:**  
  - Usar `catchError` en servicios para capturar falls HTTP.
  - Mostrar errores con MatSnackBar o componente dedicado.

## 🚀 Extras (Opcionales)  
- **API Intermedia (Node.js/Express):**
  - Crear un backend simple que: 
    - Unifique endpoints complejos (ej: /pokemon + /evolution-chain).
    - **Endpoints complejos unificados:**  
      - `GET /api/pokemon?type=fuego&sort=attack&order=desc` (filtrar por tipo + ordenar por ataque descendente).  
      - `GET /api/pokemon/evolution-chain/25` (cadena de evolución de Pikachu).
    - **Ordenamiento server-side:**  
      - Implementar lógica de sorting en el backend para datasets grandes (ej: 100+ Pokémon).  
      - Parámetros aceptados: `sort=name|hp|attack|defense`, `order=asc|desc`.
    - Cachee respuestas de la PokeAPI.
  - Tecnologías sugeridas: Express, Axios.
- Unificar endpoints complejos.  
- **Tests E2E:**
  - Usar Cypress o Playwright para probar búsqueda y navegación.
- **LocalStorage:**
  - Guardar últimos 10 Pokémon vistos.
 
## 🚀 Recomendaciones  
- **Empieza por los modelos de datos:** Define las interfaces de TypeScript primero.
- **Prueba edge cases:** ¿Qué pasa si la API retorna null en un campo crítico?.
- **Usa operadores RxJS:** switchMap, forkJoin, catchError son tus aliados.
