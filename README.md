# three.js.ssaoHack
fix ssao skinning problem

but you need create normal material for each object by yourself.

sample:

loader.load( 'models/gltf/Soldier.glb', function ( gltf ) {

  gltf.scene.traverse( function ( object ) {
  
						if ( object.material ) {
            
              //create normalMaterial
              
							object.normalMaterial = new THREE.MeshNormalMaterial( {
              
								morphTargets: object.material.morphTargets,
                
								skinning: object.material.skinning
                
							} );
              
							if (object.material.normalMap){
              
								object.normalMaterial.normalMap = object.material.normalMap;
                
							}
              
						}
            
						if ( object.isMesh){
							
						}
            
					} );

});

