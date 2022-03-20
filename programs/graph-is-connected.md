# Is Graph Connected? / Count Segments in Graph

https://www.geeksforgeeks.org/connected-components-in-an-undirected-graph/

```c#
public class Solution
{
	public int ConnectedComponents(int nodes, int[][] edges)
	{
		Graph graph = new Graph(nodes);
		for (int i = 0; i < edges.Length; i++)
		{
			graph.AddEdge(edges[i][0], edges[i][1]);
		}
		return graph.ConnectedComponents();
	}
}

public class Graph
{
	private readonly int nodes;
	//node, edges
	private readonly Dictionary<int, List<int>> edges;

	bool[] visitedNodes;

	public Graph(int nodes)
	{
		this.nodes = nodes;
		edges = new Dictionary<int, List<int>>();

		for (int i = 0; i < nodes; i++)
		{
			edges.Add(i, new List<int>());
		}

		visitedNodes = new bool[nodes];
	}

	public void AddEdge(int source, int target)
	{
		edges[source].Add(target);
		edges[target].Add(source);
	}

	public int ConnectedComponents()
	{
		int numberOfComponents = 0;

		for(int i = 0; i < nodes; i++)
		{
			if(!visitedNodes[i])
			{
				numberOfComponents++;
				ConnectedComponentsInner(i);
			}
		}

		return numberOfComponents;
	}

	public void ConnectedComponentsInner(int node)
	{
		if(visitedNodes[node])
		{
			return;
		}
		else
		{
			visitedNodes[node] = true;
			foreach (int childNode in edges[node])
			{
				ConnectedComponentsInner(childNode);
			}
		}
	}
}
```