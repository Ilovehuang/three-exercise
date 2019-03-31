<template>
  <div class="hello">
      <canvas id="mainCanvas" width="400px" height="300px" ></canvas>
  </div> 
</template>

<script>
 import * as THREE from "three";
export default {
  name: 'Three1',
  props: {
    msg: String
  },
  mounted(){
      var render   = new THREE.WebGLRenderer({
          canvas:document.getElementById('mainCanvas')
      })

      render.setClearColor(0x000000) //black

      var scene = new THREE.Scene();

      var camera = new THREE.PerspectiveCamera(45,4/3,1,1000);
      camera.position.set(0,0,5)
      camera.lookAt(new THREE.Vector3(0,0,0))
      scene.add(camera)



      //材料
      var material = new THREE.MeshBasicMaterial({
          color:0xffffff, // white
          wireframe:true
      })

      //plane
      var planeGeo = new THREE.PlaneGeometry(1.5,1.5)
      var plane = new THREE.Mesh(planeGeo,material)
      plane.position.x = 1
      scene.add(plane)

      //triangle
      var triGeo = new THREE.Geometry
      triGeo.vertices = [new THREE.Vector3(0, -0.8, 0),
                        new THREE.Vector3(-2, -0.8, 0), new THREE.Vector3(-1, 0.8, 0)];
      triGeo.faces.push(new THREE.Face3(0,2, 1));
      var triangle = new THREE.Mesh(triGeo, material);
      scene.add(triangle);

      render.render(scene, camera);
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
