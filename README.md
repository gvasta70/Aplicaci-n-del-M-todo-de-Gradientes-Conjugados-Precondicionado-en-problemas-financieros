# Guía Explicativa: Requerimiento 2 (Repositorio de Código Fuente)

El requerimiento exige entregar el **enlace al repositorio de código fuente** (en GitHub o GitLab) donde reside el proyecto. A continuación se desglosa qué evaluará el docente y qué significa cada término:

---

## 1. Desglose de los Términos del Requerimiento

### A. Repositorio Público
* **¿Qué es?:** La visibilidad del repositorio en GitHub/GitLab debe estar configurada como **Public** (no Private).
* **¿Por qué?:** El docente o evaluador debe poder ingresar al enlace sin necesidad de pedirte acceso o iniciar sesión.

### B. Estructurado
* **¿Qué es?:** El código debe estar ordenado de manera limpia.
* **En tu caso:** Al ser una aplicación web de archivo único (`index.html`), la estructura debe lucir limpia en la raíz del proyecto:
  ```text
  mi-repositorio-gcp/
  ├── index.html        # Código fuente de la página web interactiva
  ├── README.md         # Documentación detallada del proyecto
  └── LICENSE           # (Opcional) Licencia MIT u otra
  ```

### C. Historial de Commits
* **¿Qué es?:** Los *commits* son los registros de cambios ("guardados") en Git.
* **¿Por qué es obligatorio?:** Demuestra que tú desarrollaste el proyecto paso a paso y no mediante un "copiar y pegar" masivo de un solo commit.
* **Recomendación:** Realizar al menos entre 4 y 8 commits descriptivos. Ejemplos de mensajes de commit:
  1. `git commit -m "feat: estructura inicial HTML y configuración de Tailwind CSS"`
  2. `git commit -m "math: implementación de algoritmos GC, GCP (Suñagua 2020) y Cholesky"`
  3. `git commit -m "ui: integración de KaTeX y tarjetas oscuras de ecuaciones"`
  4. `git commit -m "feat: módulo de escenarios financieros y visualizador de Sylvester"`
  5. `git commit -m "test: implementación de la suite de pruebas QA y tabla comparativa"`
  6. `git commit -m "docs: adición de archivo README.md con documentación completa"`

### D. Archivo `README.md` Detallado
* **¿Qué es?:** Es la portada técnica en formato Markdown que GitHub muestra automáticamente al entrar al repositorio.
* **¿Qué debe contener?:**
  1. Título y datos del estudiante (Nombre, CI, Mención, Materia, UMSA).
  2. Descripción y objetivos del proyecto.
  3. Instrucciones de instalación y ejecución local.
  4. Arquitectura del software y métodos matemáticos implementados.
  5. Licencia y referencias bibliográficas (Cita de Suñagua, 2020).

---

## 2. Pasos para Crear y Subir tu Repositorio en GitHub

1. **Crear el repositorio en GitHub:**
   * Entra a [GitHub.com](https://github.com) -> **New repository**.
   * Nombre sugerido: `desafio-metodos-numericos-gcp`.
   * Selecciona **Public**.
   * Marca la casilla *Add a README file*.

2. **Subir tu archivo `index.html`:**
   * Puedes subir el archivo directamente desde la interfaz web (*Add file -> Upload files*) o mediante la terminal con `git`:
     ```bash
     git clone https://github.com/tu-usuario/desafio-metodos-numericos-gcp.git
     cd desafio-metodos-numericos-gcp
     # Copia tu index.html a esta carpeta
     git add index.html
     git commit -m "feat: adición de la aplicación web interactiva GCP"
     git push origin main
     ```

3. **Publicar la Página Web Gratis (GitHub Pages):**
   * En tu repositorio de GitHub, ve a **Settings** -> **Pages**.
   * En *Source*, selecciona la rama `main` y guarda (*Save*).
   * ¡Listo! Obtendrás el **enlace público de la página web** (ej: `https://tu-usuario.github.io/desafio-metodos-numericos-gcp/`).

---

# Plantilla del Archivo `README.md` (Para copiar a tu repositorio)

A continuación tienes el texto exacto que debes pegar dentro del archivo `README.md` de tu repositorio GitHub:

```markdown
# Desafío Académico de Métodos Numéricos: Gradientes Conjugados Precondicionados en Finanzas

**Universidad Mayor de San Andrés (UMSA)**  
**Facultad de Ciencias Puras y Naturales — Carrera de Informática**  
**Asignatura:** Métodos Numéricos  

---

## 👨‍💻 Datos del Estudiante
* **Estudiante:** [Tu Nombre Completo Aquí]
* **C.I.:** [Tu C.I. Aquí]
* **Mención:** Inteligencia Artificial y Ciencia de Datos / Ingeniería de Sistemas / Desarrollo de Sistemas
* **Docente:** [Nombre del Docente]
* **Fecha:** Noviembre 2026

---

## 📌 Descripción del Proyecto
Esta aplicación web interactiva resuelve y analiza modelos financieros lineales $Ax = b$ de dimensiones $n \ge 4$ mediante el **Método de Gradientes Conjugados Precondicionado (GCP)**, basándose en el artículo científico de **Porfirio Suñagua S. (Revista Boliviana de Matemática UMSA, 2020)**.

El sistema permite evaluar la velocidad de convergencia, precisión numérica, residuo relativo global y número de condición $\kappa(A)$ y $\kappa(M^{-1}A)$ a través de tres escenarios financieros:
1. **Escenario Ideal:** Matriz bien condicionada, equilibrio financiero.
2. **Escenario Bajo Estrés Financiero:** Shock de mercado e incremento de volatilidad.
3. **Escenario Mal Condicionado:** Alta interdependencia entre variables ($\kappa(A) \gg 10^3$).

---

## 🛠️ Tecnologías Utilizadas
* **HTML5 & CSS3:** Estructura web responsiva con diseño oscuro de alto contraste.
* **Tailwind CSS (CDN):** Framework de estilos para la interfaz gráfica.
* **JavaScript ES6+:** Motor matemático cliente sin dependencias pesadas de servidor.
* **Chart.js:** Gráfico dinámico de convergencia en escala logarítmica ($\|r_k\|_2 / \|b\|_2$).
* **KaTeX:** Renderizado tipográfico formal de fórmulas y expresiones matemáticas en TeX.
* **FontAwesome:** Iconografía técnica.

---

## 📐 Métodos Matemáticos Implementados
1. **Método Directo de Referencia (Solución Exacta):** Descomposición de Cholesky ($A = L L^T$) para matrices simétricas y definidas positivas.
2. **Gradientes Conjugados Simples (GC):** Algoritmo iterativo sin precondicionar.
3. **Gradientes Conjugados Precondicionado (GCP):** Algoritmo de Suñagua (2020) con soporte para precondicionadores:
   * **Jacobi / Diagonal:** $M = \text{diag}(A)$
   * **SSOR:** Relajación Simétrica ($\omega = 1.0$)
   * **Cholesky Incompleto:** IC(0)
4. **Validación Teórica:** Verificación del Criterio de Sylvester ($\Delta_1, \Delta_2, \Delta_3, \Delta_4 > 0$) y cálculo exacto de autovalores mediante el algoritmo de rotaciones de Jacobi.

---

## 🚀 Instrucciones de Ejecución Local
No requiere instalación de servidores ni entornos Node.js/Python complejos. La aplicación es totalmente autónoma (*Single-Page Application*):

1. **Clonar el repositorio:**
   ```bash
   git clone https://github.com/tu-usuario/desafio-metodos-numericos-gcp.git
   ```
2. **Abrir en el navegador:**
   * Haz doble clic sobre el archivo `index.html` o ábrelo desde cualquier navegador web moderno (Google Chrome, Mozilla Firefox, Edge).

---

## 🧪 Módulo de Pruebas de Software (QA Suite)
La aplicación integra un panel ejecutable de pruebas de calidad en la Sección 6:
* **QA-01 (Carga de Escenarios):** Verifica la convergencia en los 3 escenarios obligatorios.
* **QA-02 (Matriz No Válida):** Comprueba que matrices no simétricas o no SPD sean detectadas sin colapsar el sistema.
* **QA-03 (Edición Dinámica):** Re-cálculo instantáneo al modificar coeficientes en tiempo real.
* **QA-04 (Ganancia de Precondicionamiento):** Confirma que $k_{GCP} \le k_{GC}$ en matrices mal condicionadas.

---

## 📚 Cita Bibliográfica
* **Suñagua S., P. (2020).** *Método de Gradientes Conjugados Precondicionado.* Revista Boliviana de Matemática UMSA, 04, 2-7.
* **Golub, G. H., & Van Loan, C. F. (2013).** *Matrix Computations (4th ed.).* Johns Hopkins University Press.
* **Saad, Y. (2003).** *Iterative Methods for Sparse Linear Systems (2nd ed.).* SIAM.
```
