<template>
  <div class="hello">
    
  </div>
</template>

<script>
 import * as THREE from "three";
export default {
  name: 'DrawingLine',
  props: {
    msg: String
  },
  created(){
      
      //加载器
      var render = new THREE.WebGLRenderer();
      render.setSize(window.innerWidth,window.innerHeight)

      document.body.appendChild(render.domElement)

      //添加摄像头,
      var camera = new THREE.PerspectiveCamera(45,window.innerWidth/window.innerHeight,1,1500)

      camera.position.set(0,0,100);

      camera.lookAt(0,0,0)

      var scene = new THREE.Scene()

      var material = new THREE.LineBasicMaterial({color:0xfff})


      var geometry  = new THREE.Geometry();
      geometry.vertices.push(new THREE.Vector3(10,0,0));
      geometry.vertices.push(new THREE.Vector3( 0, 10, 0) );
    //   geometry.vertices.push(new THREE.Vector3( 10, 0, 0) );


      var line = new THREE.Line(geometry,material)

      scene.add(line)

      render.render(scene,camera)
    
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
