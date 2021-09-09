# assignment2-sunketa
# anusha sunketa
###### paris

Paris (nicknamed the **"City of light"**) is the capital city of France, and the largest city in France. ... If suburbs are counted, the population of the Paris area rises to 12 million people. The Seine river runs through the oldest part of Paris, and divides it into two parts, known as the Left Bank and the Right Bank.

---

### Route Map

1. Go to MCI airport, kansas city
2. Board into a flight to Paris Charles de Gaulle Airport, Paris
    1. Catch a taxi
    2. Go to the main city and enjoy the tourist places and food 
* Camera
* Power bank
* Lays

[AboutMeLink](AboutMe.md)

---

### Recommended food

Below table shows the food items and their locations and price of them.

|    Food Items   |     Location     |   Amount    |
|   -----------   |    ----------    |  --------   |
|Chicken Biryani  |   Hyderabad      |    300      |
|Keema Pulav      |   Nizamabad      |    200      |
|Mutton Biryani   |   Delhi          |    400      |
|Kaju Barfi       |   Bengalore      |    550      |

---

## Inspirational quotes

> Be yourself; everyone else is already taken - *Oscar Wilde*     
> Be the change that you wish to see in the world - *Mahathma Gandhi*

---

## code fencing

### Graphs Spanning

> In the mathematical field of graph theory, a spanning tree T of an undirected graph G is a subgraph that is a tree which includes all of the vertices of G. In general, a graph may have several spanning trees, but a graph that is not connected will not contain a spanning tree (see spanning forests below). If all of the edges of G are also edges of a spanning tree T of G, then G is a tree and is identical to T (that is, a tree has a unique spanning tree and it is itself).

<https://en.wikipedia.org/wiki/Spanning_tree>

```

struct Edge {
    int u, v, weight;
    bool operator<(Edge const& other) {
        return weight < other.weight;
    }
};

int n;
vector<Edge> edges;

int cost = 0;
vector<int> tree_id(n);
vector<Edge> result;
for (int i = 0; i < n; i++)
    tree_id[i] = i;

sort(edges.begin(), edges.end());

for (Edge e : edges) {
    if (tree_id[e.u] != tree_id[e.v]) {
        cost += e.weight;
        result.push_back(e);

        int old_id = tree_id[e.u], new_id = tree_id[e.v];
        for (int i = 0; i < n; i++) {
            if (tree_id[i] == old_id)
                tree_id[i] = new_id;
        }
    }
}

```
Link : <https://cp-algorithms.com/graph/mst_kruskal.html>




