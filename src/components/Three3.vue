<template>
  <div class="hello">
    <canvas id="mainCanvas" width="400px" height="300px" ></canvas>
  </div> 
</template>

<script>
 import * as THREE from "three";
export default {
  name: 'Three3',
  props: {
    msg: String
  },
  mounted(){
    var render = new THREE.WebGLRenderer({
      canvas:document.getElementById('mainCanvas')
    })

    render.setClearColor(0x000000)
    var scene = new THREE.Scene()

    //camera
    var camera = new THREE.OrthographicCamera(-1,1,1,-1, 1, 10);
    camera.position.set(0,0,5)

    scene.add(camera);

    //a cube in the scene

    var cube = new THREE.Mesh(new THREE.CubeGeometry(1,1,1),
          new THREE.MeshBasicMaterial({
            color:0xff0000,
            // wireframe:true
          }))
    scene.add(cube)

    render.render(scene,camera)
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    
</style>
