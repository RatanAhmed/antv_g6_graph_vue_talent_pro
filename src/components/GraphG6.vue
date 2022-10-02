<script setup lang="ts">
import G6 from '@antv/g6';
const data = {
  // Node set
  nodes: [
      {
          id: 'node1', // Unique identification of the node
          x: 100, // Node abscissa
          y: 200, // Node ordinate
          label: 'starting point', // Node text
          size: 50, // Node size
          type: 'circle', //Specify the node type, built-in node type name or custom node name. The default is' circle '
          // Specifies the position of the connection point of the edge connection node (relative to the node), which can be empty.
          // For example: [0, 0] represents the anchor point in the upper left corner of the node, [1, 1] represents the anchor point in the lower right corner of the node
          anchorPoints: [],	
          //Style properties for nodes
          style: {    
              fill: '#00FFFF ', // node fill color
              stroke: '#FFFF00 ', // stroke color of node
              lineWidth: 5,       // Stroke Width  
              // ...  Other properties
          }, 
          //	Text configuration item
          labelCfg: {
              position: 'bottom', // The position of the text relative to the node
              offset: 10, // Offset of text
              style: {    // Style properties for labels.
                fill: 'red', // text color
              },
            },
      },
      {
          id: 'node2',
          x: 300,
          y: 200,
          label: 'Target point',
      },
  ],
  // Edge set
  edges: [
      // Represents an edge connected from node1 node to node2 node
      {
          source: 'node1', // Starting point id
          target: 'node2', // Target point id
          label: "I'm wired", // Edge text
          style: {
              stroke: '#000000',
              lineWidth: 5,
              // ...  Other style properties
            },
      },
  ],
};
const graph = new G6.Graph({
    container: 'mountNode', // Specify mount container
    width: 800, // Width of graph
    height: 500, // Height of graph
  });

  graph.data(data); // Load data
  graph.render(); // Render

</script>
  
<template>
  <div id="mountNode"></div>
</template>
  
<style scoped>

</style>
  