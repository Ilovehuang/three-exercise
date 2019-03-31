<template>
  <div class="hello">

  </div>
</template>

<script>
 import * as THREE from "three";

export default {
  name: 'Scene',
  props: {
    msg: String
  },
  created(){
           var scene = new THREE.Scene();
			var camera = new THREE.PerspectiveCamera( 60, window.innerWidth/window.innerHeight, 0.1, 1000 );
            // var control  = new THREE.OrbitControls
			var renderer = new THREE.WebGLRenderer({
                alpha: true
            });
			renderer.setSize( window.innerWidth, window.innerHeight,false);
			document.body.appendChild( renderer.domElement );

			var geometry = new THREE.BoxGeometry( 3, 1, 2 );
			var material = new THREE.MeshBasicMaterial( { color: 0xfff } );
			var cube = new THREE.Mesh( geometry, material );
			scene.add( cube );

			camera.position.z = 6;

			var animate = function () {
				requestAnimationFrame( animate );

				cube.rotation.x += 0.01;
				cube.rotation.y += 0.01;

				renderer.render( scene, camera );
			};

			animate();
  }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
