<template>
  <div>
    <v-card
      class="pa-4"
      img="https://cdn.vuetifyjs.com/images/toolbar/map.jpg"
      flat
    >
      <v-toolbar dense floating>
        <v-autocomplete
          v-model="searchTerm"
          :items="allTerms"
          hide-details
          single-line
          placeholder="Buscar..."
        ></v-autocomplete>

        <v-btn icon @click="onSearch">
          <v-icon>mdi-magnify</v-icon>
        </v-btn>

        <v-btn icon>
          <v-icon>mdi-dots-vertical</v-icon>
        </v-btn>
      </v-toolbar>
    </v-card>

    <Definiciones :term="searchTerm" :definition="getDefinition(searchTerm)" />

    <v-snackbar v-model="snackbar" :timeout="3000" color="error">
      {{ snackbarMessage }}
    </v-snackbar>
  </div>
</template>

<script>
import Definiciones from './Definiciones.vue';

export default {
  components: {
    Definiciones,
  },
  data() {
    return {
      searchTerm: '',
      snackbar: false,
      snackbarMessage: '',
      definitions: [
        {
          id: 1,
          term: 'Neuronal Network',
          definition:
            'Red neuronal” modelo inspirado en el comportamiento de las neuronas y cómo se organizan formando la estructura del cerebro',
        },
        {
          id: 2,
          term: 'Features',
          definition:
            'Características se refieren a las variables o atributos que se utilizan como entradas para la red neuronal.',
        },
        {
          id: 3,
          term: 'Test',
          definition:
            'Prueba se utiliza para evaluar su desempeño en datos no vistos durante el entrenamiento. ',
        },
        {
          id: 4,
          term: 'Output',
          definition:
            'Salida capa final de la red neuronal que genera las predicciones o resultados finales. ',
        },
        {
          id: 5,
          term: 'Support vector machine(SMV)',
          definition:
            'Máquina de soporte vectorial es un algoritmo de aprendizaje supervisado que se utiliza ampliamente en problemas de clasificación y regresión. (herramienta de machine learning que puede descubrir patrones complejos en datos de alta dimensionalidad.) ',
        },
        {
          id: 6,
          term: 'Preprocessing',
          definition:
            ' preparación y manipulación de los datos de entrada antes de ser introducidos en la red neuronal para el entrenamiento o el test. Esto puede incluir tareas como normalización de datos, eliminación de valores atípicos, selección de características relevantes, codificación de variables, etc. El objetivo del preprocesamiento es mejorar la calidad de los datos y facilitar el entrenamiento efectivo de la red neuronal, lo que puede conducir a un mejor rendimiento del modelo. ',
        },
        {
          id: 7,
          term: 'Pipeline',
          definition:
            ' forma de automatizar el flujo de trabajo para producir el machine learning, son pasos secuenciales donde la entrada de un proceso es la salida del anterior. ',
        },
        {
          id: 8,
          term: 'Performance',
          definition:
            ' rendimiento” capacidad de un modelo para hacer predicciones o clasificaciones con eficiencia y precisión.',
        },
        {
          id: 9,
          term: 'Fit',
          definition:
            'se refiere al proceso de entrenamiento de la red neuronal utilizando un conjunto de datos de entrada (entrenamiento) para ajustar los pesos y sesgos de la red de manera que pueda realizar la tarea deseada con mayor precisión.  ',
        },
        {
          id: 10,
          term: 'Data extraction',
          definition:
            '(extracción de datos) proceso de recuperar información específica de una fuente de datos, como una base de datos, un documento o una página web, para su posterior análisis, procesamiento o almacenamiento. ',
        },
        {
          id: 11,
          term: 'Decition tree',
          definition:
            'Es una estructura similar a un diagrama de flujo en la que cada nodo interno representa una "prueba" en un atributo, cada rama representa el resultado de la prueba y cada nodo de hoja representa una etiqueta de clase (decisión tomada después de calcular todos los atributos) ',
        },
        {
          id: 12,
          term: 'Ensamble learning',
          definition:
            '(aprendizaje conjunto). Proceso de múltiples modelos como clasificadores o expertos se generan y se combinan para resolver un problema en particular  ',
        },
        {
          id: 13,
          term: 'Acurracy',
          definition:
            '(exactitu) Medida de rendimiento que indica la proporción de predicciones correctas realizadas por un modelo sobre el total de predicciones realizadas ',
        },
        {
          id: 14,
          term: 'K-Fold cross validation',
          definition:
            'La validación cruzada de K-Fold evalúa el desempeño de modelos de aprendizaje automático. Permite estimar de forma confiable la capacidad de generalización de un modelo a nuevos datos.',
        },
        {
          id: 15,
          term: 'kernel function',
          definition:
            'una función kernel es una manera de transformar datos de un espacio de entrada a un espacio de mayor dimensionalidad. Esto permite que los datos que no son linealmente separables en el espacio original puedan ser separados de manera efectiva en un espacio de mayor dimensión donde la separación lineal sea posible.',
        },
        {
          id: 16,
          term: 'Entropy',
          definition:
            'desorden del dataset o cuantifica la impureza de un conjunto de datos ',
        },
        {
          id: 17,
          term: 'Coding',
          definition:
            'codificar, representación de datos categóricos o no numéricos en una forma numérica que la red neuronal puede entender y procesar ',
        },
        {
          id: 18,
          term: 'Split',
          definition:
            ' división acción de dividir el conjunto de datos en las partes de entrenamiento y prueba.',
        },
      ],
    };
  },
  computed: {
    allTerms() {
      return this.definitions.map((item) => item.term);
    },
  },
  methods: {
    onSearch() {
      if (this.allTerms.includes(this.searchTerm)) {
        this.$emit('term-selected', this.searchTerm);
      } else {
        this.snackbarMessage =
          'Lamentamos informarle que la palabra que estaba buscando no ha sido encontrada en nuestra base de datos actual. Sin embargo, queremos asegurarle que estamos en constante actualización y expansión de nuestros contenidos. Es posible que la palabra que necesita sea agregada en el futuro cercano.';
        this.snackbar = true;
      }
    },
    getDefinition(term) {
      const found = this.definitions.find((item) => item.term === term);
      return found ? found.definition : '';
    },
  },
};
</script>

<style scoped>
.pa-4 {
  padding: 1rem;
}
</style>
