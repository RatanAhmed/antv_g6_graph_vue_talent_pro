<template>
  <div id="container"></div>
</template>

<script setup lang="ts">
  import { defineComponent, onMounted } from 'vue'
  import G6, { GraphData, TreeGraphData } from "@antv/g6";
  import insertCss from "insert-css";
  import data from "../options/index";

  onMounted(() => {
    g6(data)
  })
  
  const g6 = (data: GraphData | TreeGraphData | undefined) => {

    const graph = new G6.Graph({
      container: 'container', // Specify mount container
      width: 800, // Width of graph
      height: 500, // Height of graph
      
      // Default node set
      defaultNode: {
        shape: "circle",
        size: [30],
        color: "#5B8FF9",
        style: {
          fill: "#9EC9FF",
          lineWidth: 3
        },
        labelCfg: {
          style: {
            fill: "#fff",
            fontSize: 20
          }
        }
      },
      // Default edge set
      defaultEdge: {
        style: {
          stroke: "#e2e2e2"
        }
      }
    });
    // Data loading and rendering of Graphs
    graph.data(data);
    graph.render();
  }
  
  </script>
  
  <style lang="scss" scoped>
  </style>