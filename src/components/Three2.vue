<template>
  <div class="hello">
      <canvas id="mainCanvas" width="400px" height="300px" ></canvas>
  </div> 
</template>

<script>
 import * as THREE from "three";
export default {
  name: 'Three2',
  props: {
    msg: String
  },
  mounted(){
      //render 
      var render  = new THREE.WebGLRenderer({
          canvas:document.getElementById("mainCanvas")
      })

      render.setClearColor(0x000000) //black

      //scene
      var scene = new THREE.Scene();


      //camera
       var camera = new THREE.PerspectiveCamera(45, 4 / 3, 1, 1000);
       camera.position.set(0, 0, 5);
       scene.add(camera);
    //   scene.add(camera)

      //a cube in the scene
      var cube  = new THREE.Mesh(new THREE.CubeGeometry(1,2,3),
          new THREE.MeshBasicMaterial({
            //   wireframe: true,
              color:0xfff
        }))
        scene.add(cube)

        render.render(scene,camera)
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    
</style>
