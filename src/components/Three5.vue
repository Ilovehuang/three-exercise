<template>
  <div class="hello">

  </div> 
</template>

<script>
import * as THREE from "three";

export default {
  name: 'Three5',
  props: {
    msg: String
  },
  mounted(){
      var renderer = new THREE.WebGLRenderer({
                    canvas: document.getElementById('mainCanvas')
                });
      renderer.setClearColor(0x000000);
      var scene = new THREE.Scene();

      // camera
      var camera = new THREE.OrthographicCamera(-5, 5, 3.75, -3.75, 0.1, 100);
      camera.position.set(25, 25, 25);
      camera.lookAt(new THREE.Vector3(0, 0, 0));
      scene.add(camera);
  },
  methods:{
      drawAxes(scene){
          var xGeo = new THREE.Geometry()
          xGeo.vertices.push(new THREE.Vector3(0,0,0))
          xGeo.vertices.push(new THREE.Vector3(3,0,0));

          var xMat = new THREE.LineBasicMaterial({
              color:0xff000000
          })

          var yAxis  = new THREE.Line(xGeo,xMat);
           scene.add(yAxis);

           //z-axis
           var zGeo = new THREE.Geometry();
           zGeo.vertices.push(new THREE.Vector3(0,0,0))
           zGeo.vertices.push(new THREE.Vector3(0, 0, 3));

           var zMat = new THREE.LineBasicMaterial({
                    color: 0x00ccff
            });
           var zAxis = new THREE.Line(zGeo, zMat);
           scene.add(zAxis);
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
