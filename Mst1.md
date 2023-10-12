## Q.1 Give complete steps of Finite elements Analysis applied to stress analysis problem.?

### SOLUTION

Step 1. Four noded isoparametric element is selected for the analysis. The four noded 
isoparametric element can take quadrilateral shape also as required for element 12, 15, 18, etc. As there 
is no bending of strip, only displacement continuity is to be ensured but not the slope continuity. Hence 
displacements of nodes in x and y directions are taken as basic unknown in the problem. 

Step 2. The portion to be analysis is to be discretised portion. For this 33 elements have been used. 
There are 48 nodes. At each unknowns are x and y components of displacements. Hence in this problem 
total unknowns to be determined are 48×2=96.

Step 3. The displacement of any point inside the element is approximately by suitable functions in terms 
of the nodal displacements of the element. For the typical element, displacement at P are
u = ∑ 𝑛𝑖𝑢𝑖 = N1 u1 + N2 u2 + N3 u3 + N4 u4 and v = ∑ 𝑛𝑖𝑢𝑖 = N1 v1 + N2 v2 + N3 v3 + N4 v4
The approximating functions Ni are called shape functions or interpolation functions. Usaually they are 
derived using polynomials. The methods of deriving these functions for various elements are discussed 
in this text in latter chapters.

Step 4. Now the stiffness characters and consistant loads are to be found for each element. There are 
four nodes and at each node degree of freedom is 2. Hence degree of freedom in each element is 
4×2=8. The relationship between the nodal displacements and nodal forces is called element stiffness 
characteristics. It is of the form [𝑘]𝑒
{𝛿}𝑒 = {𝐹}𝑒 as explained earlier. 
For the element under consideration, 𝑘𝑒
is 8 × 8 matrix and 𝛿𝑒𝑎𝑛𝑑 {𝐹}𝑒 are vectors of 8 values. In solid 
mechanics element stiffness matrix is assembled using variational approach i.e. by minimizing potential 
energy. If the load is acting in the body of element or on the surface of element, its equivalent at nodal 
points are to be found using variational approach, so that right hand side of the above expression is 
assembled. This process is called finding consistant loads.

Step 5. The structure is having 48×2=96 displacement and load vector components to be determined. 
Hence global stiffness equation is of the form 
[k] = 96 × 96 {𝛿} = 96 × 1 {𝐹} = 96 × 1 
Each element stiffness matrix is to be placed in the global stiffness matrix appropriately. This process is 
called assembling global stiffness matrix. In this problem force vector F is zero at all nodes except at 
nodes 45, 46, 47 and 48 in x direction. For the given loading nodal equivalent forces are found and the 
force vector F is assembled .

Step 6. In this problem, due to symmetry traverse displacements along AB and BC are zero. The system 
equation [𝑘]{𝛿} = {𝐹} is modify to see that the solution for {𝛿} comes out with the above values. This 
modification of system equation is called imposing the boundary conditions.

Step 7. The above 96 simultaneous equations are solved using the standard numerical procedures like 
Gauss elimination or Choleski’s decomposition techniques to get the 96 nodal displacement.

Step 8. Now the interest of the analyst is to study the stresses at various points. In solid mechanics the 
relationship between the displacements and stresses are well established. The stresses at various points 
of interest may be found by using shape function and the nodal displacements and then stresses calculated. The stress concentrated may be studies by comparing the values obtained at various points 
in the fillet zone with the values at uniform zone, far away from the fillet (which is equal to p/b2t).


## Q.2 What are the advantages and disadvantages of finite element method of structural analysis..??

### SOLUTION

### Advantages

1. Versatility : FEM can be applied to a wide range of engineering problems, including static and dynamic analyses, heat transfer, fluid flow, and electromagnetics. It is versatile and can handle complex geometries and material properties.

2. Flexibility : It can incorporate various types of boundary conditions, load, and material properties, making it suitable for modeling real-world 
scenarios.
3. Accuracy : FEM allows for accurate 
modelling of complex structures with 
high precision by dividing them into 
smaller finite element. The accuracy 
can be improved by increasing the 
mesh density.
4. Visualization : FEM provides detailed 
visualizations of stress, displacement, 
temperature, and other parameters,which can aid in understanding the 
structural behavior.
5. Optimization : FEM can be used for 
optimization studies to find the best 
design parameters while meeting 
safety and performance criteria.
6. Non linear analysis : FEM can handle 
nonlinearities in materials and 
geometry, making it suitable for 
analysis structures that undergo large 
deformations or material yielding.
7. Time-dependent problems: It can 
analyze dynamic and transient 
phenomena, such as vibrations, 
impact, and heat transfer over time.
8. Reduced cost : FEM can reduce the 
need for physical prototyping and 
testing, saving time and resources 
during the design phase.

### Disadvantages 
1. Complexity: setting up an FEM 
analysis requires expertise and can be 
time-consuming. Generating an 
appropriate mesh, selecting material 
properties, and defining boundary 
conditions can be challenging. 
2. Computational resources : FEM can 
be computationally intensive, 
especially for large and complex 
models, requiring powerfull hardware 
and significant processing time.
3. Assumption of linearity : linear FEM 
assumes that material behavior is 
linear elastic, which may not always 
be accurate for some materials and 
loading conditions. Non linear analysis 
can be more complex.
4. Mesh sensitivity : the accuracy of FEM 
results is highly dependent on the 
quality of the mesh. Poorely 
generated meshes can lead to 
inaccurate results
5. Model validation : Validating FEM 
results often requires experimental 
testing, which can be costly and timeconsuming.
6. Limited to discretization : FEM results 
often requires experimental testing, 
which can costly and time consuming.
7. Limited to discretization : FEM relies 
on discretizing the domain into finite 
elements, and the accuracy of the 
solution depends on the element size. 
Small elements increase 
computational cost, while large 
elements may results in less accurate 
results.
8. Numerical errors : FEM introduces 
numerical errors due to 
approximations made during the 
discretization process, which can 
affect the accuracy of results.
9. Software and training costs : 
specialized FEA software can be 
expensive, and users need training to 
effectively use these tools

