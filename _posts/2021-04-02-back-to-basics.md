---
layout: post
read_time: true
show_date: true
title: "¿Qué chingados es una red neuronal?"
date: 2021-04-02
img: posts/20210402/post7-header.webp
tags: [redes neuronales, aprendizaje automático, inteligencia artificial]
category: teoria
author: Armando Maynez
description: "Explícamelo como si tuviera 5 años: ¿qué es una red neuronal?"
---

La omnipresencia de la tecnología hoy en día ha hecho común leer noticias sobre inteligencia artificial. Solo con echar un vistazo rápido a los titulares del día, me encuentro con:

- [Esta poderosa técnica de IA provocó conflictos en Google y un intenso debate en la industria.](https://www.morningbrew.com/emerging-tech/stories/2021/03/29/one-biggest-advancements-ai-also-sparked-fierce-debate-heres?utm_source=morning_brew)
- [Cómo las empresas con IA evitaron los peores efectos del COVID](https://fortune.com/2021/04/02/ai-forecasting-supply-chain-factories-caterpillar-agco/)
- [Tecnología de IA detecta arterias como 'bombas de tiempo'](https://www.mobihealthnews.com/news/emea/ai-technology-detects-ticking-time-bomb-arteries)
- [La IA en el descubrimiento de fármacos empieza a cumplir con las expectativas](https://www.genengnews.com/insights/ai-in-drug-discovery-starts-to-live-up-to-the-hype/)
- [El Pentágono busca soluciones comerciales para preparar sus datos para IA](https://www.c4isrnet.com/artificial-intelligence/2021/04/02/pentagon-seeks-commercial-solutions-to-get-its-data-ready-for-ai/)

Negocios, manufactura, medicina, cadena de suministro, biotecnología y hasta defensa están cubiertos en esas noticias. Definitivamente los avances en inteligencia artificial, particularmente en aprendizaje automático y redes neuronales profundas, han permeado nuestra vida diaria y llegaron para quedarse. Pero ¿la mayoría de la gente sabe realmente de qué hablamos cuando decimos "una IA"?

Supongo que la mayoría se imagina un algoritmo, o quizá algo más físico como una máquina inteligente o un robot que se vuelve más listo con cada uso. Y no están tan lejos: una IA es básicamente un algoritmo que corre en una computadora. Pero ahí es donde normalmente termina el conocimiento general.

Dicen que la mejor forma de aprender algo es tratar de explicarlo, así que haré un intento personal de versión **ELI5 (Explícamelo Como Si Tuviera 5 Años)** para responder: ¿qué es una red neuronal?

---

### Un poco de historia

Los humanos han estado jugueteando con la idea de una máquina inteligente desde hace mucho. Algunos dicen que la IA ya había sido conceptualizada por los griegos antiguos ([fuente](https://www.thinkautomation.com/bots-and-ai/a-history-of-automation-the-rise-of-robots-and-ai/)). A lo largo de la historia ha habido intentos por construir máquinas "inteligentes", como el famoso ‘Motor Analítico’ de Charles Babbage en 1837:

![The Analytical Engine](./assets/img/posts/20210402/post7-analytical-engine.jpg)  
<small>El Motor Analítico de Charles Babbage - 1837</small>

Después, a mediados del siglo pasado, intentando imitar cómo funciona el cerebro humano, nacieron las redes neuronales. Frank Rosenblatt en Cornell propuso el [perceptrón](./single-neuron-perceptron.html), un sistema muy simple que toma ciertos valores de entrada, realiza operaciones matemáticas básicas, y genera una salida.

![Un perceptrón](./assets/img/posts/20210125/Perceptron.png)

Imagina que el cerebro de una mosca es un perceptrón. Las entradas son los valores de las células en sus ojos: si detectan algo, emiten un 1; si no, un 0. Al juntar todos esos 1s y 0s, el perceptrón decide si huir (1) o quedarse (0).

![Ojo de la mosca](./assets/img/posts/20210402/post7-housefly-eye.jpg)  
![Visión de la mosca](./assets/img/posts/20210402/post7-fly-vision.jpg)

El perceptrón simplemente hace una suma ponderada: multiplica cada entrada por un "peso" (parámetro), las suma, y con eso da su resultado.

Y aquí llega la magia: esos "pesos" pueden **aprenderse** ajustándose para minimizar la diferencia entre lo que se espera y lo que calcula. A ese proceso lo llamamos **entrenar la red neuronal**.

<tweet>Esta idea es tan poderosa que hoy en día sigue siendo uno de los pilares fundamentales de lo que llamamos inteligencia artificial.</tweet>

---

### De perceptrones a redes complejas

Una red neuronal básica es solo un montón de perceptrones conectados. El perceptrón ya no es "el cerebro de la mosca", sino una sola **neurona** de toda la red.

![Perceptrón multicapa](./assets/img/posts/20210402/post7-multilayer-perceptron.png)

Una red neuronal típica tiene:
- **Entradas**
- **Capas ocultas**
- **Salida**

![Componentes de red neuronal](./assets/img/posts/20210228/nnet_flow.gif)

---

### Entrada

Las entradas son números. Cualquier cosa que se pueda convertir a número puede ser una entrada: letras, píxeles, frecuencias de sonido, datos de sensores, etc.

Por ejemplo, una imagen en color tiene píxeles, y cada píxel puede dividirse en tres valores (rojo, verde y azul), así que un solo píxel se transforma en 3 entradas distintas.

---

### Capas ocultas

Una "capa" es un grupo de perceptrones que hacen exactamente la misma operación matemática, pero con diferentes pesos. La más común es la **capa densa**, donde todas las entradas están conectadas a todas las neuronas.

![Capas densas](./assets/img/posts/20210402/post7-dense-layers.png)

Cada capa puede conectarse a otra, y el número de capas y neuronas depende del problema que queremos resolver. La combinación de capas, neuronas, entradas y salidas se llama la **topología de la red**.

---

### Salida

La última capa genera el resultado final. Por ejemplo, si entrenamos una red para reconocer animales, cada salida podría representar una especie distinta y el valor sería qué tanta confianza tiene la red en que la imagen pertenece a esa especie.

Después de entrenarse con datos conocidos, la red puede hacer predicciones con nuevos datos. Y como las operaciones que hace son muy simples, es súper eficiente y rápida.

---

### Ejemplo: ¿Cómo entiende Alexa?

![Alexa reconociendo voz](./assets/img/posts/20210402/post7-alexa.png)

Pedirle a Alexa: "pon música de Van Halen", parece fácil, pero detrás hay varias redes neuronales trabajando:

#### 1. Reconocimiento de voz

Convierte tu voz en texto. Esto es difícil por todas las variaciones humanas (acento, timbre, velocidad). Pero una red neuronal puede aprender a hacerlo con suficiente entrenamiento.

#### 2. Comprensión del lenguaje natural

Después de tener el texto, la IA debe **entender** qué quisiste decir. Detecta el comando, el sujeto, el contexto. Identifica: "Alexa", "pon música", "Van Halen".

![Lenguaje natural](./assets/img/posts/20210402/post7-alexa-natural-lang.png)

#### 3. Responderte

Luego, genera una respuesta hablada usando **síntesis de voz**, eligiendo el tono y duración adecuados: *"Reproduciendo canciones de Van Halen en Spotify."*

![Pasos de Alexa](./assets/img/posts/20210402/post7-alexa-steps.png)  
<small>Aunque parece complejo, todo se reduce a simples operaciones matemáticas</small>

---

Una vez entrenadas, las redes de Alexa hacen su magia con unas cuantas operaciones matemáticas. Como dije antes, seguiré escribiendo más sobre redes neuronales, y el próximo artículo se adentrará un poco más en las matemáticas detrás de estas maravillas.

