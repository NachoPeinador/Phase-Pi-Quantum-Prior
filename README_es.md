Aquí tienes la versión en español del `README.md`, traducida manteniendo el mismo nivel de rigor académico y la terminología técnica de alto nivel (FTQC, MPDO, Lindbladiano Padre) que consolidamos durante la revisión del artículo.

He ajustado el \\textit{badge} de idioma para que, en esta versión, apunte a la lectura en inglés.

Copia y pega este bloque en tu archivo `README_es.md`:

````markdown
# 🌀 Phase-Pi-Quantum-Prior

### Orígenes Analíticos de la Fase y Superselección Topológica $\mathbb{Z}/6\mathbb{Z}$ para la Preparación de Estados en NISQ/FTQC
[![Read in English](https://img.shields.io/badge/Lang-Read%20in%20English-blue?style=flat&logoColor=white&color=00529B)](https://github.com/NachoPeinador/Z6Z-Riemann-Spectrum/blob/main/README.md)
[![Python 3.10+](https://img.shields.io/badge/Python-3.10%2B-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.xxxxxxxx.svg)](https://doi.org/10.5281/zenodo.xxxxxxxx)
[![ORCID](https://img.shields.io/badge/ORCID-0009--0008--1822--3452-A6CE39?style=flat&logo=orcid&logoColor=white)](https://orcid.org/0009-0008-1822-3452)
[![X](https://img.shields.io/badge/X-%40todos__lumpen-000000?style=flat&logo=x&logoColor=white)](https://twitter.com/todos_lumpen)
[![Papers](https://img.shields.io/badge/Paper-Read_PDF-B31B1B?style=flat&logo=latex&logoColor=white)](https://github.com/NachoPeinador/Z6Z-Riemann-Spectrum/blob/main/Papers/Z6Z_EHH_paper.pdf)

---

## 🎯 TL;DR – Lo Esencial

### 🔬 **Hitos Teóricos**

* 📐 **Descubrimiento Analítico de Fases:** Demostración de que las fases óptimas de inicialización ($\phi_1, \phi_2$) no son heurísticas. $\phi_2 = \pi$ emerge del isomorfismo del grupo de unidades $(\mathbb{Z}/6\mathbb{Z})^{\times} \cong \mathbb{Z}/2\mathbb{Z}$ actuando como una Holonomía de Berry no conmutativa.
* 🔄 **Origen en el Grupo de Renormalización (RG):** La fase termodinámica $\phi_1 \approx R_{\text{fund}}/10$ se deriva estrictamente como un punto fijo infrarrojo de la función beta de Callan-Symanzik, acoplada al invariante de Euler-Kronecker.
* ⚡ **Complejidad Polinómica:** Preparación exacta del estado mediante **Matrix Product States (MPS)** con dimensión de enlace topológica constante $\chi \le 6$, evitando el coste exponencial $\mathcal{O}(2^n)$ de las distribuciones arbitrarias.
* 🛡️ **Lindbladiano Padre y Fase NEE:** Construcción de un superoperador disipativo libre de frustración con una brecha espectral (\textit{Liouvillian gap}) que no colapsa ($\Delta = \Omega(1)$). Esto prueba rigurosamente que el sistema entra en una **Fase Extendida No Ergódica (NEE)**, derrotando la Hipótesis de Termalización del Estado Propio (ETH).

### 📊 **Validación Computacional (N=60 Qubits)**

* 📉 **Ley de Área Disipativa:** Bajo una tasa de ruido despolarizante de $p=0.015$, la entropía bipartita MPDO $S_2$ se satura estrictamente en $\approx 1.65$ bits, desafiando la Ley de Volumen ergódica (30 bits).
* 🧪 **Plateau de Robustez:** El análisis de sensibilidad confirma que la fase NEE es estructuralmente estable frente a fluctuaciones de \textit{gauge} en el rango $\phi_1 \in [0, 0.1]$ rad.
* 🚀 **Ganancia de Recursos FTQC:** La reducción estructural del espacio de búsqueda (purga del 66.6%) permite una reducción masiva en el prefactor de puertas Toffoli (**~189.000 millones de puertas T ahorradas** para RSA-2048), relajando los umbrales de corrección de errores cuánticos.

---

## 🔍 Visión General de la Investigación: Más allá de la Superposición Uniforme

Los algoritmos cuánticos estándar (ej. Shor, Grover) inicializan los registros en un estado de máxima ignorancia: la superposición uniforme $H^{\otimes n}|0\rangle$. Aunque es fácil de preparar, esto obliga al oráculo a procesar un volumen exponencial de trayectorias aritméticamente imposibles, exigiendo tiempos de coherencia inasumibles.

Esta investigación introduce el **Prior Topológico $\mathbb{Z}/6\mathbb{Z}$**, un protocolo estructurado de Preparación de Estados Cuánticos (QSP) que inyecta inteligencia aritmética en el estado de vacío. Al alinear la amplitud cuántica con la densidad modular de los números primos, transformamos la factorización de enteros de una búsqueda ciega a una **resonancia topológicamente sintonizada**, optimizada para hardware NISQ y las primeras generaciones FTQC (Tolerantes a Fallos).

---

## 🧭 Marco Conceptual

```mermaid
graph TD
    A["Topología Aritmética<br>Anillo Z/6Z"] --> B["Superselección Modular<br>Canales Resonantes 1 y 5"]
    C["Isomorfismo de Grupo<br>(Z/6Z)× ≅ Z/2Z"] --> D["Gauge No Conmutativo<br>φ₂ = φ₁ + π"]
    E["Termodinámica de la Información<br>Flujo RG e Impedancia"] --> F["Punto Fijo Infrarrojo<br>φ₁ ≈ R_fund/10"]
    
    B --> H["Estado Prior Topológico<br>|ψ_top⟩"]
    D --> H
    F --> H
    
    H --> NEE["Lindbladiano Padre (Δ > 0)<br>Fase NEE (Ley de Área)"]
    H --> MPS["Compilación MPS<br>χ ≤ 6 | Profundidad O(poly(n))"]
    H --> CRYP["Criptoanálisis FTQC<br>Reducción Masiva del T-Count"]

    style H fill:#f96,stroke:#333,stroke-width:3px
    style NEE fill:#bbf,stroke:#333,stroke-width:2px
    style CRYP fill:#bfb,stroke:#333,stroke-width:2px
````

---

## 📊 Resultados Experimentales y Escalado Macroscópico

Las siguientes tablas resumen el rendimiento termodinámico y computacional del estado $\mathbb{Z}/6\mathbb{Z}$ bajo dinámica de sistemas abiertos (Ecuación Maestra de Lindblad) utilizando **Operadores de Densidad de Producto Matricial (MPDO)** hasta $N=60$ qubits:

### 1\. Resiliencia Termodinámica (N=60, p=0.015)

| Métrica | Prior Modular (Fase NEE) | Base Uniforme (Ergódica ETH) | Ventaja |
| :--- | :--- | :--- | :--- |
| **Entrelazamiento Bipartito ($S_2$)** | **1.6495 bits** | **30.0 bits** | **Reducción del 94.5%** |
| **Comportamiento Asintótico** | Ley de Área ($S \le \log_2 \chi$) | Ley de Volumen ($S \sim N/2$) | Inmunidad Térmica |
| **Gap de Liouville ($\Delta$)** | $\Omega(1)$ (Mezcla Rápida) | $\to 0$ (Mezcla Lenta) | Libre de Frustración |

### 2\. Proyección de Recursos FTQC (RSA-2048)

| Métrica | Shor Clásico ($H^{\otimes n}$) | Estrategia Adaptativa MST | Impacto |
| :--- | :--- | :--- | :--- |
| **Entropía del Espacio de Búsqueda** | 100% (Todos los canales) | 33.3% (Solo resonantes) | **Purga Zero-Leakage** |
| **T-Count Estimado** | $\sim 2.83 \times 10^{11}$ puertas | $\sim 9.45 \times 10^{10}$ puertas | **\~1.89e11 Puertas Ahorradas** |
| **Implicación en Hardware** | FTQC Profundo Requerido | FTQC Temprano / NISQ Tardío | **Relajación del Umbral** |

---

## 🚀 Reproducibilidad y Laboratorio Computacional

La suite de validación empírica está dividida en tres Cuadernos Jupyter (Jupyter Notebooks) exhaustivos.

  * **Cuaderno I:** Validación Geométrica y Coherencia de Fase.
  * **Cuaderno II:** Viabilidad en Hardware, Contracción Tensorial MPDO (N=60) y Análisis Espectral de Liouville.
  * **Cuaderno III:** Criptoanálisis Híbrido, Estrategia Adaptativa y Proyecciones de T-Count FTQC.

### Instalación Local

```bash
git clone [https://github.com/NachoPeinador/Phase-Pi-Quantum-Prior.git](https://github.com/NachoPeinador/Phase-Pi-Quantum-Prior.git)
cd Phase-Pi-Quantum-Prior
pip install numpy matplotlib scipy sympy tensornetwork qiskit qiskit-aer tqdm
```

---

## 📂 Estructura del Repositorio

\<details\>
\<summary\>\<strong\>👇 Clic para ver la estructura del repositorio\</strong\>\</summary\>

```text
.
├── 📂 docs/               # Documentación Teórica
│   ├── 📄 Phase_Pi_Gold.pdf # El manuscrito definitivo revisado por pares
│   └── 📝 Phase_Pi_Gold.tex # Código fuente en LaTeX
│
├── 📂 notebooks/          # Suites de Validación Experimental
│   ├── 📓 01_Geometric_Phase_Validation.ipynb
│   ├── 📓 02_MPDO_Lindblad_NEE_Scaling.ipynb
│   └── 📓 03_FTQC_Cryptanalysis_TCount.ipynb
│
├── 📜 LICENSE             # Esquema dual: Apache 2.0 / CC-BY 4.0
└── 📜 CITATION.cff        # Metadatos de citación académica
```

\</details\>

---

## ⚖️ Licencia y Citación

Este proyecto utiliza un **esquema de doble licencia**:

  * **Código y Algoritmos:** [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0).
  * **Contenido Teórico y Manuscrito:** [Creative Commons Attribution 4.0 International (CC-BY-4.0)](https://creativecommons.org/licenses/by/4.0/).

**Citación BibTeX:**

```bibtex
@software{Peinador_Phase_Pi_2026,
  author = {Peinador Sala, José Ignacio},
  title = {El Origen Analítico de la Fase π: Simetría, Dualidad y Preparación de Estados en la Superselección Topológica Z/6Z},
  url = {[https://github.com/NachoPeinador/Phase-Pi-Quantum-Prior](https://github.com/NachoPeinador/Phase-Pi-Quantum-Prior)},
  year = {2026},
  doi = {10.5281/zenodo.xxxxxxxx}
}
```

---

## 🔭 Contexto Filosófico

> *"La fase analítica no es un ajuste; es la penalización geométrica por intentar comprimir el vacío continuo en un registro binario discreto."*

Este trabajo establece que la aritmética no es una secuencia aleatoria, sino una **estructura ondulatoria determinista** codificada en la topología $\mathbb{Z}/6\mathbb{Z}$. Reconocer este hecho nos permite reescribir fundamentalmente las reglas del criptoanálisis cuántico y la inicialización de hardware para la era FTQC.

-----

\<div align="center"\>

**Última Actualización:** Marzo 2026 | **Estado:** Versión Gold | Construido con ⚛️ & 🐍

\</div\>

---
