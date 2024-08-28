<script>
import { defineComponent, ref, onMounted, onBeforeUnmount } from 'vue';
import * as THREE from 'three';
import { STLLoader } from 'three/examples/jsm/loaders/STLLoader.js';

export default defineComponent({
  name: 'Scene',
  setup() {
    const sceneContainer = ref(null);
    let scene, camera, renderer, object;

    const initScene = () => {
      scene = new THREE.Scene();
      camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000);
      renderer = new THREE.WebGLRenderer({ antialias: true });
      renderer.setSize(window.innerWidth, window.innerHeight);
      sceneContainer.value.appendChild(renderer.domElement);

      const topLight = new THREE.DirectionalLight(0xF22F2F, 10);
      topLight.position.set(0, 1, 0.3);
      scene.add(topLight);

      const rightLight = new THREE.DirectionalLight(0x111E81, 7);
      rightLight.position.set(1, 0.4, 0.3);
      scene.add(rightLight);

      const leftLight = new THREE.DirectionalLight(0x111E81, 7);
      leftLight.position.set(-1, 0, 0.3);
      scene.add(leftLight);
      
      camera.position.set(0, 0, 1.5);
      camera.lookAt(scene.position);
    };

    const loadObject = () => {
      const loader = new STLLoader();
      loader.load(
        "./src/assets/Fighter.stl",
        (geometry) => {
          const material = new THREE.MeshStandardMaterial({
            color: 0xffffff,
            metalness: 1,
            roughness: 0.25,
            envMapIntensity: 1
          });
          object = new THREE.Mesh(geometry, material);
          object.rotation.x = -Math.PI / 2;
          object.rotation.z = -Math.PI / 2;
          object.rotation.z = 0.5;
          const checkIfMobile = () => {
            if (window.innerWidth <= 480) {
              return 1;
            } else if (window.innerWidth <= 768) {
              return 2;
            } else if (window.innerWidth <= 1140) {
              return 3;
            }
            return 0;
          }
          if (checkIfMobile()== 1) {
            object.scale.set(0.8, 0.8, 0.8);
          } 
          else if (checkIfMobile()== 2) {
            object.scale.set(1, 1, 1);
          }
          else {
            object.scale.set(1.3, 1.3, 1.3);
          }
          
          geometry.center();
          geometry.translate(0, 0, 0.05);
          geometry.computeBoundingBox();
          
          const height = geometry.boundingBox.max.y - geometry.boundingBox.min.y;
          object.position.y = height / 2 * 1.5;
          
          scene.add(object);
          animate();
          const handleResize = () => {
            camera.aspect = window.innerWidth / window.innerHeight;
            camera.updateProjectionMatrix();
            renderer.setSize(window.innerWidth, window.innerHeight);
          };
          window.addEventListener('resize', handleResize);
        },
      );
    };

    const animate = () => {
      requestAnimationFrame(animate);
      if (object) {
        object.rotation.z += 0.007;
      }
      renderer.render(scene, camera);
    };

    onMounted(() => {
      initScene();
      loadObject();
    });

    onBeforeUnmount(() => {
      window.removeEventListener('resize', handleResize);
    });

    return { sceneContainer };
  },
});
</script>

<template>
  <div ref="sceneContainer" class="scene-container"></div>
</template>

<style scoped>
.scene-container {
  width: 100%;
  height: 100vh;
}
</style>