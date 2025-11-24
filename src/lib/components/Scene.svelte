<script lang="ts">
  import { T } from '@threlte/core'
  import { ContactShadows, Grid, OrbitControls } from '@threlte/extras'
  import Shibuya from './models/shibuya.svelte'
  import Tree from './models/tree.svelte'
  import Human from './models/human.svelte'
  import House from './models/house.svelte'
</script>

<T.PerspectiveCamera
  makeDefault
  position={[-10, 10, 10]}
  fov={15}
>
  <OrbitControls
    autoRotate
    enableZoom={false}
    enableDamping
    autoRotateSpeed={0.5}
    target.y={1.5}
  />
</T.PerspectiveCamera>

<T.DirectionalLight
  intensity={0.8}
  position.x={5}
  position.y={10}
/>
<T.AmbientLight intensity={0.2} />

<Grid
  position.y={-0.001}
  cellColor="#ffffff"
  sectionColor="#ffffff"
  sectionThickness={0}
  fadeDistance={25}
  cellSize={2}
/>

<ContactShadows
  scale={10}
  blur={2}
  far={2.5}
  opacity={0.5}
/>

<Shibuya />
<Tree position={[3, 0, 0]} />
<Human position={[-3, 0, 0]} />
<House position={[0, 0, 3]} />
