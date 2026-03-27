# 🌀 Phase-Pi-Quantum-Prior

### Superselección Topológica $\mathbb{Z}/6\mathbb{Z}$: Derivación Analítica de Fases y Estabilización Disipativa para Criptoanálisis FTQC
[![Read in English](https://img.shields.io/badge/Lang-Read%20in%20English-blue?style=flat&logoColor=white&color=00529B)](https://github.com/NachoPeinador/Phase-Pi-Quantum-Prior/blob/main/README.md)
[![Python 3.10+](https://img.shields.io/badge/Python-3.10%2B-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.xxxxxxxx.svg)](https://doi.org/10.5281/zenodo.xxxxxxxx)
[![ORCID](https://img.shields.io/badge/ORCID-0009--0008--1822--3452-A6CE39?style=flat&logo=orcid&logoColor=white)](https://orcid.org/0009-0008-1822-3452)
[![X](https://img.shields.io/badge/X-%40todos__lumpen-000000?style=flat&logo=x&logoColor=white)](https://twitter.com/todos_lumpen)
[![Papers](https://img.shields.io/badge/Paper-Read_PDF-B31B1B?style=flat&logo=latex&logoColor=white)](https://github.com/NachoPeinador/Phase-Pi-Quantum-Prior/blob/main/Paper/Superseleccion_Topologica_Z6Z.pdf)

---

## 🎯 TL;DR – Lo Esencial

### 🔬 **Hitos Teóricos**

* 📐 **Descubrimiento Analítico de Fases:** Demostración de que las fases óptimas de inicialización ($\phi_1, \phi_2$) no son heurísticas. $\phi_2 = \pi$ emerge del isomorfismo del grupo de unidades $(\mathbb{Z}/6\mathbb{Z})^{\times} \cong \mathbb{Z}/2\mathbb{Z}$ actuando como una Holonomía de Berry no conmutativa.
* 🔄 **Origen en el Grupo de Renormalización (RG):** La fase termodinámica $\phi_1 \approx R_{\text{fund}}/10$ se deriva estrictamente como un punto fijo infrarrojo de la función beta de Callan-Symanzik, acoplada al invariante de Euler-Kronecker.
* ⚡ **Complejidad Polinómica:** Preparación exacta del estado mediante **Matrix Product States (MPS)** con dimensión de enlace topológica constante $\chi \le 6$, evitando el coste exponencial $\mathcal{O}(2^n)$ de las distribuciones arbitrarias.
* 🛡️ **Lindbladiano Padre y Fase NEE:** Construcción de un superoperador disipativo libre de frustración con un \textit{Liouvillian gap} que no colapsa ($\Delta = \Omega(1)$). Acotado por la **Desigualdad de Sóbolev Logarítmica Modificada (MLSI)**, esto garantiza una mezcla rápida estricta (\textit{rapid mixing}), probando que el sistema entra en una **Fase Extendida No Ergódica (NEE)** que derrota la Hipótesis de Termalización del Estado Propio (ETH).

### 📊 **Validación Computacional (N=60 Qubits)**

* 📉 **Ley de Área Disipativa:** Bajo una tasa de ruido despolarizante de $p=0.015$, la entropía bipartita MPDO $S_2$ se satura estrictamente en $\approx 1.65$ bits, desafiando la Ley de Volumen ergódica (30 bits).
* 🧪 **Plateau de Robustez:** El análisis de sensibilidad confirma que la fase NEE es estructuralmente estable frente a fluctuaciones de \textit{gauge} en el rango $\phi_1 \in [0, 0.1]$ rad.
* 🚀 **Ganancia de Recursos FTQC:** La reducción estructural del espacio de búsqueda (purga del 66.6%) permite una reducción masiva en el prefactor de puertas Toffoli (**~189.000 millones de puertas T ahorradas** para RSA-2048). Esto comprime drásticamente el volumen espacio-temporal de los ciclos de síndrome de los **Códigos de Superficie** ($\tau$), relajando los umbrales de destilación de estados mágicos.

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
    
    H --> NEE["Lindbladiano Padre y MLSI<br>Fase NEE (Ley de Área)"]
    H --> MPS["Compilación MPS<br>χ ≤ 6 | Profundidad O(poly(n))"]
    H --> CRYP["FTQC con Código de Superficie<br>Reducción Masiva del T-Count"]

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

La suite de validación empírica se divide en tres exhaustivos Jupyter Notebooks. Cada notebook está meticulosamente diseñado para demostrar las afirmaciones teóricas del manuscrito a través de código funcional, contracciones tensoriales exactas y simulaciones termodinámicas.

### 📓 Notebook I: Fundamentos Aritméticos y Termodinámicos
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/NachoPeinador/Phase-Pi-Quantum-Prior/blob/main/Notebooks/Arithmetic_and_Thermodynamic_Foundations_of_Z_6Z_Superselection.ipynb)

Este notebook proporciona el marco experimental y la validación empírica para el **Prior Topológico $\mathbb{Z}/6\mathbb{Z}$**. Demuestra cómo romper con la tradicional superposición uniforme de máxima entropía (utilizada en algoritmos como el de Shor) confinando la amplitud cuántica estrictamente a canales aritméticos resonantes.

**Validaciones y Descubrimientos Clave:**
* **Confinamiento Aritmético (\textit{Zero-Leakage} / Fuga Cero):** Demuestra que el **100%** de los números primos $p > 3$ residen exclusivamente en las clases de congruencia $1 \pmod 6$ y $5 \pmod 6$, anulando por completo las amplitudes en los canales estériles ($0, 2, 3, 4$).
* **Impedancia Informacional ($R_{\text{fund}}$):** Deriva y valida las constantes termodinámicas que rigen el mapeo de la topología aritmética ternaria sobre qubits binarios. Para aislar el canal 1 con una fidelidad del **99.98%**, el sistema requiere estrictamente la fase $\phi_1 \approx R_{\text{fund}}/10$.
* **Óptimo de Fase Dual y Transferencia Isomórfica:** Demuestra que el aislamiento absoluto para la clase 5 se logra en $\phi_2 = \pi$. La transición entre canales no requiere recalibración del sistema, solo la inyección de esta fase geométrica pura, confirmando la dualidad del inverso multiplicativo ($5 \equiv -1 \pmod 6$).
* **Simetría Discreta y Paridad Modular:** Valida numéricamente la periodicidad $\pi$ de la función de partición $Z(\phi)$ y la dualidad exacta $P_1(\phi) = P_5(\phi+\pi)$. La preservación del invariante de paridad modular $\langle \hat{P} \rangle$ garantiza que las rotaciones holonómicas sean fundamentalmente estables y libres de entropía.

**Conclusión:** Este marco permite la preparación de estados cuánticos utilizando **Estados de Producto Matricial (MPS)** con una dimensión de enlace acotada ($\chi \le 6$). Esto evade estrictamente el límite de profundidad exponencial $\mathcal{O}(2^n)$ y protege al sistema de la decoherencia a través de la Fase No Ergódica Extendida (NEE).

---

### 📓 Notebook II: El Desafío del Hardware NISQ y la Compresión MPS
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/NachoPeinador/Phase-Pi-Quantum-Prior/blob/main/Notebooks/The_NISQ_Hardware_Challenge_and_MPS_Compression.ipynb)

En este notebook, pasamos de las matemáticas abstractas a la **Ingeniería de Hardware Cuántico**. Demostramos que el Prior Topológico $\mathbb{Z}/6\mathbb{Z}$ no es meramente una construcción teórica, sino un vector de estado cuántico unitario y válido que puede codificarse en la matriz densidad de un ordenador cuántico real, superando la histórica profundidad de circuito exponencial $\mathcal{O}(2^n)$ típicamente requerida para la preparación de estados dispersos.

**Validaciones y Descubrimientos Clave:**
* **Unitariedad Perfecta y Fuga Cero (vía Qiskit):** Demuestra que las fases exactas $\phi_1 = R_{\text{fund}}/10$ y $\phi_2 = \pi$ generan un estado cuántico físicamente válido que anula perfectamente las amplitudes en los canales estériles, acotando estrictamente la complejidad del entrelazamiento.
* **El Camino a la Compresión MPS:** Demuestra que las reglas de superselección actúan como un autómata finito de 6 estados. Esto permite compilar el estado usando **Estados de Producto Matricial (MPS)** con una dimensión de enlace máxima $\chi \le 6$, garantizando una eficiente profundidad de circuito polinómica $\mathcal{O}(\text{poly}(n))$.
* **Unicidad del Estado Estacionario ($\lambda_0 = 0$):** Mediante análisis espectral exacto, confirmamos que el autovalor dominante es exactamente cero, demostrando que el estado MPS es el único "estado oscuro" (\textit{dark state}) del Lindbladiano Padre.
* **Protección Macroscópica y Mezcla Rápida (\textit{Rapid Mixing}, $\Delta = \Omega(1)$):** Muestra que el hiato o \textit{gap} espectral del Liouvilliano no colapsa en el límite termodinámico ($N \to \infty$). En su lugar, la penalización topológica escala de forma aditiva ($\Delta \propto N$), garantizando una relajación ultrarrápida hacia el subespacio protegido y evadiendo la Hipótesis de Termalización del Estado Propio (ETH).

**Conclusión:** El subespacio topológico $\mathbb{Z}/6\mathbb{Z}$ actúa como un atractor disipativo estrictamente estable y libre de frustración. La fase No Ergódica Extendida (NEE) no es un transitorio pre-termal ni un artefacto de tamaño finito, sino una realidad macroscópica asintótica que protege matemáticamente al hardware de la decoherencia.

---

### 📓 Notebook III: Criptoanálisis Híbrido y Estrategia Adaptativa Óptima
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/NachoPeinador/Phase-Pi-Quantum-Prior/blob/main/Notebooks/Hybrid_Cryptanalysis_and_Optimal_Adaptive_Strategy.ipynb)


En este último notebook, trasladamos nuestros descubrimientos a nivel termodinámico y de hardware al dominio del **Criptoanálisis Aplicado**. Simulamos la partición ortogonal del espacio de Hilbert contra módulos criptográficos objetivo (ej., RSA), cuantificando rigurosamente la reducción neta en las evaluaciones del oráculo en comparación con la inicialización de máxima entropía del algoritmo de Shor estándar.

**Validaciones y Descubrimientos Clave:**
* **La Estrategia Adaptativa Óptima:** Valida un protocolo de búsqueda tolerante a fallos de dos rondas que explota la simetría de inversión quiral y el invariante de paridad modular ($\langle \hat{P} \rangle$). La Ronda 1 inyecta $\phi_1 \approx R_{\text{fund}}/10$ para colapsar la amplitud sobre el canal $1 \pmod 6$. Si no tiene éxito, la Ronda 2 aplica una rotación holonómica $\Delta\phi = \pi$ para transferir íntegramente la masa de probabilidad al canal $5 \pmod 6$ con **fuga algorítmica cero** (\textit{zero algorithmic leakage}).
* **Compresión de Recursos FTQC:** Demuestra que purgar el 66.66% de las trayectorias de búsqueda estériles *antes* de la primera llamada al oráculo reduce directamente el prefactor polinómico del algoritmo de búsqueda en 2/3.
* **Reducción Masiva del \textit{T-Count} (RSA-2048):** Proyecta la estrategia sobre un módulo RSA-2048 macroscópico. Mientras que la inicialización estándar de Shor exige $\sim 2.83 \times 10^{11}$ compuertas T, la Estrategia de Búsqueda Modular (MST) elude aproximadamente **189 mil millones** de estas operaciones altamente costosas.
* **Relajación de los Umbrales de Coherencia:** Demuestra que la drástica reducción en la profundidad lógica disminuye significativamente la fidelidad de compuerta requerida y extiende el tiempo de coherencia efectivo necesario para una factorización exitosa.

**Conclusión:** La estrategia MST trasciende una mera aceleración matemática. Proporciona un "atajo" estructural y termodinámico que despresuriza los umbrales de corrección de errores, haciendo que el algoritmo de Shor sea viable en hardware de Computación Cuántica Tolerante a Fallos (FTQC) con niveles de ruido de fondo significativamente mayores de lo estimado previamente.

---

## 📂 Estructura del Repositorio

<details>
<summary><strong>👇 Clic para ver la estructura del repositorio</strong></summary>

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

</details>

---

## ⚖️ Licencia y Citación

Este proyecto utiliza un **esquema de doble licencia**:

  * **Código y Algoritmos:** [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0).
  * **Contenido Teórico y Manuscrito:** [Creative Commons Attribution 4.0 International (CC-BY-4.0)](https://creativecommons.org/licenses/by/4.0/).

**Citación BibTeX:**

```bibtex
@software{Peinador_Phase_Pi_2026,
  author = {Peinador Sala, José Ignacio},
  title = {Superselección Topológica Z/6Z: Derivación Analítica de Fases y Estabilización Disipativa para Criptoanálisis FTQC},
  url = {[https://github.com/NachoPeinador/Phase-Pi-Quantum-Prior](https://github.com/NachoPeinador/Phase-Pi-Quantum-Prior)},
  year = {2026},
  doi = {10.5281/zenodo.xxxxxxxx}
}
```

---

## 🔭 Contexto Filosófico

> *"La fase analítica no es un ajuste; es la penalización geométrica por intentar comprimir el vacío continuo en un registro binario discreto."*

Este trabajo establece que la aritmética no es una secuencia aleatoria, sino una **estructura ondulatoria determinista** codificada en la topología $\mathbb{Z}/6\mathbb{Z}$. Reconocer este hecho nos permite reescribir fundamentalmente las reglas del criptoanálisis cuántico y la inicialización de hardware para la era FTQC.

---

\<div align="center"\>

**Última Actualización:** Marzo 2026 | **Estado:** Versión Gold | Construido con ⚛️ & 🐍

\</div\>

