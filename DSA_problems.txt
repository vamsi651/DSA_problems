#STACK
#1
class stack:
    def __init__(self,size):
        self.size = size
        self.box = [0]*self.size
        self.top = -1
    def push(self,data):
        if self.top+1 == self.size:
            print("overflow")
            return
        self.top+=1
        self.box[ self.top ] = data
    def display(self):
        if self.top == -1:
            print("underflow")
            return
        for i in range(self.top,-1,-1):
            print(self.box[i],end=" ")
    def pop(self):
        if self.top == -1:
            print("underflow")
            return
        self.top-=1
    def peek(self):
        if self.top == -1:
            print("underflow")
            return
        print(self.box[self.top])
stack1 = stack(3)
stack1.push(18)
stack1.push(7)
stack1.display()
stack1.pop()
stack1.pop()
print()
stack1.display()
#2
class stack:
    def __init__(self):
        self.box = []
    def push(self,data):
        self.box.append(data)
    def display(self):
        if len(self.box)==0:
            print("empty")
            return
        for i in self.box[::-1]:
            print(i,end=" ")
    def pop(self):
        if len(self.box) == 0:
            print("empty")
            return
        self.box.pop()
    def peek(self):
        if len(self.box) == 0:
            print("empty")
            return
        print(self.box[-1])
stack1 = stack()
stack1.push(18)
stack1.push(7)
stack1.display()
stack1.pop()
stack1.pop()
print()
stack1.display()
#3 QUEUE:
class Queue:
    def __init__(self):
        self.queue = []
    def enqueue(self,data):
        self.queue.append(data)
    def display(self):
        if len(self.queue)==0:
            print("empty")
            return
        for i in self.queue:
            print(i,end=" ")
    def dequeue(self):
        if len(self.queue) == 0:
            print("empty")
            return
        self.queue.pop(0)
    def front(self):
        if len(self.queue) == 0:
            print("empty")
            return
        print(self.queue[0])
obj = Queue()
obj.enqueue(18)
obj.enqueue(7)
obj.display()
obj.dequeue()
print()
obj.display()
#4 DOUBLE-ENDED QUEUE:
class Queue:
    def __init__(self,size):
        self.size = size
        self.front=self.rear = -1
        self.queue = [0]*self.size
    def enqueue(self,data):
        if self.rear == -1:
            self.front=self.rear=0
            self.queue[self.rear]=data
            return
        if self.rear+1 == self.size:
            print("is_full")
            return
        self.rear+=1
        self.queue[self.rear] = data
    def display(self):
        if self.front == -1 or self.front > self.rear:
            print("empty")
            return
        for i in range(self.front , self.rear+1):
            print(self.queue[i],end=" ")
    def dequeue(self):
        if self.front ==-1 or self.front>self.rear:
            print("empty")
            return
        self.front+=1
    def front1(self):
        if self.front == -1 or self.front > self.rear:
            print("empty")
            return
        print(self.queue[self.front])
obj = Queue(3)
obj.enqueue(18)
obj.enqueue(7)
obj.display()
obj.dequeue()
print()
obj.display()
#5 LINKED-LIST:
class Node:
    def __init__(self,data):
        self.data=data
        self.next = None
class Linked_list:
    def __init__(self):
        self.head=None
    def b_insert(self,data):
        newnode = Node(data)
        newnode.next = self.head
        self.head = newnode
    def e_insert(self,data):
        newnode = Node(data)
        if self.head is None:
            self.head = newnode
            return
        cur = self.head
        while cur.next:
            cur = cur.next
        cur.next = newnode
    def display(self):
        if self.head is None:
            print("empty")
            return
        cur = self.head
        while cur:
            print(cur.data,end="->")
            cur = cur.next
obj = Linked_list()
obj.b_insert(8)
obj.b_insert(10)
obj.b_insert(21)
obj.e_insert(36)
obj.display()
#6 LinkedList
class Node:
    def _init_(self,data):
        self.data=data
        self.next = None
class Linked_list:
    def _init_(self):
        self.head=None
    def b_insert(self,data):
        newnode = Node(data)
        newnode.next = self.head
        self.head = newnode
    def e_insert(self,data):
        newnode = Node(data)
        if self.head is None:
            self.head = newnode
            return
        cur = self.head
        while cur.next:
            cur = cur.next
        cur.next = newnode
    def display(self):
        if self.head is None:
            print("empty")
            return
        cur = self.head
        while cur:
            print(cur.data,end="->")
            cur = cur.next
    def e_delete(self):
        if self.head is None or self.head.next==None:
            self.head=None
            return
        cur=self.head
        while  cur.next.next:
            cur=cur.next
        cur.next=None
        
obj = Linked_list()
obj.b_insert(8)
obj.b_insert(10)
obj.b_insert(21)
obj.e_insert(36)
obj.e_delete()
obj.e_delete()
obj.e_delete()
obj.display()
#7 LinkedList deletion at begin
class Node:
    def _init_(self,data):
        self.data=data
        self.next = None
class Linked_list:
    def _init_(self):
        self.head=None
    def b_insert(self,data):
        newnode = Node(data)
        newnode.next = self.head
        self.head = newnode
    def e_insert(self,data):
        newnode = Node(data)
        if self.head is None:
            self.head = newnode
            return
        cur = self.head
        while cur.next:
            cur = cur.next
        cur.next = newnode
    def display(self):
        if self.head is None:
            print("empty")
            return
        cur = self.head
        while cur:
            print(cur.data,end="->")
            cur = cur.next
    def e_delete(self):
        if self.head is None or self.head.next==None:
            self.head=None
            return
        cur=self.head
        while  cur.next.next:
            cur=cur.next
        cur.next=None
    def b_delete(self):
        if self.head:
            self.head=self.head.next      
obj = Linked_list()
obj.b_insert(8)
obj.b_insert(10)
obj.e_insert(36)
obj.display()
print()
obj.b_delete()
obj.display()
#8
class Node:
    def __init__(self,data):
        self.data = data
        self.next = None
        self.prev = None

class Double_linkedlist:
    def __init__(self):
        self.head=self.tail=None

    def b_insert(self,data):
        newnode = Node(data)
        if self.head is None:
            self.head =self.tail= newnode
            return
        newnode.next = self.head
        self.head.prev = newnode
        self.head = newnode

    def e_insert(self,data):
        newnode = Node(data)
        if self.head is None:
            self.head =self.tail= newnode
            return
        newnode.prev = self.tail
        self.tail.next = newnode
        self.tail = newnode

    def forward_display(self):
        if self.head is None:
            print("empty")
            return
        cur = self.head
        while cur:
            print(cur.data,end="->")
            cur = cur.next

    def backward_display(self):
        if self.head is None:
            print("empty")
            return
        cur = self.tail
        while cur:
            print(cur.data, end="->")
            cur = cur.prev
    def b_delete(self):
        if self.head == self.tail:
            self.head = self.tail =None
        if self.head:
            self.head = self.head.next
            self.head.prev=None

    def e_delete(self):
        if self.head == self.tail:
            self.head = self.tail =None
        if self.tail:
            self.tail = self.tail.prev
            self.tail.next = None

    def position(self,pos):
        cur = self.head
        for i in range(pos-1):
            if cur.next is None:
                break
            cur = cur.next
        else: return cur


    def position_insert(self,data,pos):
        if pos == 1:
            self.b_insert(data)
            return
        cur = self.position(pos)
        # if cur == self.tail:
        #     self.e_insert(data)
        #     return
        newnode = Node(data)
        if cur:
            newnode.next = cur
            newnode.prev = cur.prev
            cur.prev = newnode.prev.next = newnode

    def position_delete(self, pos):
        if pos == 1:
            self.b_delete()
            return
        cur = self.position(pos)
        if cur == self.tail:
            self.e_delete()
            return
        if cur:
            cur.next.prev = cur.prev
            cur.prev.next = cur.next
            cur.prev=cur.next=None


obj = Double_linkedlist()
obj.e_insert(6)
obj.e_insert(10)
obj.e_insert(30)
obj.b_insert(5)
obj.forward_display()
print()
obj.backward_display()
obj.position_delete(2)
print()
obj.forward_display()
print()
obj.backward_display()
#9
class Node:
    def __init__(self,data):
        self.data=data
        self.next = None



class Linked_list:
    def __init__(self):
        self.head=None

    def b_insert(self,data):
        newnode = Node(data)
        newnode.next = self.head
        self.head = newnode

    def e_insert(self,data):
        newnode = Node(data)
        if self.head is None:
            self.head = newnode
            return
        cur = self.head
        while cur.next:
            cur = cur.next
        cur.next = newnode


    def e_delete(self):
        if self.head is None or self.head.next is None:
            self.head = None
            return
        cur = self.head
        while cur.next.next:
            cur = cur.next
        cur.next = None


    def b_delete(self):
        if self.head:
            self.head = self.head.next

    def pos_delete(self,pos):
        if pos == 1:
            self.b_delete()
            return
        cur = self.position(pos - 1)
        if cur and cur.next:
            cur.next = cur.next.next
        else:
            print("position not found")


    def position(self,pos):
        if pos<=0:
            print("invalid position")
            return

        cur = self.head
        for i in range(pos-1):
            if cur.next==None:
                break
            cur = cur.next
        else: return cur
    def display(self):
        if self.head is None:
            print("empty")
            return
        cur = self.head
        while cur:
            print(cur.data,end="->")
            cur = cur.next

    def pos_insert(self,data,pos):
        if pos == 1:
            self.b_insert(data)
            return
        newnode = Node(data)
        cur = self.position(pos-1)
        if cur:
            newnode.next = cur.next
            cur.next = newnode
        else: print("position not found")

obj = Linked_list()
obj.b_insert(10)
obj.e_insert(8)
obj.e_insert(36)
obj.display()
print()
obj.pos_delete(4)
obj.display()
#10
class Node:
    def __init__(self,data):
        self.data=data
        self.next = None

class Linked_list:
    def __init__(self):
        self.head=None

    def b_insert(self,data):
        newnode = Node(data)
        newnode.next = self.head
        self.head = newnode

    def e_insert(self,data):
        newnode = Node(data)
        if self.head is None:
            self.head = newnode
            return
        cur = self.head
        while cur.next:
            cur = cur.next
        cur.next = newnode


    def e_delete(self):
        if self.head is None or self.head.next is None:
            self.head = None
            return
        cur = self.head
        while cur.next.next:
            cur = cur.next
        cur.next = None


    def b_delete(self):
        if self.head:
            self.head = self.head.next

    def position(self,pos):
        if pos<=0:
            print("invalid position")
            return
        cur = self.head
        for i in range(pos-1):
            if cur.next==None:
                break
            cur = cur.next
        else: return cur
    def display(self):
        if self.head is None:
            print("empty")
            return
        cur = self.head
        while cur:
            print(cur.data,end="->")
            cur = cur.next

    def pos_insert(self,data,pos):
        if pos == 1:
            self.b_insert(data)
            return
        newnode = Node(data)
        cur = self.position(pos-1)
        if cur:
            newnode.next = cur.next
            cur.next = newnode
        else: print("position not found")

obj = Linked_list()

obj.b_insert(10)
obj.e_insert(8)
obj.e_insert(36)
obj.display()
print()
obj.pos_insert(17,4)
obj.display()
#11
class Node:
    def __init__(self,data):
        self.data=data
        self.next = None
class Linked_list:
    def __init__(self):
        self.head=None

    def e_insert(self,data):
        newnode = Node(data)
        if self.head is None:
            self.head = newnode
            return
        cur = self.head
        while cur.next:
            cur = cur.next
        cur.next = newnode
    def remove_dup(self):
        cur = self.head
        while cur and cur.next:
            if cur.data == cur.next.data:
                cur.next = cur.next.next
            cur = cur.next
    def display(self):
        if self.head is None:
            print("empty")
            return
        cur = self.head
        while cur:
            print(cur.data,end="->")
            cur = cur.next
t = int(input())
obj= [0]*t
for i in range(t):
    obj[i] = Linked_list()
    n = int(input())
    a = list(map(int,input().split(" ")))
    for j in range(n):
        obj[i].e_insert(a[j])
    obj[i].remove_dup()
for k in obj:
    k.display()
    print()
#TREE:
#12 inorder traversal
class Node:
    def __init__(self,data):
        self.data=data
        self.left=self.right=None
def inorder_traversal(root):
    if root is None:
        return
    inorder_traversal(root.left)
    print(root.data)
    inorder_traversal(root.right)
root=Node(5)
root.left=Node(6)
root.right=Node(12)
root.left.left=Node(10)
root.left.right=Node(33)
root.left.left.left=Node(56)
root.right.right=Node(3)
inorder_traversal(root)
#13 preorder traversal
class Node:
    def __init__(self,data):
        self.data=data
        self.left=self.right=None
def inorder_traversal(root):
    if root is None:
        return
    print(root.data)
    inorder_traversal(root.left)
    inorder_traversal(root.right)
root=Node(5)
root.left=Node(6)
root.right=Node(12)
root.left.left=Node(10)
root.left.right=Node(33)
root.left.left.left=Node(56)
root.right.right=Node(3)
inorder_traversal(root)
#14 postorder traversal
class Node:
    def __init__(self,data):
        self.data=data
        self.left=self.right=None
def inorder_traversal(root):
    if root is None:
        return
    inorder_traversal(root.left)
    inorder_traversal(root.right)
    print(root.data)
root=Node(5)
root.left=Node(6)
root.right=Node(12)
root.left.left=Node(10)
root.left.right=Node(33)
root.left.left.left=Node(56)
root.right.right=Node(3)
inorder_traversal(root)
#15 
class Node:
    def __init__(self,data):
        self.data=data     #data for the node 
        self.left=None     #value stored in left side
        self.right=None    #value stored in right side
        
class binary_tree:  #new class created
    
        
    def inorder_traversal(self,root):
        if root is None:
            return
        self.inorder_traversal(root.left)
        print(root.data,end=" ")
        self.inorder_traversal(root.right)

    def height(self,root):  #finding height of the tree
        if root is None or root.left is None and root.right is None:
            return 0
        l_count=1+self.height(root.left)
        r_count=1+self.height(root.right)
        return l_count if l_count>r_count else r_count    

root=Node(5)
root.left=Node(6)
root.right=Node(12)
root.right.right=Node(3)
root.left.left=Node(10)
root.left.right=Node(33)
root.left.left.left=Node(56)
obj=binary_tree()
obj.inorder_traversal(root)
print()
print(obj.height(root)) 
#16
class Node:
    def __init__(self,data):
        self.data =data
        self.left=None
        self.right=None
class bst:
    def __init__(self):
        self.root = None
    def insert(self,data):
        self.root = self.rec_insert(self.root,data)
    def rec_insert(self,root,data):
        if root is None:
            return Node(data)
        if root.data >data:
            root.left = self.rec_insert(root.left,data)
        else:
            root.right = self.rec_insert(root.right,data)
        return root
    def inorder(self):
        def rec_inorder(root):
            if root:
                rec_inorder(root.left)
                print(root.data,end=" ")
                rec_inorder(root.right)
        rec_inorder(self.root)
obj = bst()
obj.insert(25)
obj.insert(63)
obj.insert(72)
obj.insert(22)
obj.insert(35)
obj.insert(17)
obj.inorder()
#17 height of bst
class Node:
    def __init__(self,data):
        self.data =data
        self.left=None
        self.right=None
class bst:
    def __init__(self):
        self.root = None
    def insert(self,data):
        self.root = self.rec_insert(self.root,data)
    def rec_insert(self,root,data):
        if root is None:
            return Node(data)
        if root.data >data:
            root.left = self.rec_insert(root.left,data)
        else:
            root.right = self.rec_insert(root.right,data)
        return root
    def inorder(self):
        def rec_inorder(root):
            if root:
                rec_inorder(root.left)
                print(root.data,end=" ")
                rec_inorder(root.right)
        rec_inorder(self.root)
    def count(self,root):
        if not root:
            return 0
        return 1+self.count(root.left)+self.count(root.right)
obj = bst()
obj.insert(25)
obj.insert(63)
obj.insert(72)
obj.insert(22)
obj.insert(35)
obj.insert(17)
obj.inorder()
print(obj.count(obj.root))
#18 height of tree by using max func
class Node:
    def __init__(self,data):
        self.data =data
        self.left=None
        self.right=None
class bst:
    def __init__(self):
        self.root = None
    def insert(self,data):
        self.root = self.rec_insert(self.root,data)
    def rec_insert(self,root,data):
        if root is None:
            return Node(data)
        if root.data >data:
            root.left = self.rec_insert(root.left,data)
        else:
            root.right = self.rec_insert(root.right,data)
        return root
    def inorder(self):
        def rec_inorder(root):
            if root:
                rec_inorder(root.left)
                print(root.data,end=" ")
                rec_inorder(root.right)
        rec_inorder(self.root)
    def count(self,root):
        if not root:
            return 0
        return 1+max(self.count(root.left),self.count(root.right))
obj = bst()
obj.insert(25)
obj.insert(63)
obj.insert(72)
obj.insert(22)
obj.insert(35)
obj.insert(17)
obj.inorder()
print()
print(obj.count(obj.root))
#19 sum of all values
class Node:
    def __init__(self,data):
        self.data =data
        self.left=None
        self.right=None
class bst:
    def __init__(self):
        self.root = None
    def insert(self,data):
        self.root = self.rec_insert(self.root,data)
    def rec_insert(self,root,data):
        if root is None:
            return Node(data)
        if root.data >data:
            root.left = self.rec_insert(root.left,data)
        else:
            root.right = self.rec_insert(root.right,data)
        return root
    def inorder(self):
        def rec_inorder(root):
            if root:
                rec_inorder(root.left)
                print(root.data,end=" ")
                rec_inorder(root.right)
        rec_inorder(self.root)
    def count(self,root):
        if not root:
            return 0
        return 1+max(self.count(root.left),self.count(root.right))
    def sum(self,root):
        if not root:
            return 0
        return root.data+self.sum(root.left)+self.sum(root.right)
obj = bst()
obj.insert(25)
obj.insert(63)
obj.insert(72)
obj.insert(22)
obj.insert(35)
obj.insert(17)
obj.inorder()
print()
print(obj.count(obj.root))
print(obj.sum(obj.root))
#20 ALL MIX
class Node:
    def __init__(self,data):
        self.data =data
        self.left=None
        self.right=None
class bst:
    def __init__(self):
        self.root = None
    def insert(self,data):
        self.root = self.rec_insert(self.root,data)
    def rec_insert(self,root,data):
        if root is None:
            return Node(data)
        if root.data >data:
            root.left = self.rec_insert(root.left,data)
        else:
            root.right = self.rec_insert(root.right,data)
        return root
    def inorder(self):
        def rec_inorder(root):
            if root:
                rec_inorder(root.left)
                print(root.data,end=" ")
                rec_inorder(root.right)
        rec_inorder(self.root)
    def sum(self,root):
        if not root:  return 0
        return root.data + self.sum(root.left) + self.sum(root.right)
    def count(self, root):
        if not root:  return 0
        return 1 + self.count(root.left) + self.count(root.right)
    def height(self, root):
        if not root:  return 0
        return 1 + max(self.height(root.left) , self.height(root.right))
obj = bst()
obj.insert(20)
obj.insert(60)
obj.insert(70)
obj.insert(25)
obj.insert(35)
obj.insert(10)
obj.inorder()
print()
print( obj.sum(obj.root) )
print( obj.count(obj.root) )
print( obj.height(obj.root)-1 )
#21 COUNT, MIN AND MAX
class Node:
    def __init__(self,data):
        self.data =data
        self.left=None
        self.right=None
class bst:
    def __init__(self):
        self.root = None
    def insert(self,data):
        self.root = self.rec_insert(self.root,data)
    def rec_insert(self,root,data):
        if root is None:
            return Node(data)
        if root.data >data:
            root.left = self.rec_insert(root.left,data)
        else:
            root.right = self.rec_insert(root.right,data)
        return root
    def inorder(self):
        def rec_inorder(root):
            if root:
                rec_inorder(root.left)
                print(root.data,end=" ")
                rec_inorder(root.right)
        rec_inorder(self.root)
    def sum(self,root):
        if not root:  return 0
        return root.data + self.sum(root.left) + self.sum(root.right)
    def count(self, root):
        if not root:  return 0
        return 1 + self.count(root.left) + self.count(root.right)
    def height(self, root):
        if not root:  return 0
        return 1 + max(self.height(root.left) , self.height(root.right))
    def left_sum(self,root):
        if not root:
            return 0
        self.left_sum(root.right)
        left =   self.left_sum(root.left)
    def min(self,root):
        if root is None:
            print("no data")
        while root.left:
            root = root.left
        return root.data
    def max(self, root):
        if root is None:
            print("no data")
        while root.right:
            root = root.right
        return root.data
obj = bst()
obj.insert(20)
obj.insert(60)
obj.insert(70)
obj.insert(5)
obj.insert(351)
obj.insert(10)
obj.inorder()
print()
print( obj.max(obj.root) )
#Deletion in bst
#left side biggest child
#right side smallest child   
#deletion
#22
def find(self,root,key):
    if root is None or root.data==key:
        return root
    if key<root.data:
        return self.find(root.left,key)
    else:
        return self.find(root.right,key)
def delete(self,root,key):
    if root:
        if root.data > key:
            root.left=self.delete(root.left,key)
            return root 
        elif root.data<key:
            root.right=self.delete(root.right,key)
            return root
        if root.left is None:
            return root.right 
        elif root.right is None:
            return root.left
        max_val=self.max(root.left) #from max function
        root.data=max_val
        self.delete(root.left,max_val)
        return root
obj.delete(obj.root,25)  
#23 DELETION OF BST
class Node:
    def __init__(self,data):
        self.data =data
        self.left=None
        self.right=None

class bst:
    def __init__(self):
        self.root = None

    def insert(self,data):
        self.root = self.rec_insert(self.root,data)

    def rec_insert(self,root,data):

        if root is None:
            return Node(data)
        if root.data >data:
            root.left = self.rec_insert(root.left,data)
        else:
            root.right = self.rec_insert(root.right,data)
        return root

    def inorder(self):
        def rec_inorder(root):
            if root:
                rec_inorder(root.left)
                print(root.data,end=" ")
                rec_inorder(root.right)
        rec_inorder(self.root)

    def sum(self,root):
        if not root:  return 0
        return root.data + self.sum(root.left) + self.sum(root.right)

    def count(self, root):
        if not root:  return 0
        return 1 + self.count(root.left) + self.count(root.right)

    def height(self, root):
        if not root:  return 0
        return 1 + max(self.height(root.left) , self.height(root.right))

    # def left_sum(self,root):
    #     if not root:
    #         return 0
    #     self.left_sum(root.right)
    #     left =   self.left_sum(root.left)
    #     return left

    def left_sum(self,root):
        if root is None:
            return 0
        total = 0
        if root.left:
            total += root.left.data
        total += self.left_sum(root.left)
        total += self.left_sum(root.right)
        return total

    def right_sum(self,root):
        if root is None:
            return 0
        rightsum= self.sum(root) - self.root.data - self.left_sum(root)
        return rightsum

    def min(self,root):
        if root is None:
            print("no data")
        while root.left:
            root = root.left
        return root.data

    def max(self, root):
        if root is None:
            print("no data")
        while root.right:
            root = root.right
        return root.data

    def find(self,root,key):
        if root is None or root.data == key:
            return root
        if key < root.data:
            return self.find(root.left,key)
        else:
            return self.find(root.right,key)

    def delete(self,key):
        self.root = self.rec_delete(self.root,key)
    def rec_delete(self,root,key):
        if root:
            if root.data > key:
                root.left = self.rec_delete(root.left,key)
            elif root.data < key:
                root.right = self.rec_delete(root.right,key)
            else:
                if root.left is None:
                    return root.right
                elif root.right is None:
                    return root.left
    
                max_val = self.max(root.left)
                root.data = max_val
                self.rec_delete(root.left,max_val)
            return root
#24 graphs-Adjacent List
class Graph:
    def __init__(self):
        self.graph={}
    def insert(self,v,e):
        if v not in self.graph:
            self.graph[v]=[e]
        else:
            self.graph[v].append(e)
obj=Graph()
obj.insert("B","T") #from B to T
obj.insert("T","B")
obj.insert("B","P")
obj.insert("P","B")
obj.insert("D","P")
obj.insert("P","D")
obj.insert("D","T")
obj.insert("T","D")
obj.insert("B","L")
obj.insert("L","B")
print(obj.graph)
#25 ADJACENCY MATRIX
class Graph:
    def __init__(self,size):
        self.graph = [ [0]*size for i in range(size)]
        self.dict = {"B": 0, "T": 1, "P": 2, "D": 3, "L": 4}
    def insert_list(self,v,e):
        if v not in self.graph:
            self.graph[v] = [e]
        else:
            self.graph[v].append(e)

    def insert_matrix(self,v,e):
        row , col = self.dict[v] ,self.dict[e]
        self.graph[row][col]=1
        self.graph[col][row]=1
obj = Graph(5)
obj.insert_matrix("B","T")
obj.insert_matrix("B","P")
obj.insert_matrix("B","L")
obj.insert_matrix("D","P")
obj.insert_matrix("D","T")
print(obj.graph)
#26 BFS:We use queue
class Graph:
    def __init__(self,size):
            self.graph = {}
    def insert_list(self,v,e):
        if v not in self.graph:
            self.graph[v] = [e]
        else:
            self.graph[v].append(e)

    def bfs(self,start):
        queue = [start]
        visited = []
        while queue:
            cur = queue.pop(0) #if 0 it is bfs, without 0 dfs
            if cur not in visited:
                visited.append(cur)
                queue.extend(self.graph[cur])
        print(visited)
obj = Graph()
obj.insert_list("B","T")
obj.insert_list("T","B")
obj.insert_list("B","P")
obj.insert_list("P","B")
obj.insert_list("B","D")
obj.insert_list("D","B")
obj.insert_list("P","D")
obj.insert_list("D","P")
obj.insert_list("T","D")
obj.insert_list("D","T")
obj.insert_list("D","G")
obj.insert_list("G","D")
obj.insert_list("D","K")
obj.insert_list("K","D")
obj.insert_list("K","L")
obj.insert_list("L","K")
print(obj.graph)
obj.bfs("B")
#27 Linear search:one by one. it searches sequentially.
def linear_search(a,key):
    for i in range(len(a)):
        if a[i]==key:
            return f"{key} found in the index of {i}"
    return "not found"
a=[4,6,7,420,3,20,41,81]
print(linear_search(a,420))
print(linear_search(a,5))
#28 Binary search:take mid value. it works only for sorted list.(not sequentially)
def binary_search(a,key):
    s=0
    e=len(a)-1
    while s<=e: #checks until start crosses end
        mid=(s+e)//2
        if a[mid]==key: #a[mid] means it takes value of that index =12(3rd index)
            return mid
        elif a[mid]>key:
            e=mid-1
        else:
            s=mid+1
        
a=[5,8,10,12,41,45,81,108]
print(binary_search(a,8)) 
# Sorting:arranging the elements in sequence order i.e., asc or des order.
#29 Bubble sort:bubble values goes to the top.It takes n-1 iterations.
def bubble_sort(a):
    for phase in range(1,len(a)):
        #phase 1 
        for i in range(len(a)-phase): #here phase=1 so 6-1=5 
            if a[i]>a[i+1]:
                a[i],a[i+1]=a[i+1],a[i]
    return a         
a=[21,18,61,45,81,10]
print(bubble_sort(a))
#30 bubble_sort
def bubble_sort(a):
    for phase in range(1,len(a)):
        flag=0
        #phase 1 
        for i in range(len(a)-phase): #here phase=1 so 6-1=5 
            if a[i]>a[i+1]:
                flag=1
                a[i],a[i+1]=a[i+1],a[i]
        if flag==0: #if flag remains zero then stop program and got to for loop phase
            break
    return a
a=[21,18,61,45,81,10]
print(bubble_sort(a))
#31 selection_sort
def selection_sort(a):
    for phase in range(len(a)-1):
        min=phase
        #phase 1 
        for i in range(phase+1,len(a)): 
            if a[i]<a[min]:
                min=i
        if min!=phase: 
            a[min],a[phase]=a[phase],a[min]
    return a
a=[21,18,61,45,81,10]
print(selection_sort(a))	
#32 insertion_sort
def insertion_sort(a):
    for i in range(1,len(a)):
        j=i-1
        temp=a[i] #stores the copy of values of ith position
        while j>=0 and a[j]>temp:
            a[j+1]=a[j]
            j-=1 
        a[j+1]=temp
    return a
a=[21,18,61,45,81,10]
print(insertion_sort(a))    
#33 quick_sort
def quick_sort(a,s,e):
    if s<e:
        pivot_index = partition(a,s,e)
        quick_sort(a,s,pivot_index-1)
        quick_sort(a,pivot_index+1,e)
def partition(a,s,e):
    pivot = e
    l = e-1
    while s<=l:
        while a[s] < a[pivot]:
            s+=1
        while l>=0 and a[l]>= a[pivot]:
            l-=1
        if s<l: a[s] , a[l]  = a[l] ,a[s]
    if s>l:  a[s] , a[pivot] = a[pivot] , a[s]
    return s
a = [ 21 ,18,61,45,81,10]
print( quick_sort(a,0,len(a)-1) )
print(a)	
#34 
def Merge_sort(arr):
    if len(arr)==1:
         return
    mid = len(arr)//2
    left = arr[:mid]
    right = arr[mid:]
    Merge_sort(left)
    Merge_sort(right)

    k = i= j =0
    while i<len(left) and j<len(right):
        if left[i]<right[j]:
            arr[k] = left[i]
            i+=1
        else:
            arr[k] = right[j]
            j+=1
        k+=1
    while i<len(left):
        arr[k]=left[i]
        i+=1
        k+=1
    while j < len(right):
        arr[k] = right[j]
        j+=1
        k+=1
a = [ 21 ,18,61,45,81,10]
Merge_sort(a)
print(a)

