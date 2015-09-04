#Daniel Palmer 
import Queue
from collections import defaultdict

#part one, QUEUE
q = Queue.Queue()

#part two, STACK
class Stack():

	def __init__(self):
		self.items = []
    
	def push(self, item):
		return self.items.append(item)
  
	def pop(self):
		return self.items.pop()
	
	def checkSize(self):
		print len(self.container)


class Node():
	def __init__(self,value,parent):
		self.leftChild = None
		self.rightChild = None
		self.value = value
		self.parent = parent
		
class binaryTree():

	def __init__(self):
		self.root = None
	
	def createRoot(self, value):
		if self.root == None:
			self.root = Node(value, None)
		else:
			return "root already exists"
		return self.root

	def returnRoot(self):
		if self.root == None:
			return None
		return self.root

	def add(self, value, parentValue):
		if self.returnRoot == None:
			return "no tree!"

		parentNode = self.search(parentValue)
		
		
		if parentNode == None:
			return "Parent not found"

		elif parentNode.leftChild == None: 
			if parentNode.rightChild == None:
				parentNode.leftChild = Node(value, parentNode)
				return

		elif parentNode.leftChild != None: 
			if parentNode.rightChild == None:
				parentNode.rightChild = Node(value, parentNode)
				return
		return "Parent has two children, node not added"
		
	def delete(self, value):
		nodeToDelete = self.search(value)
		if nodeToDelete:
			if nodeToDelete.leftChild != None:
				if nodeToDelete.rightChild != None:
					print "Node not deleted, has children"
			else:
				if nodeToDelete.parent.leftChild == nodeToDelete:
					nodeToDelete.parent.leftChild = None
					del nodeToDelete
				elif nodeToDelete.parent.rightChild == nodeToDelete:
					nodeToDelete.parent.rightChild = None
					del nodeToDelete
		else:
			return "node not found"
	
	def search(self, value):
		searchQueue = Queue.Queue()

		current = self.returnRoot()

		while(isinstance(current, Node)):
			if current.value == value:
				return current
			
			else:
				searchQueue.put(current.leftChild)
				searchQueue.put(current.rightChild)
				current = searchQueue.get()
			if searchQueue.empty() == True:
				print "item not found!"
				break
		
		return None

	def printTree(self):
		current = self.returnRoot()
		nodeQueue = Queue.Queue()

		while(isinstance(current, Node)): 
			print current.value
			nodeQueue.put(current.leftChild)
			nodeQueue.put(current.rightChild)
			current = nodeQueue.get()
		
			
class graph():
	def __init__(self, dictionary ={}):
		self.dictionary = dictionary

	def addVertex(self, value):
		if value in self.dictionary:
			print "vertex already exists in graph"
		else:
			self.dictionary[value] = []
	def addEdge(self,first,second):
		if first not in self.dictionary or second not in self.dictionary:
			print "error! vertices not found"
		else:
			self.dictionary[first].append(second)
			self.dictionary[second].append(first)
	def findVertex(self,value):
		if value in self.dictionary:
			print value, ":", self.dictionary[value]
		else:
			print "vertex not found!"


def test():
	print "#########  TESTING QUEUE  ########"
	for i in range (0,10):
		q.put(i)
	for i in range (0,10):
		print q.get()
	
	print
	print

	print "#########  TESTING STACK  ########"
	testStack = Stack()
	for i in range (0,10):
		testStack.push(i)
	for i in range (0,10):
		print testStack.pop()

	print
	print

	print "########  TESTING TREE  ##########"
	testTree = binaryTree()
	print "printed tree"
	testTree.createRoot(1)
	testTree.add(2,1)
	testTree.add(3,1)
	testTree.add(4,2)
	testTree.add(5,2)
	testTree.add(6,3)
	testTree.add(7,3)
	testTree.add(8,4)
	testTree.add(9,4)
	testTree.add(10,5)
	testTree.printTree()
	print "**nodes 8,9,10 will now be deleted**"
	testTree.delete(8)
	testTree.delete(9)
	testTree.delete(10)
	testTree.printTree()
	
	print
	print

	print "########  TESTING GRAPH"
	
	testGraph = graph()
	
	testGraph.addVertex(1)
	testGraph.addVertex(2)
	testGraph.addVertex(3)
	testGraph.addVertex(4)
	testGraph.addVertex(5)
	testGraph.addVertex(6)
	testGraph.addVertex(7)
	testGraph.addVertex(8)
	testGraph.addVertex(9)
	testGraph.addVertex(10)
	
	testGraph.addEdge(1,2)
	testGraph.addEdge(2,3)
	testGraph.addEdge(3,4)
	testGraph.addEdge(4,5)
	testGraph.addEdge(5,6)
	testGraph.addEdge(6,7)
	testGraph.addEdge(7,8)
	testGraph.addEdge(8,9)
	testGraph.addEdge(9,10)
	testGraph.addEdge(1,3)
	testGraph.addEdge(2,4)
	testGraph.addEdge(3,5)
	testGraph.addEdge(4,6)
	testGraph.addEdge(5,7)
	testGraph.addEdge(6,8)
	testGraph.addEdge(7,9)
	testGraph.addEdge(8,10)
	testGraph.addEdge(10,2)
	testGraph.addEdge(2,6)
	testGraph.addEdge(5,8)
	
	print "search for vertices 5,6,7,8,9"
	testGraph.findVertex(5)
	testGraph.findVertex(6)
	testGraph.findVertex(7)
	testGraph.findVertex(8)
	testGraph.findVertex(9)

test()
