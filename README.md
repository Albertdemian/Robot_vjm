# Robot_vjm

This repo is a matlab implementation of virtual joint model approach for the tripteron manipulator 

#File "task" is the main file in this library 

any function that needs a flag, it's either 'x' , 'y' or 'z' as each sub chain works in a different plane 
      this flag is to specify which one you need
      
here a name list of each function and its purpose: 

- Inverse_kin_trip:
      calculates the inverse kinematics of a chain in the manipulator
      
      inputs: (x,y,z) in a structure of .x , .y , .z 
              link length
              boundary of work space 
              flag: 'x' , 'y' or 'z' 
      returns: array of three angles [q1, q2, q3]
      
- Rdx, Rdy, Rdz, Tdx, Tdy, Tdz : derivative of basic transformation matrices 

- Rx, Ry, Rz, Tx, Ty, Tz : basic transformation matrices 

- elastic_fk : calculaties forward kinematics while counting for deflection of (theta)
        inputs: array   of passive joints angles
                array of vertual joints coordinates
                base transformation 
                flag 
                
         returns: a structure of all intermediate transformations; t01, t12, t23, t_sp1, t_sp2 

- forward_kin : calculates rigid forward kinematics 
              inputs: array of angles for passive joints
                      structure of bases transformations 
                      flag to indicate which sub chain you're counting for 
                      
              returns: structure of all intermediate rotations 
                       structure of all intermediate position vectors 
                       homogenous transformation matrix of forward kinematics in global frame

- get_leg_position: takes (x,y,z) and bounding limit of work space 
                     returns a structure of local position to be used in inverse kinematics
                     
-graph bounds: to graph work space 

- graph_manipulator: to graph robot manipulator at a position 

- Jacobian_q1, Jacobian_q2, jacobian_q3 to calculate jacobian vectors for each of these angles 

- jacobian_t : calculates the jacobian matrix for all virtual joints 

- transform to base: returs homogenous transformation of each robot sub chain


