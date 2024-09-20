### Spring and Bar Elements in Finite Element Method (FEM)

#### **Introduction**

In the Finite Element Method (FEM), **spring and bar elements** are among the simplest types of elements used to introduce students and engineers to the fundamental concepts of FEM. Both elements exhibit axial deformations and help in understanding key concepts like **stiffness matrix formulation**, **equilibrium equations**, and **assembly of the global stiffness matrix**.

- **Spring Element**: Represents mechanical springs and is used to study systems where displacements and forces are related linearly by a stiffness constant.
- **Bar Element**: Represents structural members subjected to axial forces (tension or compression) with no bending or shear, such as truss elements. It is often referred to as a "truss element."

#### **Applications**

- **Spring Elements**: Found in mechanical systems like suspension systems, car springs, and spring-loaded mechanisms.
- **Bar Elements**: Common in civil and structural engineering applications like trusses, cables, bridges, and towers, where members primarily experience axial forces.

#### **Spring Element**

##### 1. **Governing Principle**
A spring follows **Hooke's Law**, which states that the force in a spring is proportional to its displacement:
\[
F = k \Delta u
\]
Where:
- \( F \) is the force,
- \( k \) is the spring stiffness (constant),
- \( \Delta u \) is the displacement.

##### 2. **Derivation of the Stiffness Matrix**

For a simple spring with two nodes (Node 1 and Node 2) and stiffness \( k \), the relationship between the forces at the nodes and their displacements can be expressed as:
\[
F_1 = k (u_1 - u_2)
\]
\[
F_2 = k (u_2 - u_1)
\]
In matrix form, this becomes:
\[
\begin{bmatrix} F_1 \\ F_2 \end{bmatrix} = 
\begin{bmatrix} k & -k \\ -k & k \end{bmatrix}
\begin{bmatrix} u_1 \\ u_2 \end{bmatrix}
\]
Thus, the stiffness matrix for a spring element is:
\[
\mathbf{K}_{spring} = \begin{bmatrix} k & -k \\ -k & k \end{bmatrix}
\]
This matrix describes the relationship between nodal forces and displacements for the spring element.

##### 3. **Procedure to Apply in a Real Situation**

1. **Model the System**: 
   Identify all the springs and assign their stiffness values. Define the connections between nodes (where springs are attached).
   
2. **Form the Element Stiffness Matrix**: 
   For each spring, use the derived stiffness matrix.

3. **Assemble the Global Stiffness Matrix**: 
   Assemble the individual stiffness matrices into a global matrix representing the entire system of springs.

4. **Apply Boundary Conditions**: 
   Specify fixed nodes or known displacements, ensuring the system is stable.

5. **Solve the System**: 
   Use the global stiffness matrix and known forces/displacements to solve for the unknown displacements or forces at each node.

---

#### **Bar (Truss) Element**

##### 1. **Governing Principle**
The bar (or truss) element follows axial deformation. The force-displacement relationship in the bar element is derived using **Hooke's Law** and the **direct stiffness method**. The axial force \( F \) in the bar is related to the displacement through the axial stiffness:
\[
F = EA \frac{\Delta L}{L}
\]
Where:
- \( E \) is Young's modulus (material property),
- \( A \) is the cross-sectional area,
- \( L \) is the original length of the bar,
- \( \Delta L \) is the change in length (displacement difference between nodes).

##### 2. **Derivation of the Stiffness Matrix**

Consider a bar element connecting two nodes (Node 1 and Node 2) in one-dimensional space.

1. **Axial displacement** between the two nodes is given by:
\[
\Delta u = u_2 - u_1
\]
2. The internal force generated in the element is:
\[
F = EA \frac{u_2 - u_1}{L}
\]
3. Relating forces at the two nodes:
\[
F_1 = EA \frac{u_1 - u_2}{L}
\]
\[
F_2 = EA \frac{u_2 - u_1}{L}
\]
In matrix form, this becomes:
\[
\begin{bmatrix} F_1 \\ F_2 \end{bmatrix} = \frac{EA}{L}
\begin{bmatrix} 1 & -1 \\ -1 & 1 \end{bmatrix}
\begin{bmatrix} u_1 \\ u_2 \end{bmatrix}
\]
Thus, the stiffness matrix for the bar element is:
\[
\mathbf{K}_{bar} = \frac{EA}{L} \begin{bmatrix} 1 & -1 \\ -1 & 1 \end{bmatrix}
\]
Where:
- \( \frac{EA}{L} \) is the axial stiffness of the bar element.

##### 3. **Procedure to Apply in a Real Situation**

1. **Model the Structure**:
   Identify all the bar elements, their material properties (Young’s modulus \( E \) and cross-sectional area \( A \)), and their lengths \( L \).

2. **Form the Element Stiffness Matrix**:
   For each bar element, use the derived stiffness matrix based on \( EA/L \).

3. **Transformation of Coordinates (if needed)**:
   If the bars are in 2D or 3D space, a transformation matrix is required to account for the element’s orientation.

   The stiffness matrix in the global coordinate system becomes:
   \[
   \mathbf{K}_{global} = \mathbf{T}^T \mathbf{K}_{local} \mathbf{T}
   \]
   Where \( \mathbf{T} \) is the transformation matrix derived from the geometry of the bar element.

4. **Assemble the Global Stiffness Matrix**:
   Combine the stiffness matrices of all bar elements into a global matrix that represents the entire truss structure.

5. **Apply Boundary Conditions**:
   Specify known displacements or fixed nodes, ensuring the system is stable and well-defined.

6. **Solve the System**:
   Use the global stiffness matrix and applied loads to solve for the unknown displacements at each node.

7. **Post-Processing**:
   Once displacements are known, calculate the forces in each bar using the force-displacement relationship \( F = K u \).

##### Example Application: Truss Analysis

Consider a simple two-bar truss structure with a load applied at a joint.

1. **Model**: The truss consists of two bar elements with known material properties (\( E \), \( A \)) and geometry (lengths \( L_1 \), \( L_2 \)).
   
2. **Element Stiffness Matrices**: 
   Calculate the stiffness matrices for both elements based on the formula \( \mathbf{K}_{bar} = \frac{EA}{L} \begin{bmatrix} 1 & -1 \\ -1 & 1 \end{bmatrix} \).

3. **Global Stiffness Matrix**: 
   Assemble the stiffness matrices into a global matrix. Apply transformation matrices if the bars are not aligned with the global coordinate axes.

4. **Boundary Conditions**: 
   Fix one or more nodes to prevent rigid body motion. Apply known external forces or displacements.

5. **Solve**: 
   Solve for the unknown nodal displacements using the global stiffness matrix and boundary conditions.

6. **Post-Processing**: 
   Calculate the forces in each bar element and check whether they are in tension or compression.
