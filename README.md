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
## Insert Operation implementation
	void insert(int data) {
   		struct node *tempNode = (struct node*) malloc(sizeof(struct node));
   		struct node *current;
   		struct node *parent;

   		tempNode->data = data;
   		tempNode->leftChild = NULL;
   		tempNode->rightChild = NULL;

   	//if tree is empty, create root node
   	if(root == NULL) {
      		root = tempNode;
   	} else {
      		current = root;
      		parent  = NULL;

      	while(1) {                
         	parent = current;

         	//go to left of the tree
         	if(data < parent->data) {
            		current = current->leftChild;                
            
            		//insert to the left
            		if(current == NULL) {
               		parent->leftChild = tempNode;
               		return;
            		}
         	}
			
         	//go to right of the tree
         	else {
            		current = current->rightChild;
            
            		//insert to the right
            		if(current == NULL) {
               			parent->rightChild = tempNode;
               			return;
            			}
         		}
      		}            
   		}
	}
