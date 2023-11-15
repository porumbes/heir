# heir
Construct a simple mesh hierarchy:
- duplicate the mesh and maintain a one-to-one correspondence between a vertex on the original mesh level and the duplicate
- choose an approximate set of independent vertices
- collapse a vertex edge towards that vertex's one ring
- map the original vertex to a new triangle on the simplified mesh

Compile:
- git clone
- mkdir build; cd build
- cmake ..