<template>
  <v-app>
    <v-container>
      <h1>Recomendaciones</h1>
      <v-stepper :items="['Step 1', 'Step 2', 'Step 3', 'Step 4']">
        <template v-slot:item.1>
          <v-card title="Support vector machine(SMV)" flat
            >"Máquina de soporte vectorial” es un algoritmo de aprendizaje
            supervisado que se utiliza ampliamente en problemas de clasificación
            y regresión. (herramienta de machine learning que puede descubrir
            patrones complejos en datos de alta dimensionalidad.)
          </v-card>
        </template>

        <template v-slot:item.2>
          <v-card title="Kernel function " flat
            >Una función kernel es una manera de transformar datos de un espacio
            de entrada a un espacio de mayor dimensionalidad. Esto permite que
            los datos que no son linealmente separables en el espacio original
            puedan ser separados de manera efectiva en un espacio de mayor
            dimensión donde la separación lineal sea posible.</v-card
          >
        </template>

        <template v-slot:item.3>
          <v-card title="K-Fold cross validation" flat
            >La validación cruzada de K-Fold evalúa el desempeño de modelos de
            aprendizaje automático. Permite estimar de forma confiable la
            capacidad de generalización de un modelo a nuevos datos.
          </v-card>
        </template>
        <template v-slot:item.4>
          <v-card title="MLPRegressor " flat
            >Se refiere a un Regresor de Perceptrón Multicapa. Es un tipo de
            modelo de aprendizaje automático que utiliza una red neuronal
            artificial con múltiples capas de nodos y puede usarse para predecir
            valores numéricos en problemas de regresión.</v-card
          >
        </template>
      </v-stepper>
    </v-container>
  </v-app>
</template>
