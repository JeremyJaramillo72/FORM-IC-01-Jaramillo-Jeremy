# FORM-IC-01 — Investigación Individual: Arquitecturas Distribuidas en la Industria (Netflix: Zuul y Zuul 2)

**Universidad Técnica Estatal de Quevedo (UTEQ)**  
Facultad de Ciencias de la Computación · Carrera de Ingeniería en Software  
**Asignatura:** Aplicaciones Distribuidas (`ISR-701`) — Séptimo nivel, Paralelo "A"  
**Docente:** Gleiston Cicerón Guerrero Ulloa, PhD  
**Estudiante:** Luis Jeremy Jaramillo Acosta (`@JeremyJaramillo72`)  
**Período académico:** SPA 2026–2027  

---

## 1. Descripción general

Investigación individual formativa (`FORM-IC-01`, preparatoria para el Informe Académico Individual `TA-IND-02`) enfocada en el patrón **API Gateway** aplicado en producción por **Netflix**, analizando la evolución desde **Zuul 1** (arquitectura síncrona bloqueante sobre *servlets* Tomcat) hacia **Zuul 2** (arquitectura asíncrona y no bloqueante sobre bucles de eventos de Netty) y su aplicación crítica frente al Proyecto Fin de Curso del equipo (*Bolsa de Empleos para Graduados UTEQ*).

---

## 2. Estructura del repositorio

```text
FORM-IC-01-Jaramillo-Jeremy/
├── main.tex                       # Archivo principal LaTeX (carátula + 1 pág. de análisis + referencias + evidencias)
├── referencias.bib                # Bibliografía IEEE (fuentes oficiales de Netflix + 4 artículos 2022-2026 con DOI verificado)
├── main.pdf                       # Documento compilado completo en formato PDF
├── img/
│   └── captura_fuente_zuul.png    # Captura subrayada y anotada de la fuente principal del caso (Netflix TechBlog)
└── README.md                      # Instrucciones de compilación, orden de comandos y dependencias
```

---

## 3. Instrucciones de compilación en LaTeX

### 3.1 Compilador y procesador bibliográfico
- **Compilador principal:** `pdflatex` (distribución **TeX Live 2023+** o **MiKTeX 23+**, también compatible con **Overleaf**).
- **Motor de bibliografía:** `biber` (requerido por `biblatex` con estilo `ieee`).
- **Archivo principal:** `main.tex` (genera `main.pdf`).

### 3.2 Orden exacto de comandos
Ejecutar desde la raíz del repositorio en una terminal (`bash`, `cmd` o `PowerShell`):

```bash
pdflatex main.tex
biber main
pdflatex main.tex
pdflatex main.tex
```

### 3.3 Dependencias (paquetes LaTeX requeridos)
Todos los paquetes empleados forman parte de una instalación estándar de TeX Live (`texlive-latex-extra`, `texlive-fonts-recommended`, `texlive-lang-spanish` y `texlive-bibtex-extra` + `biber`) o MiKTeX:

- **Codificación e idioma:** `inputenc` (`utf8`), `fontenc` (`T1`), `babel` (`spanish,es-tabla`), `csquotes`.
- **Geometría, tipografía y secciones:** `geometry`, `newtxtext`, `newtxmath`, `microtype`, `titlesec`.
- **Figuras, tablas y color:** `graphicx`, `booktabs`, `xcolor`.
- **Bibliografía IEEE y enlaces:** `biblatex` (`backend=biber,style=ieee,sorting=none`), `xurl`, `hyperref`.

---

## 4. Verificación de referencias (DOI y fuentes primarias)

| Clave `.bib` | Obra | Año | Identificador / Enlace verificado |
| :--- | :--- | :---: | :--- |
| `cohen2013zuul` | M. Cohen y M. Hawthorne, *Announcing Zuul: Edge Service in the Cloud* (Netflix TechBlog) | 2013 | https://netflixtechblog.com/announcing-zuul-edge-service-in-the-cloud-ab3af5be08ee |
| `gonigberg2016zuul2` | A. Gonigberg y M. Cohen, *Zuul 2: The Netflix Journey to Asynchronous, Non-Blocking Systems* (Netflix TechBlog) | 2016 | https://netflixtechblog.com/zuul-2-the-netflix-journey-to-asynchronous-non-blocking-systems-45947377fb5c |
| `netflix2018opensourcing` | Netflix Technology Blog, *Open Sourcing Zuul 2* | 2018 | https://netflixtechblog.com/open-sourcing-zuul-2-82ea476cb2b3 |
| `haindl2024security` | P. Haindl, P. Kochberger y M. Sveggen, *IEEE Access*, vol. 12, pp. 90252–90286 | 2024 | https://doi.org/10.1109/ACCESS.2024.3406500 |
| `dhawan2026gateway` | M. Dhawan, *IEEE Access*, vol. 14, pp. 9348–9358 | 2026 | https://doi.org/10.1109/ACCESS.2026.3654150 |
| `santos2025catalog` | E. dos Santos y S. Casas, *DYNA*, vol. 92, no. 237, pp. 106–114 | 2025 | https://doi.org/10.15446/dyna.v92n237.118741 |
| `blinowski2022monolithic` | G. Blinowski, A. Ojdowska y A. Przybyłek, *IEEE Access*, vol. 10, pp. 20357–20374 | 2022 | https://doi.org/10.1109/ACCESS.2022.3152803 |
