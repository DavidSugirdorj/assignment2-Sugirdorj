# assignment2-Sugirdorj
# David Sugirdorj
###### movie theater in Mongolia.

There is a **Cinema** called **Urgoo** in **Mongolia**, which I used to visit all the time. 
I went there practically on **every celebratory** event that happened to me.

***

### Direction to Urgoo from Maryville

1. go to KS Airport
2. get a plane ticket to that goes from China or Japan or Korea to Mongolia
    1. get out Ulaanbaatar Airport
        1. take a taxi to Urgoo
        2. Get a movie ticket and enjoy!

### Items to bring

* small blanket
* Money!!!!!!
* there are arcades there so play while you wait!!!
* Friends (if have some TT) the more the merrier (or even a girlfriend UmU)

***

![link-to-aboutme](AboutMe.md)

***

### Foods and Drinks to recommend

| Food/Drink | Location | AmountOfMoney |
| :--- | :---| :---|
| Mongolian BBQ | Khaan Nomads Restaurant, Mongolia | 10-20$ |
| Fried Rice | Red Snapper, Kansas City | 10-20$ |
| Dr.Pepper canned | Any grocery store | at most 10$ buy packs|
| Fried Dumplings | Happy Garden, Maryville | 6$ |

***

***

### Quotes

> If anything can go wrong, it will. 
>> (murphy's law) *Edward Aloysius Murphy Jr.*

> If I don't have to do it, I won't. If I have to do it, I'll make it quick. 
>> (from Hyouka) *Oreki Houtarou*

***

### Algorithm

> Given a tree (represented as graph, not as a rooted tree) with n labeled nodes with labels from 1 to n, a Prufer code uniquely idetifies the tree. The sequence has n-2 values.
>> <https://www.geeksforgeeks.org/prufer-code-tree-creation/> 

'''
vector<vector<int>> adj;

vector<int> pruefer_code() {
    int n = adj.size();
    set<int> leafs;
    vector<int> degree(n);
    vector<bool> killed(n, false);
    for (int i = 0; i < n; i++) {
        degree[i] = adj[i].size();
        if (degree[i] == 1)
            leafs.insert(i);
    }

    vector<int> code(n - 2);
    for (int i = 0; i < n - 2; i++) {
        int leaf = *leafs.begin();
        leafs.erase(leafs.begin());
        killed[leaf] = true;

        int v;
        for (int u : adj[leaf]) {
            if (!killed[u])
                v = u;
        }

        code[i] = v;
        if (--degree[v] == 1)
            leafs.insert(v);
    }

    return code;}


<https://cp-algorithms.com/graph/pruefer_code.html>

