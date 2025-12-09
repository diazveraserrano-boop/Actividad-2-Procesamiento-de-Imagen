# Actividad-2-Procesamiento-de-Imagen
Creado por Álvaro Díaz y Pablo Durán

Este proyecto forma parte de una actividad universitaria centrada en el procesamiento de imágenes médicas, específicamente en la segmentación de vasos sanguíneos en imágenes de fondo de ojo.

Se utiliza la arquitectura U-Net, ampliamente empleada en segmentación biomédica, y se desarrolla un proceso sistemático de optimización en el que se evalúa el impacto de múltiples hiperparámetros y componentes del modelo.

El objetivo es obtener una configuración óptima que permita mejorar la precisión del modelo, evitar sobreajuste y aprovechar eficientemente los recursos computacionales.

Objetivos

Entrenar una U-Net para segmentación binaria de vasos retinianos.

Optimizar progresivamente parámetros del modelo mediante experimentación controlada.

Analizar el impacto de cada modificación en métricas como:

F1-Score

Dice Coefficient

IoU

Metodología

Se aplica un enfoque acumulativo de optimización:

Se parte de una configuración base.

Se modifica un único parámetro por experimento.

El mejor resultado se fija para la siguiente iteración.

De esta forma se mide directamente el aporte real de cada componente en el rendimiento final del modelo.

Parámetros analizados

A lo largo del estudio se evalúan los siguientes elementos:

Función de pérdida

BCE

Dice Loss

BCE + Dice
→ Mejor resultado: Dice Loss

Early Stopping

Paciencias de 7, 10 y 15
→ Mejor resultado: Patience = 15

Batch Size

8, 4, 2
→ Mejor resultado: Batch size = 2

Tamaño de imagen

512×512, 256×256, 128×128
→ Mejor rendimiento: 512×512
→ Mejor equilibrio costo/precisión: 128×128

Optimizador

SGD

Adam

RMSprop
→ Mejor resultado: RMSprop

Data Augmentation

Suave

Moderada

Fuerte
→ Mejor resultado: Augmentación suave

Función de activación interna

ReLU

Leaky ReLU

ELU
→ Mejor resultado: ELU

Normalización

Min/Max

Estandarización

Sin normalizar
→ Mejor resultado: Min/Max scaling (x/255)

Tamaño del dataset

25, 100, 500 imágenes
→ Mejor generalización: 100 imágenes

Épocas

5, 50, 100
→ Mejor resultado: 100 épocas

Inicialización de pesos

Random Normal

He Normal

Por defecto
→ Mejor resultado: He Normal

Monitor Checkpoint

val_loss

val_iou_metric

val_dice_coef
→ Más estable: val_dice_coef (mode='max')

Monitor Early Stopping

val_loss

val_iou_metric

val_dice_metric
→ Mejor estabilidad general: val_dice_metric (mode='max')

Resultados principales

El rendimiento mejora significativamente con el proceso acumulativo de optimización.

Las métricas de segmentación aumentan notablemente frente al modelo base.

La configuración óptima presenta curvas de validation accuracy muy estables y un validation loss bajo, minimizando el sobreajuste.
