Estructura Recomendada de Capítulos
1. Introducción
    Antecedentes: Breve historia de la psicrometría y herramientas de cálculo.
    Planteamiento del Problema: ¿Por qué un graficador para mezclas binarias? (Limitaciones de las cartas tradicionales aire-agua a 1 atm).
    Objetivos: Generar una herramienta versátil para diferentes presiones y componentes.
    Justificación: Relevancia técnica en procesos industriales (secado, refrigeración con amoníaco, etc.).
2. Marco Teórico (El Fundamento Físico)Este capítulo debe estar listo para que cualquier ingeniero entienda las ecuaciones que programaste.
    Psicrometría de Mezclas Binarias: Definiciones de $\omega, \phi, h, v$ extendidas a cualquier masa molar $M$.
    Termodinámica de Gases Reales: * Ecuaciones de Estado ($EoS$): Virial (Tsonopoulos/Meng-Duan) y Lee-Kesler.Cálculo de Fugacidad y Entalpía en Exceso ($\Delta H_{exceso}$).
    Correlaciones de Presión de Saturación: Ecuaciones de Antoine y Wagner.
3. Marco Conceptual (El Fundamento del Software)
    Arquitectura del Sistema: Explicación del modelo de datos.
    Tecnologías Utilizadas: Justificación de Rust (backend) y Flutter (frontend) si es el caso, o las herramientas que estés usando.
    Conceptos de Computación Gráfica: Cómo se realiza el mapeo de coordenadas termodinámicas a píxeles en pantalla.
4. Marco Metodológico (La Ingeniería)Diseño de la Investigación: Tipo de investigación (aplicada).
    Desarrollo del Algoritmo: Explicación de los diagramas de flujo que ya tienes (main_flowchart, excess_enthalpy_submodule).Lógica de Iteración: Cómo resuelves el Bulbo Húmedo (ej. Newton-Raphson).
5. Implementación y Resultados
    Presentación del Software: Capturas de pantalla de la interfaz.
    Pruebas de Funcionamiento: Generación de diagramas para:
        Agua-Aire (Caso base para validación).
        Amoniaco-Nitrógeno (Caso de mezcla binaria no convencional).Comparativa: Mostrar el error relativo entre tu software y tablas estandarizadas.
6. Conclusiones y Recomendaciones
    Cumplimiento de objetivos.Limitaciones encontradas (ej. comportamiento cerca del punto crítico).Trabajos futuros (ej. mezclas multicomponente).
    
Cómo organizar esto en tu main.tex
Para mantener el orden en tu código, te sugiero estructurar la sección de capítulos así:
\mainmatter
\restauraCabecera

% 1. Introducción
\include{chapters/details/introduction/01_Introduccion}

% 2. Marco Teórico
\include{chapters/marco_teorico/marco_teorico}
\include{chapters/marco_teorico/mt_psychrometry}

% 3. Marco Conceptual
\include{chapters/marco_conceptual/marco_conceptual}
\include{chapters/marco_conceptual/procesos_psichrometricos}

% 4. Metodología y Algoritmos (Aquí entran tus diagramas y lógica)
\include{chapters/marco_metodologico/diseno_investig}
\section{Algoritmos y Lógica de Cálculo}
\input{algorithms/main_algorithm}
\input{flowcharts/main_flowchart}

% 5. Resultados (Donde muestras el graficador funcionando)
\include{chapters/resultados/pruebas_validacion}

% 6. Conclusiones
\include{chapters/conclusiones/conclusiones}
Un consejo para tus diagramas de flujo:Dado que usas pgfplots y tikz, asegúrate de que el Capítulo 4 (Metodología) sea donde expliques cómo el algoritmo decide qué correlación usar (por ejemplo, cuando el sistema decide usar Lee-Kesler en lugar de Virial basándose en la presión reducida).¿Te gustaría que te ayude a redactar el párrafo de Justificación técnica para el uso de mezclas binarias distintas al aire-agua?