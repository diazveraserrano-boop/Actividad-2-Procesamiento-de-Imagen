# Segmentación de Vasos Retinianos con U-Net: Optimización Secuencial de Hiperparámetros
\# Este proyecto implementa y entrena una arquitectura U-Net para la segmentación de vasos sanguíneos en imágenes de fondo de ojo. El objetivo principal es analizar cómo cada hiperparámetro afecta al rendimiento cuando se optimiza de forma acumulativa, manteniendo los cambios que mejoran los resultados y descartando los que los empeoran.
---
# Objetivos del proyecto
Implementar una arquitectura U-Net funcional para segmentación biomédica.<br>
Entrenar utilizando un dataset reducido de imágenes de retina (“fundus”).<br>
Evaluar de manera secuencial distintos hiperparámetros:<br>
* Loss Function
* Patience
* Batch Size
* Image Size
* Optimizer
* Data Augmentation
* Activation Function
* Normalization
* Dataset Size
* Epoch Number
* Weight Initializer
* Output Activation Function
* Callbacks (EarlyStopping, Checkpoint) <br>
Determinar qué configuraciones mejoran realmente la segmentación.<br>
Este proyecto implementa y entrena una arquitectura U-Net para la segmentación de vasos sanguíneos en imágenes de fondo de ojo. El objetivo principal es analizar cómo cada hiperparámetro afecta al rendimiento cuando se optimiza de forma acumulativa, manteniendo los cambios que mejoran los resultados y descartando los que los empeoran.
