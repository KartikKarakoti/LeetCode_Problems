"""
# Definition for a Node.
class Node:
    def __init__(self, val = 0, neighbors = None):
        self.val = val
        self.neighbors = neighbors if neighbors is not None else []
"""

from typing import Optional


class Solution:
    def __init__(self):
        # Dictionary to store the cloned nodes
        self.cloned_nodes = {}

    def cloneGraph(self, node: Optional["Node"]) -> Optional["Node"]:
        # Base case: if the input node is None, return None
        if node is None:
            return None

        # If the node has already been cloned, return the clone
        if node in self.cloned_nodes:
            return self.cloned_nodes[node]

        # Clone the current node (without neighbors initially)
        clone = Node(node.val)
        # Store the clone in the dictionary to avoid cloning the same node again
        self.cloned_nodes[node] = clone

        # Recursively clone all the neighbors and add them to the cloned node's neighbors list
        for neighbor in node.neighbors:
            clone.neighbors.append(self.cloneGraph(neighbor))

        return clone
