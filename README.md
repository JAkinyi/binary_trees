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
## Search operation algorithm
	If root.data is equal to search.data
   		return root
	else
   		while data not found

      			If data is greater than node.data
         			goto right subtree
      			else
         			goto left subtree
         
      			If data found
         			return node
   		endwhile 
   
   		return data not found
   
	end if
	
## Search Operation implementation
	struct node* search(int data) {
   		struct node *current = root;
   		printf("Visiting elements: ");

   		while(current->data != data) {
      			if(current != NULL)
      				printf("%d ",current->data); 
      
      			//go to left tree

      			if(current->data > data) {
         			current = current->leftChild;
      				}
      			//else go to right tree
     			else {                
         			current = current->rightChild;
      				}

      			//not found
      			if(current == NULL) {
         			return NULL;
      				}
  		}
   		return current;
	}
