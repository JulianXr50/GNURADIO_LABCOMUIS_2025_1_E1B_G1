# PRÁCTICA 1C

## **Práctica 1C. Mediciones de potencia y frecuencia**

### **Objetivo General**
Familiarizarse con el uso de herramientas de software definido por radio (SDR) como GNU Radio, junto con equipos de medición como el USRP 2920, el osciloscopio R&S RTB2004 y el analizador de espectros R&S FPC1000. Los estudiantes aprenderán a medir y analizar parámetros clave en comunicaciones, como potencia, ancho de banda, relación señal a ruido (SNR) y piso de ruido.

---

## **Materiales y Equipos**
- **USRP 2920**: Radio definido por software.
- **Osciloscopio R&S RTB2004**: Para visualización de señales en el dominio del tiempo y frecuencia.
- **Analizador de Espectros R&S FPC1000**: Para mediciones en el dominio de la frecuencia.
- **Computador con GNU Radio**: Para simulación y generación de señales usando el USRP 2920.
- **Cables y conectores**: Para interconexión de equipos.

---

## **Actividad 1: Revisión de Especificaciones de los Equipos**

### **Objetivo**
Familiarizarse con las especificaciones técnicas de los equipos de laboratorio y entender cómo configurarlos para realizar mediciones.

### **Procedimiento**
#### **Revisar Manuales y Verificar Equipos:**
- Revisar las especificaciones de los equipos de laboratorio (USRP 2920, Osciloscopio R&S RTB2004 y Analizador de Espectros R&S FPC1000).
- Identificar las principales funciones y controles de los equipos.

#### **Seleccionar Especificaciones Relevantes:**
- Seleccionar las 5 especificaciones que consideren más relevantes de cada equipo.

#### **Configuración de los Equipos:**
- **USRP 2920:** Identificar el rango de frecuencia y ganancia configurable del radio. Para esto, conecte la alimentación y el cable de red al radio, y desde un terminal (`Ctrl + Alt + T`) ejecute el comando:
  ```bash
  uhd_usrp_probe
  ```
- **Osciloscopio R&S RTB2004:** Identificar el ancho de banda máximo, resolución vertical y tipos de mediciones soportadas.
- **Analizador de Espectros R&S FPC1000:** Identificar el rango de frecuencia, resolución y figura de ruido.

### **Evidencia**
Lista con las 5 especificaciones más relevantes de cada equipo.

#### **USRP 2920:**
- **Rango de frecuencia:** 50 MHz a 2.2 GHz
- **Ancho de banda de transmisión:** hasta 20 MHz
- **Potencia máxima de salida TX:** +20 dBm
- **Nivel máximo de entrada RX:** -15 dBm
- **Impedancia de puertos RF:** 50 ohmios

#### **Analizador de Espectros R&S FPC1000:**
- **Rango de frecuencia:** 5 kHz a 1 GHz (ampliable a 3 GHz)
- **Ancho de banda de resolución (RBW):** desde 1 Hz
- **Pantalla:** 10.1" WXGA (1366 × 768 píxeles)
- **Preamplificador integrado**
- **Impedancia de entrada RF:** 50 ohmios

#### **Osciloscopio UNI-T UTD2102CEX:**
- **Ancho de banda:** 100 MHz
- **Número de canales:** 2
- **Tasa de muestreo en tiempo real:** 1 GSa/s
- **Impedancia de entrada:** 1 MΩ en paralelo con 24 pF
- **Tensión máxima de entrada:** 400 V (pico)

---

## **Medición de Piso de Ruido Normalizado**

El piso de ruido normalizado se calcula usando la ecuación:

```
Piso de Ruido Normalizado = Potencia del ruido - 10log(RBW)
```

Sustituyendo los valores dados:
```
-100 dB - 10log(30) = -114.8 dB
```

---

## **Actividad 2: Simulación de Señales en GNU Radio**

### **Objetivo**
Generar y analizar señales en GNU Radio para entender cómo se comportan diferentes formas de onda en tiempo y frecuencia.

### **Análisis de Señales**
Analice y valide los resultados en el dominio del tiempo y de frecuencia si se modifica:
- El tipo de dato de la fuente (compleja o flotante).
- La forma de onda.
- La frecuencia y fase de la señal.
- La amplitud de la señal generada.
- Modifique el nivel de ruido del modelo de canal y analice el efecto en tiempo y frecuencia.

---

## **Actividad 3: Transmisión y Medición de Señales con el USRP 2920**

### **Objetivo**
Transmitir señales usando el USRP 2920 y medir parámetros clave como potencia, ancho de banda, piso de ruido y relación señal a ruido (SNR).

### **Procedimiento**
1. Configurar el USRP 2920 en GNU Radio para transmitir señales.
2. Medir las señales usando el Analizador de Espectros y Osciloscopio.
3. Comparar resultados con las simulaciones previas.

### **Resultados:**
| Tipo de Señal | Potencia (dBm) | SNR (dB) | Ancho de Banda (kHz) |
|--------------|---------------|----------|----------------|
| Cuadrada (flotante) | -39.13 | 60.87 | 10.279 |
| Cosenoidal (compleja) | -39.00 | 61.00 | 10.000 |
| Triangular (flotante) | -36.93 | 62.07 | 5.990 |

---

## **Actividad 4: Análisis de Resultados y Conclusiones**

### **Comparación de Resultados**
Los resultados obtenidos en las simulaciones y las transmisiones reales muestran diferencias debido al ruido y limitaciones de los equipos. En la simulación, las señales son ideales, mientras que en las mediciones reales con el USRP 2920, se observa degradación debido a interferencias electromagnéticas y sensibilidad de los dispositivos.

### **Reflexión sobre la SNR**
- La **SNR** es crucial en comunicaciones inalámbricas.
- Un **piso de ruido alto** reduce la capacidad de detectar señales débiles.
- La SNR varió entre **34.76 dB y 62.07 dB**, dependiendo del tipo de señal y entorno.

### **Conclusiones Finales**
- **Precisión de medición:** Depende del equipo y condiciones del entorno.
- **Optimización de mediciones:** Uso de preamplificadores y calibración.
- **Análisis espectral:** Validación de conceptos de Fourier y exponencial compleja.

---

## **Referencias**
1. GNU Radio Documentation: [https://www.gnuradio.org/](https://www.gnuradio.org/)
2. USRP 2920 Manual: [https://www.ettus.com/](https://www.ettus.com/)
