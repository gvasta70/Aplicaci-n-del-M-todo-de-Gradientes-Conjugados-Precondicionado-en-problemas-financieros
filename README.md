
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
