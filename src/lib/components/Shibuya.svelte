<script lang="ts">
  import { T, useGLTF } from '@threlte/core'

  const gltf = useGLTF('/models/shibuya.glb')
</script>

{#await gltf}
  <p>Loading...</p>
{:then model}
  <T.Primitive object={model.scene} />
{/await}
