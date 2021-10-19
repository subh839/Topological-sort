# Topological-sort

//DFS ALGO
void findTOPO(int node,vector<int> &vis,stack<int> &st,vector<int> adj[]){
	    vis[node] = 1;

	    for(auto it : adj[node]){

	        if(!vis[it]){

	          findTOPO(it,vis,st,adj);

	        }
	    }
	    st.push(node);

	}
	vector<int> topoSort(int N, vector<int> adj[]) 
	{
	  stack<int> st;

	  vector<int> vis(N,0);
	  for(int i = 0;i < N;i++){

	      if(vis[i] == 0){

	          findTOPO(i,vis,st,adj);
	      }
	  }
	  vector<int> res;

	  while(!st.empty()){ 

	      res.push_back(st.top());

	      st.pop();
	  }
	  return res;
	}
