# Group Project on binary trees
## Code to write a tree node
      struct node {
         int data;   
         struct node *leftChild;
         struct node *rightChild;
      };
## Insert Operation Algorithm
      If root is NULL 
             then create root node
      return

      If root exists then
            compare the data with node.data
   
      while until insertion position is located

            If data is greater than node.data
                  goto right subtree
            else
                  goto left subtree

      endwhile 
   
      insert data
	
      end If 
