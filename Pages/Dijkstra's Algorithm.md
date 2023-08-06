# Dijkstra's Algorithm

AKA the shortest path algo, a priority-first algo for pathfinding.

Used primarily to find the shortest path between two nodes on a graph, works by building a set of nodese that have a min. distance from the source node.

Only works when the graph possesses no negative weights, the algorithm adds the weights together when finding a path so negative weights throw off the calculation.

### Basic layout
1. mark all vertices as unvisited;
2. mark source vertex as 0, all others as infinity(unknown);
3. make source vertex current vertex;
4. calculate path length of all neighbouring vertices from current by adding the weight of the edge in the current vertex;
5. if new path is smaller than prev. path length, replace path, otherwise ignore it;
6. mark current vertex as visited after visited neighbour vertex;
7. select vertex with smallest path length as new current vertex and repeat from step 4;
8. 4-7 are repeated until all vertices are marked as visited.

Once this algorithm has been completed we can backtrack to get the shortest path supposedly.

### The Code for this shit
``` 
	#include<iostream>
	#include<climits>
	using namespace std;

	int miniDist(int distance[], bool Tset[]) // finding minimum distance
	{
		int minimum=INT_MAX,ind;

		for(int k=0;k<6;k++) 
		{
			if(Tset[k]==false && distance[k]<=minimum)      
			{
				minimum=distance[k];
				ind=k;
			}
		}
		return ind;
	}

	void DijkstraAlgo(int graph[6][6],int src) // adjacency matrix 
	{
		int distance[6]; // // array to calculate the minimum distance for each node                             
		bool Tset[6];// boolean array to mark visited and unvisited for each node


		for(int k = 0; k<6; k++)
		{
			distance[k] = INT_MAX;
			Tset[k] = false;    
		}

		distance[src] = 0;   // Source vertex distance is set 0               

		for(int k = 0; k<6; k++)                           
		{
			int m=miniDist(distance,Tset); 
			Tset[m]=true;
			for(int k = 0; k<6; k++)                  
			{
				// updating the distance of neighbouring vertex
				if(!Tset[k] && graph[m][k] && distance[m]!=INT_MAX && distance[m]+graph[m][k]<distance[k])
					distance[k]=distance[m]+graph[m][k];
			}
		}
		cout<<"Vertex\t\tDistance from source vertex"<<endl;
		for(int k = 0; k<6; k++)                      
		{ 
			char str=65+k; 
			cout<<str<<"\t\t\t"<<distance[k]<<endl;
		}
	}

	int main()
	{
		int graph[6][6]={
			{0, 1, 2, 0, 0, 0},
			{1, 0, 0, 5, 1, 0},
			{2, 0, 0, 2, 3, 0},
			{0, 5, 2, 0, 2, 2},
			{0, 1, 3, 2, 0, 1},
			{0, 0, 0, 2, 1, 0}};
		DijkstraAlgo(graph,0);
		return 0;                           
	}
```

### But what about the goddamn time complexity???
The time complexity of Dijkstra's boi here is O(V^2) where V is the num. of vertices in the graph.

Note, if the input graph is represented using an adjacency list, then the time complexity is reduced to O(E log V) using a binary heap.

And we haven't learnt much about space complexity yet so fuck that but it can go here later.

### Applications if you're curious
Pretty sure this is how Google does their mapping magic, but it's also used in routing protocols and other boring shit like telephone networking.

See also:
- [[Asymptotic Complexity]]
- [[Algorithms]]