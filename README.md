[Taken courses](taken-courses)

<img title="A gem" src="shape1 - cropped, resized, and cleaned.png">

# Brian's perambulations
## 2019-05-23

We recently fixed Simple2ECB from Georgiadis et al. 2014. We are working on Rec2ECB with emphasis on correctness; time also is still not yet O(m * n * alpha). We need to determine five cases (two bridge-related and three shortcut-related) in lower time. The first two cases are for auxiliary nodes and auxiliary edges. The last three cases are for auxiliary edges only. After we complete Rec2ECB, we will be relatively close to finishing Fast2ECB efficiently, as well. A key is that we need to distinguish between overall ordinary nodes/edges and locally ordinary nodes/edges.

## 2019-04-27

Turns out there's a bug with our approach of using 2-edge-connectivity to answer lax Boolean MM -- it is possible to contaminate whether we have enough paths by looping around back to right side using behind node.

Briefly, we considered whether 1-edge-connectivity (i.e. strongly connected components) is enough. Those ideas did not pan out.

Thankfully, we have a new idea and it uses 2-vertex-connectivity. Somewhat reassuringly, 2-vertex-connectivity queries can be done in O(1) time as well, pre-processing takes time linear in number of nodes and edges, the algorithms are slightly more difficult to implement w.r.t. 2-edge-connectivity, we can maximally take advantage of sparsity. Also, there is a simple version as well that we can use for proof of concept and testing cases that we fail for 2-edge-connectivity-based approach. Also, we don't have to throw all our previous algorithm implementations away and pieces we don't need anymore can be laid to rest by testing them for correctness by comparing to results for simple versions of those algorithms (i.e. simple versions for them generally do seem to exist, which is also good).

## 2019-04-25

It's a little bit crazy to think that I've been working on some version of fast MM since end of 2017.

Anyhow, we are working on summarizing the Georgiadis et al. 2014 article and especially the part of it that centers on how to construct auxiliary graphs.

## 2019-04-17

We have finished implementing the seven Fraczak et al. 2013 dominator tree algorithms s.t. they are as efficient as promised from original article with exception that we do not use Gabow-Tarjan 1985 off-line DSU algorithm. As such, a few of them have time nearly linear in \|E\|; i.e. the time is in O(\|E\| \* alpha(\|V\|, \|E\|). We choose to focus on algorithm GD #2. Now, we plan to work on Rec2ECB and Fast2ECB from Georgiadis et al. 2014. Later, we will make use of Gabow-Tarjan DSU to speed up GD #2 to take time linear in \|E\| under certain model of computation.

## 2019-04-13

We have figured out almost all of the seven Fraczak et al. 2013 dominator tree algorithms. Now, we are planning on polishing our implementations. This means we can move on to Georgiadis et al. 2014 Rec2ECB and Fast2ECB soon or Gabow/Tarjan 1985 off-line DSU. DFS tree is the union tree we use for off-line DSU. We also have to figure out auxiliary graph for Georgaidis et al. 2014.

## 2019-03-30 (again)

Splendid success! We implemented reduction of lax Boolean MM to Simple2ECB and SCC algorithms. We appear to be getting the same answer as brute-force. This approach is slower than brute-force in terms of asymptotic complexity. It is a proof of concept. Now, we work on Georgiadis et al. 2014 Rec2ECB and Fast2ECB, Gabow/Tarjan 1985 off-line DSU, Fraczak et al. 2013 vertex dominator tree.

## 2019-03-30

We've implemented Tarjan 1976 INTERVALS and BRIDGES, Italiano et al. strong bridges. Our implementation of INTERVALS and BRIDGES is ready for swapping out of standard DSU structure for Gabow/Tarjan 1985 off-line DSU structure that uses links instead of standard unions; however, we have not implemented that Gabow/Tarjan structure yet, though we believe we understand how to. We are working on Georgiadis et al. 2014 Simple2ECB. The algorithm ought to be O(n ^ 3 * alpha(n, n ^ 2))-time.

## 2019-03-17

We've figured out Gabow/Tarjan 1985 macroset/microset-based off-line DSU, Tarjan 1976 flow-graph INTERVALS and BRIDGES; we have gone through the articles for them and we believe we have filled in gaps in the descriptions. Now, we will attempt to implement Simple2ECB and judge correctness based on if we get the right answers for our application (i.e. we run a gauntlet). First, we do what it takes to get correct answers and then we will swap out parts for faster versions. Ultimately, the algorithm ought to be O(n ^ 3 * alpha(n, n ^ 2))-time.

To get whether two nodes are 2-edge-connected, we take advantage of 2-edge-connected blocks partitioning the vertex set and check if the two nodes are in same 2-edge-connected block in constant time.

## 2019-02-19

<img title="Incredible!" src="incredible - cropped and resized.png">

We're working on implementing Simple2ECB from Georgiadis et al. 2016. As we partially mentioned, this in a sense requires Gabow/Tarjan 1985 off-line DSU, Kosaraju 1978 SCC, Bender/Farach-Colton 2000 LCA, Tarjan 1976 flow-graph bridges, Italiano et al. 2012 strong bridges. Also, Fraczak et al. 2013 dominator tree is required for Rec2ECB.

Thankfully, the Fraczak article seems quite detailed and it happens to also use Gabow/Tarjan 1985 off-line DSU, which allows time linear in number of items and find/union queries. If we were more clever, we might be able to reduce vertex-dominator to edge-dominator case, though it's not clear how to then construct a terse vertex dominator tree from a collection of vertex dominators. So, we don't do that reduction and instead defer to Fraczak.

## 2019-02-08

To get to edge dominator set, we need intervals (via Tarjan's "INTERVALS") and flow-graph bridge set (via Tarjan's "BRIDGES"); before that, we need to use DFS to explicitly create a tree, using which we can get subtree size, pre-order numbering, edge classification, pretty printing. Then, using edge dominator set, we can get strong bridges.

## 2019-02-06

We have at our disposal certain algorithms whose implementations we have generally borrowed from other people in the interest of expediency. These are disjoint set union-find data structure with union-by-size and path compression, LCA from Bender and Farach-Colton 2000, SCC algorithm from Kosaraju 1978.

Now, we need flow-graph-bridge set finding, which serves to give us edge dominator set for a directed graph. Then, we use edge dominators to get strong bridges for a directed graph. Then, we use strong bridges to get 2-edge-connected blocks. We use 2-edge-connected blocks to answer 2-edge-connected queries for pairs of vertices. The first 2ECB algorithm we implement will be Simple2ECB from Georgiadis et al. 2014.

## 2019-02-02

Not writing about our progress and keeping secrets is eating us up inside and leading us to be less productive.

We have a way for lax Boolean MM that takes time in O(n ^ 2). We have a partial approach for strict Boolean MM -- we have pushed it to backburner in order that we may be able to buy time by solving a weaker problem -- i.e. lax Boolean MM. The partial strict approach happens to -- as an aside -- make use of our lax flavor problem. The article for lax flavor we have written up partially and we are working on implementing it, currently.

Pretty incredible that the time can be strictly quadratic, no? That's a highlight -- hopefully we will implement successfully and publish to pre-print before we get front-run, though.

We went to a magic show on Feb. 1st. It's pretty fun to see what one can do with sleight of hand.

We have a bunch of loose strings to tie up regarding Oregon. I have some things on Amazon that are not selling and that we should probably donate to some brick and mortar store. I have some material from high school classes (e.g. AP Biology) in a filing cabinet to pull out and group into folders.

## 2019-01-09

Hope is still alive for a reasonably fast approach for strict Boolean MM.

Meanwhile, here are some bits of art.

<img title="Whirlpool 1a" src="whirlpool1a - cropped, resized, cropped.png"> <img title="Whirlpool 1b" src="whirlpool1b - cropped, resized, cropped.png">

## 2018-12-17

We have figured out a way to solve strict Boolean MM in O(n ^ 2 * polylog(n)) time, but it will take a while to implement and test. For our sanity's sake, though, we leave this message in case it does indeed take a long time to follow through on.

## 2018-12-09

It turns out our alternate approach for (min, plus) semiring MM approach is not valid because there is a coefficient of d (i.e. our dimension) that we leave out. This d for matrix multiplication is n and so is not small and fixed (e.g. it is not two); so, the approach we are thinking of takes time that is actually n-factor larger and thus takes time at least cubic in n.

## 2018-12-07

We are waffling -- we have another idea for lax Boolean semiring and (min, plus) semiring MM approaches. In 2016, we described a possible way to solve APSP that involves first solving (min, plus) MM via Chan 2008 red-blue dominance queries. We can reduce APSP to lax Boolean MM, which reduces to (min, plus) MM. The idea is that (min, plus) MM takes time in O(n ^ 2 \* log(n) ^ 2), though there is a chance that the reductions may introduce extra polylogarithmic factors. It would be great if this works as then we have something to show for our time. We note that these ideas do not necessarily imply good times for strict Boolean semiring and standard (plus, times) ring flavors of MM.

## 2018-12-06

We have dropped lax Boolean, strict Boolean, f.p. (plus, times), (min, {plus, max}) (i.e. tropical) MM approaches. We posted a postmortem in our FMM repository. We believe that if we are to come back to this problem later, that we will need a good understanding of tensors.

Perhaps it is telling that we regret not being able to make a worthwhile article (currently) given that the typesetting we arrived at is so pleasant.

## 2018-11-11

We will be heading back to China for from November 12th to November 23rd.

We have another detail to address that is important -- we must acknowledge that we don't always have a one bit at the right staircase. Somewhat fortuitously, as long as we occasionally omit rectangles at right, the modifier memoized values are made in the same way and are used in the same way. This is the case not because the modifier e.g. gives across-the-board zero values in some sense. Our remedy involves two details -- (1) We omit rectangles that are weighted at right if we have a zero bit for some B column; and (2) it's okay if we have a zero bit at right if we have a handful of one bits at left as the modifier continues to work correctly in this case (i.e. without requiring a change in how we determine it and use it).

## 2018-11-10 (for fourth time)

We will address what are and how to use the modifier memoized array values.

First, we consider relative behavior. If we have full A row prefix w.r.t. a B column, our modifier pair should give zero. Note that by full A row prefix w.r.t. a B column, we mean lowest A row up to same level as B column. To get this zero, we have x\_1 - x\_2 == 0. The x\_2 is shortening of modifier based on B column level and x\_1 is based on how non-full A row prefix is; both these values are based on modifier memoized values. If A prefix is full w.r.t. B column, x\_1 equals x\_2. How do we choose an x\_2? It is the value for the level associated with that for chosen B column.

Secondly, we consider absolute behavior. We wish to avoid off-by-one error. The correct behavior is we have value describe for a level contributions strictly above that level. In other words, we do not have "at or above" behavior; we have "above" behavior. Okay, then -- what are we counting? We are counting number of zeroes in left staircase -- and we care about this amount s.t. they are strictly above our level.

## 2018-11-10 (for third time)

Well, how do we get prefix that we use by subtracting to get suffix when it comes to B column rectangle reactionary weights for modifier pre-processing? We note that individual values in modifier memoization array may be larger than one and they are nondescending as we go from high z to low z. We don't blame ourselves for neglecting to go into this issue in detail yet; the other details are just as important; how do we memoize? To get prefix, we consider number of zero bits either (1) above us only or (2) above us or at same level; choosing between those two ways of memoizing just affects how we use the memoized values. Then, we subtract so we don't have unnecessary B column rectangle reactionaries that protrude; this may sound vague, but we make sense of this description by resorting to considering fixed-z subproblems for correctness. The modifier memoized array has n entries and they are for different z value targets.

We flit between being confident and uncertain about the approach we have described, but currently we feel optimistic, because we have some agreement in that when we eyeball what our modifiers give for certain small examples we do get numbers to subtract that seem appropriate or numbers that are memoized that can be used correctly later.

Our next task is to work out some examples by hand.

P.S. -- One might have thought we would have gone through examples by hand earlier -- and we have in a sense -- at the same time, it has been important to not be too invested in a single approach because it can be difficult to know we are in a dead-end or whether it is worth the (significant) effort to e.g. devise the necessary notation to keep the work simultaneously terse and understandable.

## 2018-11-10 (again)

Three things are helping us stay confident in the correctness of the approach:

1. We don't need a literal rectangle train for suffix.
2. We want suffix because we are dealing with A row prefix -- suffix is poorly named and is for B column rectangle reactionaries what prefix is for A row collections. In a sense, the former suffix and the latter prefix are the same thing -- they are truncated version of a sequence where only one end differs and no gaps are allowed in the result sequence w.r.t. original sequence.
3. A way to prove correctness (e.g. because it may seem confusing to want a suffix for dealing with modifier) is to consider isolating fixed-z subproblems and considering them separately.

## 2018-11-10

This is about Boolean MM.

So, we're building on Kaplan's approach. They say that four-sided query in plane takes too much time. We agree, except that we argue that we can cope by using three-sided query pairs in plane; i.e. we use telescoping to get the same effect.

They use color carpentry, which means specifically that we start of by making use of a particular pair of descending staircases where left has points that are associated with A rows and right has points that are associated with B columns. Eventually, we will need a pair of that arrangement to correctly determine all of the matrix for the product result. A target B column can only be considered in combination with a target A row if that A row point is at same level vertically or lower. For second pair of staircases, we reverse the order of A rows, which lets us consider all combinations of A row and B column. Color refers to each offset for a dot product of an A row and B column. With color carpentry, many colors can be considered to be superimposed on each other. Eventually, we will see that it is okay for us to consider each color in isolation initially. The term color carpentry refers to the idea that we can flatten rectangles for the same color so that we don't double-count ones when we have a pair of ones interacting. We care about this "saturating" behavior because of Kaplan's argument that we can use it to determine a union (i.e. bit-wise OR) and then turn that into an intersection (i.e. bit-wise AND), the latter of which is in a sense what Boolean MM product asks for. It is not entirely, because we add the detail of the idea that we need to add the results of bit-wise AND for each color.

While we start with points associated with A row or B column and a color, we will want to turn them into rectangles. We will get rectangles as a result of color carpentry, which we then store and access via using a segment tree. Segment trees are good for counting queries (as opposed to reporting, which requires at least unit time for each satisfying rectangle for point enclosure), which is in a sense what we would like. However, we will need to cope with three-sided queries. We have an idea that instead of four-sided query that selects via a rectangular query region that includes an A row and a B column and that we assume is well-formed, we can instead of isolating a specific A row, we consider point enclosure query that selects for a B column and a contiguous sequence (i.e. "prefix") of A rows. Then, we consider another such query except that deals with a prefix that is one smaller in terms of number of A rows. The idea then is that we subtract the result and if our rectangles are valid and that they have adequate weights then we are using telescoping to get a correct answer for an output cell. We specify prefixes by using a third dimension (i.e. an extra one on top of the plane) that we say is for z-level. For left staircase, A row rectangles have z value that starts at zero at right and repeatedly grows by one as we move left. For right staircase, all B column rectangles have z equal to zero. Given that we use a 3-d segment tree, we know that subtrees we visit will have for the current component sorted items; we can accumulate from one side moving to other to get correct memoized values for nodes in the tree which we use for determining the answer to one of a pair of queries we need for an output cell. This is not enough, however.

If we attempt implementing what we have described so far, we will only get the correct answer when our two prefixes are size one and size zero. This is because if done improperly, we are double-counting or under-counting as we start to combine subproblems for individual z values. Or, if we wish to introduce more rectangles with various z values to combat the inaccurate counting which is due to not adequately addressing the issue of saturation, we may be able to get the correct answer but do so in too much time (i.e. cubic in n). There is another way, however. We first ought to say that so far, we assume that for each A row at left (except right-most one) we have a z value that no other rectangle shares. We can see that if we unpack and look at the required rectangles when we consider individual z values and a fixed color, we will see that there are repeated shapes on the right staircase (for each time we have a zero for an A row at left); each z value is associated with a single left A row for a fixed color. Then, if we give ourselves permission to have weights for rectangles that are not solely either one or zero, but possibly larger than one, we can share work by not duplicating those rectangles at right that appear when we have a zero at left, as long as we give larger weights which assume that we are dealing with maximal-size A row prefixes s.t. those prefixes are valid for the current B column choice. It may not seem like we are making progress yet, but we note that so far we are avoiding time cubic in n, again; particularly, we would like to point out that the combining of rectangles for fixed color and when we have a zero at left for an A row is affordable enough. We are not getting a correct answer, yet.

We have dealt with telescoping via z that reins in A rows at left. It turns out that we will benefit by considering telescoping for A row interactions with fixed B column; we rein them in by introducing a non-geometric detail s.t. for each query we will need a modifier value that we subtract in O(1) time as long as we perform pre-processing, which we argue is doable. With the shared rectangles at right, we are getting results s.t. we have singled out a particular B column, but too many reactionary contributions resulting from A rows at left that interact with the B column. We undo the contributions from unnecessary right rectangles.

B columns at right are affected by A rows at left at or below our level defined by B column chosen. Not all A rows we want to interact with a B column; this affects killing A rows and also affects killing B rectangles that are reactionary to A row. B column is chosen via query point. A row is chosen via z. Compatible A row can be at or below our B column level. We are counting too many reactionary rectangles. We have three key values: B column "z", z-level for chosen A row, highest z. As part of memoization, we keep an array for a fixed color. Later, we merge across colors. This array for a fixed color describes w.r.t. highest z (i.e. upper-most) how much to remove to get to B column. In general, the weights can be s.t. their sum is much larger than n -- this is a roundabout way of saying individual weights can also be much larger than one. This is not enough, however. We need to remove not starting at highest z, but starting at z value for chosen A row. We take advantage of telescoping or non-scrambledness -- whatever one wishes to call it -- again and remove the effect of values from z values in between highest z and chosen A row z by subtracting a "prefix" (again). Then, we merge across colors to get good time for query -- i.e. not proportional to number of colors, but in O(1). The pre-processing for this merging takes time overall in O(n ^ 2). The arithmetic is tricky, we admit. But, it can be done affordably.

We have a main query for each output cell. For each main query, we have two primary queries. For each primary query, we have a rough query and a pair of modifier queries. Rough query is for a prefix of A rows. Modifier query pair is to get the correct value to subtract from result of a rough query because we over-counted B rectangles that are reactionary towards chosen A row. Then, we take difference of results for pair of primary queries. Then, for main query, we use union-intersection arithmetic.

Then, we have a correct answer. We appeal to considering each z value in isolation. We have two-layered telescoping -- that for A row prefix and that for B columns that are reactionary towards our chosen A row.

We have neglected to consider optimization -- time is O(n ^ 2 \* log(n) ^ 3) if we do not use fractional cascading and interval tree for lowest level; otherwise, we could remove a factor of log(n). Of course, also, we can consider floating-point MM that uses ideas from the Boolean MM approach we have just described.

## 2018-10-31

Came back from China yesterday.

The Boolean MM things are not working out. We have one last hunch to see through and after that we will come up with a post-mortem article to show what we tried as a sort of way of making sure we do not have totally nothing to show for our time.

We finished My Antonia on October 30th, 2018. We'll be working on reading Oedipus.

After this, we will be focusing on class work.

We might like to update our class history with semesters spent at community colleges for completion.

## 2018-10-13

Nope, ignoring colors gives a similar approach -- expiries bias towards adding detail, ignoring colors bias towards removing detail; both may require knowing a lot about a certain B column's one-bit pattern s.t. we require O(n ^ 3) time, again.

Needless to say, if this were all there was to the story, we would come to the conclusion that our attempt at Boolean MM is incomplete.

We currently are pursuing an approach that is based on flattening for each color across A rows and then getting closer to the intention of having telescoping -- i.e. we have progressively more contributions (i.e. along z direction) in an efficient manner via base post-flatten shape and pair of modulating post-flatten shapes, the former of which consists of many rectangles, each of which have weight we update in O(1) time instead of in O(p) time, where p is number of rectangles that makes that base shape up via indirection (i.e. we associate each with a symbol, which we later look up weight for via a hash table). The reason we have a pair of modulating rectangles is that one is to repair a prefix and the other is for neutralizing effect of that repair for a later z. The idea is that this leads to an O(n)-factor time improvement.

We even believe there is a chance that there is a quadratic-time algorithm for Boolean MM, currently, but we ought to have learned our lesson by now that quadrarithmic-time is good enough for now. We ought to implement and know that this first approach actually works.

## 2018-10-12

I must admit that the core idea for out previous claim that we figured Boolean MM out -- collapsing colors -- was not enough. Easy come, easy go, I suppose. The reason we did not realize this was that we actually must have multiple expiry rectangles when a B column for some color has a one bit. If we only needed one, then we can customize expiries for the B column cross-color one bit pattern, which would take O(n ^ 2) time overall. If we have O(n) expiry rectangles instead of one for each B-column-color combination, then instead we have O(n ^ 3) time overall -- the idea is that each B column could have a relatively unique cross-color one-bit pattern, which aids in making this more-correct pre-processing too expensive. We remember that the point of expiry is to avoid double-counting one bits and so we would from a certain perspective need them every time we alternate from zero to one or vice versa -- not just once for each B-column-color combination.

However, we have actually figured the problem out in that we can take more advantage of problem structure. We have no need for expiry rectangles at all -- given that they only are relevant when B column has a one bit for some color, we can make an additional observation (after a certain amount of floundering and consternation) that we can avoid cut-out and expiry altogether when we have a one bit for a B-column-color combination because the contribution for a prefix difference for that combination is highly predictable -- it is always one.

Then, the structure construction is even cheaper than before (though not necessarily asymptotically -- i.e. in big-oh notation). We then ought to an early moment pre-process to count the number of one bits for each B column so that we can use that value and add to the result from a query (i.e. via a prefix difference).

Voila!

We are attempting to write this approach up in an article and attempting to implement this. Somehow, it feels that we should (as mentioned in last blog entry) be a bit secretive. Wish us luck!

Of course, we should mention that in the future, we may wish to swap out the tree structure; how practical or difficult this would be is currently up in the air to us.

## 2018-10-10

We figured Boolean MM case out! I feel almost that I ought to keep it a secret until I can finish the article, but alas. We ended up dropping so many aspects. Also, I am feeling a bit paranoid right now.

This comes at the heels of a disappointment as to the actual distance for a max-weight MST for n points in n dimensions; it turns out it (in l1-norm) is in O(n), not O(1) adjusted with protrusion-related factors. This appears to be the case when we have a hypercube in n dimensions with either hypercube primitive or hypersphere primitive in n - 1 dimensions. An offset that we mindlessly introduced to bound a particular expression turned out to be too costly.

The important idea is criss-crossing as an extra early pre-processing phase to merge color contributions for expiry rectangles that appear later.

The result is Boolean MM in O(n ^ 2 \* log(n) ^ 2) time. The polylog factor can presumably be improved with a different tree in the future.

Now, we can focus on finishing the implementation (yes -- we have not finished it completely yet) and the article. We can also mention ideas that we ended up dropping. (In the end, of course, fewer required details is better.)

We also have floating-point version to consider, next.

We can talk about (i) approximate NNS, use of JL lemma, turning it into a Las Vegas approach; (ii) appropriateness conditions; (iii) an Indyk paper analysis.

The best part is that this addition does not require very much change to a partly-finished implementation that we already have; we need to have more expiry rectangles with different weights based on pre-processing criss-cross phase.

## 2018-10-07

### Tooth fixed
I got a tooth fixed on October 1st (i.e. this past month). Last time we visited China (in around April of this past year), I got a root canal. This time, instead of a crown, I got a silicone-based filling/reconstruction. The root canal was ~900Y and the filling was ~360Y. That makes ~$150 for the former and ~$60 for the latter. Altogether, that's $210. This tooth -- a left molar -- was cut up considerably as part of an attempt to fix a metal filling that had fallen out. What's good is that with the reconstruction, the tooth is essentially whole again and the material looks like tooth material. It's a good deal!

### Funds
Reminiscing -- for freshman year, the meal plan we went for was likely non-upgraded and included as part of rent for the dorm. Based on 2018-2019 rates, a triple at unit two was likely around $14,600 for an academic year (i.e. ten months). This means each month was about $1,460.

### Legitimacy of a prediction for n\_p points on a n\_d-dimensional hypersphere s.t. n\_p > n\_d + 1

We are considering upper bound on distance associated with an edge for a max-weight MST for n\_p points on the surface of a hypersphere in n\_d dimensions s.t. n\_p > n\_d + 1. Typically, the maximum number of mutually equidistant points in n\_d dimensions is n\_d + 1.

Why do we care about Hamiltonian paths associated with polytopes? The candidate edges are purely those relating vertices to "neighbor" vertices, which we associate with predictably-low lengths via "densifying" a net by considering n-dimensional hypercube surface area and (n - 1)-dimensional primitive hypercube volumes.

We made a mistake for FMM s.t. we thought that d-simplex is a Platonic solid, but Platonic solids are three-dimensional; we care because Platonic solids are associated with Hamiltonian paths.

Instead, we can show that a d-simplex is associated with a Hamiltonian path as it is a simple d-polytope and via Barnette, for d >= 4, simple d-polytopes are associated with Hamiltonian path. For d == 3, d-simplex is associated with a Hamiltonian path via Platonic solid via Gardner. Trivially, for d in {1, 2}, d-simplex is also associated with a Hamiltonian path.

### Prediction for n\_p points on a n\_d-dimensional hypersphere s.t. n\_p << n\_d = m \* n\_p

We get a prediction that if n\_d = m * n\_p that distance is not bounded by twenty, but by log\_2(m) \* 20.

We can confirm this by performing a ratio test (i.e. use a limit).

### Postscript

The above concerns are associated with predictions that are wrong -- distances for l1-norm for first case and second case are not twenty and log\_2(m) \* 20, but 20 \* n and log\_2(m) \* 20 \* n.

## 2018-09-21

We are going to drop Chan's ANN approach for our Boolean MM. It is hard for us to adequately tile d-dimensional space (where d is large) using spherical cones with a point arbitrarily chosen as center s.t. the cones emanate from it. Also, presumably some overlap is allowable. Supposedly, we can get (1 + epsilon)-approximate nearest neighbor via Chan, which then uses Arya and Mount's BBD-tree for each cone and then possibly an additional optimization. We wish to be able to tune s.t. we have a "branching factor" of between one and two for each dimension. But, while it is in principle plausible that we can tune to get a target number of cones, the details are unclear to us s.t. we do not end up with far too few or far too many. The difficulty of this task is related to why we ended up using hypercubes for primitives that we tile instead of using hyperspheres for primitives for Boolean MM; if packing constant is not one, then of course our tiling can be quite elaborate and we would have to justify why some packing constant is achievable.

We found out that Indyk described a deterministic version of LSH (DLSH). We also had Las-Vegas-style LSH (LVLSH) planned for word-packed version of ANN -- i.e. for f.p. case of MM. The reason for this is that it supports word-packing, ostensibly. Why then would we want to pursue either DLSH or LVLSH for both Boolean or f.p. flavors of MM? DLSH is described somewhat vaguely, is older (from 2000), is for (3 + epsilon)-approximate NN, has deterministic time. LVLSH is more detailed, is newer (from 2016), is for (1 + epsilon)-approximate NN, has expected time.

TO put having 2-factor vs. 4-factor in perspective, log_2(1024) = 10; 10 * 2 = 20 and 10 * 4 = 40 are both much lower than 1024. On the other hand, a peace of mind from having deterministic time instead of expected time has value, as well.

We still must see if both DLSH and LVLSH work with word-packing. We will have to look into hash function families for Hamming distances (i.e. l1-norm) and possibly the same but s.t. we have no false negatives. It seems that bit sampling (for Hamming distance hash) can be done not on a bit-by-bit basis necessarily, but with a whole word at a time, by sampling uniformly from integers in \[0, 2 ^ m' - 1\], where words are m' bits large.

## 2018-09-15

Making progress with an idea called "protrusion ratio".

<img title="Protrusion of diagonal vs. that of radius" src="protrusion1 - cropped, cleaned, and resized.png"> <img title="A close-up of protrusion" src="protrusion2 - cropped, cleaned, and resized.png">

## 2018-09-02

Still procrastinating.

We are using n-dimensional cube and tiling using (n - 1)-dimensional spheres and then going from Euclidean distance to Manhattan distance upper bound via added sqrt(n) factor. We expect to still have decay. We may be interested in stripping out constant factors to make plotting easier. We still need to incorporate average l1-norm distance, even if (thinking into the future) we eventually are able to exploit sparsity and are dealing with not n equidistant points but perhaps with only two equidistant points; a current motto of ours is that truncated decay is still decay, but over a smaller domain. We may wish to subtract from this average a one because we need (and can afford) an entry point.

To be truly confident, we would like to know if average over n terms in n-dimensional space minus one gives same order as average over two terms in n-dimensional space minus one.

If due to sparsity we have only two points in n-dimensional space (e.g. if we have two non-zero A rows), we can look beyond discrete aspect and have integral s.t. we also have coarse sampling.

Here is a useful result -- integral of 1 / x shifted left so that there is no singularity at x == 0 (and instead there is one at a negative x) is logarithm; this implies that we don't have to do much that is special to properly take advantage of sparsity. For our geometric approach, either an item for an A row or B column appears or it does not.

So, unlike we just said on September 1st, surprisingly, it looks like logarithms for equidistant aspect may appear as long as we integrate. It's unclear at the moment whether the l1-norm distances for equidistant codes will lead to polylog(n) terms; that is power of log that may be larger than one.

We can handle rectangular input matrices trivially; it is as if we just have more or fewer A rows or B columns.

A more difficult thing to handle is running time in terms of number of non-zeroes; all we can do at the moment is hand-wave and say that if we have lots of zeroes, we are tending towards localizing for the codes on Hamming hypercube. Imbalance -- e.g. having much more zeroes than ones -- leads to localizing, which reduces time for pre-processing. This will have to be a future issue to consider, if we want to get desirable behavior, to get specific time bounds, and to do it justice.

Based on recent news, it looks like there's competition from a school in Massachusetts.

## 2018-09-01

We're interested in seeing how distance to closest neighbor decreases at worst as we increase the number of points on a hypersphere or hypercube. Intuitively, the biggest distances occur with small number of points; as we continue to add points with requirement that we have equal spacing, the distances decrease relatively less than they do earlier on. Further, say we have n points on an n-dimensional cube or sphere. One might think that by increasing the dimension at the same time that it could be the case that average distance does not approach zero as n approaches infinity. Surprisingly, we do observe decay as n approaches infinity. An important issue is to find out after scaling (to account for differences between l1 norm and l2 norm) and solving for ideal packing whether the decay implies time in O(n ^ 2 \* polylog(n)). It seems unlikely for us to actually have logarithms explicitly involved for this step, so we are hoping that this step is in O(n ^ 2) and other steps will act as bottlenecks and have logarithms involved.

We are planning on using (1 + epsilon)-factor approximate NN with epsilon at most one; also, we use bichromatic approximate closest pairs and Prim's for finding approximate MST. These should be able to work even though our dimension is n (i.e. it is high). Chan 1998 has information on such tasks and his approaches do not have chance of failure as would be the case with locality-sensitive hashing. Also, it seems a lot easier to implement ANN rather than exact NN and for our application we can accept at most a constant epsilon for error ratio. This is true even though relation between l1 and l2 norms is non-trivial and we must assume that we have only the n input points (and then argue that with 2 \* n points we are strictly better; these 2 \* n points include n input points and n points resulting from XOR).

These distances are important because they tell us about how XOR one-bits decreases; intuitively, since the sphere or cube has finite surface area, there must be decay in min. distances. Also, intuitively, concentrated points give good XOR for nearest neighbor; this is essentially why we consider evenly spaced out; this latter case is the opposite of the former case qualitatively.

We will need to find out surface area of higher-dimensional hypercube. We can use XOR s.t. input vectors are replaced with representation vectors with at most two non-zeroes and dictionary vectors we memoize cut-out/expiry rectangles for based on neighbors. We first create MST. We're happy with 2-approximation because this just means XOR distances are multiplied by two overall, which does not affect decay order. We could later find a trade-off that reduces epsilon s.t. we can afford it. Then, we choose an entry point for the tree. Then, all other nodes are based on some node we previously memoized for.

We use many upper bounds; e.g. for Euclidean vs. Manhattan distances, for sphere vs. cube, NN for islands vs. MST for tree, dimension for n-dimensional cube vs. dimension for primitive on its surface (i.e. the primitive's dimension is n - 1), adding more (i.e. O(n)) XOR-related points is at least as good as having only input points (i.e. we have n input points and possibly 2 \* n points that each ar either from input or related to result from XOR).

Intermediate coefficients that are not in {0, 1}, i.e. that are possibly greater than one or that are negative (possibly counterintuitively) or that are fractional are fine as long as result coefficients for each query end up being in {0, 1} for Boolean MM. Fractional case is not desirable for Boolean MM because we would like to later for floating-point case be able to take advantage of word packing. If Boolean case does not have intermediate coefficients that take O(1) bits in a sense, having word packing would seem quite expensive for floating-point case. Thankfully, Boolean MM does appear to support only ever having handful of bits (i.e. O(1)) for intermediate coefficients.

Average time is useful because it captures concept of decay and we can rewrite a certain sum of terms assuming (affordably enough) the dynamic structure for ANN always has O(n) points, even if it may have significantly less at certain moments in time.

Our goal is to find the time for cut-out/expiry memoization based on decay and surface area for n-dimensional hypercube and volume for (n - 1)-dimensional hypercube. These values will involve gamma function.

For n equidistant points in n dimensions, distinction between NN-island-based and MST disappears because both are associated with same weight. NN-island-based overall weight for n points bounds the same for n - 1 points in n dimensions. MST overall weight for n points bounds the same for n - 1 points in n dimensions.

Other tasks include Applecare before December, crown, CS 61A and CS 169, certain math subjects, group appointment, trip overseas at close to end of September, paying Pelham pharmacy over the phone, picking up certain side-effect medications early enough, gathering old songs for piano and practicing, getting gym perks card punched, exercise (e.g. basketball), gathering certain materials for classes in high school (e.g. for AP Biology), read books for AP Literature, fixing wrong name for bill for insurance, selling certain odds and ends (e.g. music CDs, high school study aids, graphics book pair), tactile display project, refine portfolio/resume, possibly contact headhunters, retrieve Philos. 138 notebook.

Time is of the essence; we've seen quite a bit of new articles talking about MM. It seems that people may be smelling blood. We will want to implement our approach and post on arxiv.

Relevant resources:

* Chan - Approximate nearest neighbor queries revisited (1998)

* Scott - StackExchange - Manhattan distance vs. Euclidean distance - Answer (2015)

  https://math.stackexchange.com/questions/1168759/manhattan-distance-vs-euclidean-distance

* EuYu - StackExchange - Hypercube maximum distance, graph theory - Answer (2012)

  https://math.stackexchange.com/questions/232713/hypercube-maximum-distance-graph-theory

## 2018-08-27

We tried out other people's implementations for FJLT and figured out that there was an assumption for dot product preservation additive error bound of epsilon which is that norms of input vectors are at most one. This means that for Boolean matrix multiplication that for exact approach the bound we want is epsilon\_old / n. Then, with target dimensionality proportional to 1 / (epsilon ^ 2) = O(n ^ 2 / epsilon\_old), which is much larger than polylogarithmic in n. On the positive side, though, forcing the case that we have unit norm does seem to make the algorithm (for dimensionality reduction) give reliability as good as predicted by many papers in the sense that we often have dot product (s.t. we are less than or equal to one) that stays within small additive error.

It's fun to go after transformations, but probably advisable to hold back on it given that to solve a problem it is often the case that one needs to go after a strength reduction, which is arguable diametrically opposed to finding a reframing of the problem.

## 2018-08-26

We are going to attempt implementing fast Johnson-Lindenstrauss transform with random projections. Then, we will attempt version with Toeplitz and circulant matrices. This is to get a sense of whether distance or inner product invariants with bounded small additive error hold reasonably not just on paper but in practice.

## 2018-08-11

We should note that we finished, for all intents and purposes, remedial work for Physics 24 from freshman year first semester on Wednesday 7/25 afternoon.

Came back from vacation in Iceland for a week from Friday 7/27 night to Friday 8/3 night.

We have found a way to get close-to-optimal time for Boolean MM, i.e. a quadrarithmic-time algorithm for it that doesn't require explicit packing as for bit spread/gather. It's tricky to know how much we need to get done before we should publish and in this sense it's a bit stressful. Part and parcel with the task, I suppose. We are attempting to implement, so there could be hidden issues. Morale boost can come from writing drafts of the article. For the most part, the work is essentially a secret, for now; I wouldn't want to get front-run.

## 2018-06-17

We went back to Physics 24, a freshman seminar with Prof. Jacobsen, from freshman year first semester (Fall 2007).

One thing that had been nagging us was a quote from Feynman about how in the low-intensity double-slit experiment lies "the heart of quantum mechanics" and "[its] only mystery." This is apparently from the Feynman lectures from 1965.

First, we must note that the standard double-slit experiment shows that particles can have wave-like behavior in that corpuscles shot at slits behave s.t. we observe interference much in the way one might expect if we shot corpuscles of water through slits on the surface of a lake.

The low-intensity flavor is, in our opinion, more interesting.

Where is the beef?

We're just going to go ahead and state that we assume that the multiple-worlds interpretation (MWI) is valid; this is to us a particularly colorful way of remembering an appropriate way of making sense of experimental results. In our opinion, there are three meanings of "wave" that we ought to care about. They are to do with (1) imprecision, (2) filled space, (3) multiple worlds. The first is valid when e.g. considering electron orbitals in chemistry given that we assume there are sub-atomic particles flying around in a relatively small region of space. The second is valid from the perspective that particles can be represented as waves and vice versa as we are apt to do in electrical engineering via Fourier analysis. The third is valid specifically to explain sterile environments such as in low-intensity double slit and EPR. We claim that wavefunction (or matter wave) is doing double duty and covers both the first and third types (i.e. imprecision and multiple worlds).

In the low-intensity double slit experiment, if treating the photons we shoot as particles were enough, why would we build up an interference pattern when we avoid determining which slit each particle passed through? Presumably, if each particle stays intact as we shoot them, they should not lead to interference ever.

If treating the photons we shoot as waves were enough, that would explain how we get an interference pattern in the high-intensity case; remember that this was originally the point of the standard experiment from Young in that sometimes we should consider that particles can behave like waves. But this is an inadequate approach for the low-intensity case because we require that the photons we shoot (even allowing for particle-wave equivalence via Fourier analysis) exist as covering point-like regions in space.

Let us assume we use photons to bounce off corpuscles. We know that momentum for the photon is inversely proportional to its wavelength. Resolving power for when we use this photon is also inversely proportional its wavelength and thus is proportional to its momentum. There have been experiments showing that with lower momentum when shooting these measurement-related photons near each slit we get closer to situation where we don't shoot measurement-related photons at all (as we would expect, if we assume that these measurement-related photons are prone to mucking up the paths of the corpuscles by virtue of imparting force). But, with lower momentum means worse resolving power; and it turns out that at the point where resolving power is s.t. we can distinguish between which slit a corpuscle must have gone through to the exclusion of the other, the interference pattern becomes absent and we just have a sum of two peaks as number of samples increases.

With multiple-worlds interpretation, we have mechanism of superposition across worlds. One might attempt as a last gasp to avoid this; say that we treat each corpuscle as an intermediate between particle and wave. Imagine that we have a wavefront emanating from a point source that comes to cover a large expanse and when it interacts with another object it is replaced by a particle. But, as we want to be able to visualize what is happening, would we have the particle that we end up with actually making up the original wavefront in a way similar to what we like to visualize with an electron orbital from chemistry; i.e. we have some traversal pattern and we then use concept of imprecision-based wavefunction? It seems to us personally that it is unreasonable to require that we imagine this traversal pattern that turns a particle in a sterile environment into a possibly large and intricate wavefront prior to collapse unless we come up with some mental aid. And, of course, we should be in compliance with clean probabilities and collapse for the various double slit scenarios.

So, let's say there is a concept of "wave" that we need to introduce that is orthogonal to both of the other two meanings of it that we mentioned before. This "wave" is one that leads us to consider multiple worlds. Let us talk about extremes; i.e. we don't consider where the boundary is between world-related collapse and world-related non-collapse for now (let alone for imprecision-related collapse/non-collapse). Presumably, world-related non-collapse is associated with sterile environment and world-related collapse is associated with what one normally encounters; this is how we arrive at a flavor of correspondence principle. As a reminder, we have correspondence principle for non-world-related small-scale, i.e. non-world-related QM, and for large-scale, e.g. relativity, s.t. they have as special cases intermediate-scale, i.e. classical physics.

Using multiple-worlds interpretation, when we look at low-intensity double slit experiment, we say that upon collapse (i.e. let's just say imprecision-related and world-related collapse are the same) if precision of our measuring equipment is s.t. we can rule out a slit then we are ruling out certain worlds and we effectively select a specific world. Then, that explains why if we collapse at slits we have no interference and if we collapse at recording screen we do.

We use the word "explain" loosely; this effectively is just a mental aid.

Apparently, MWI is compatible with EPR as well; we have world-splitting s.t. one of two entangled particles has a certain spin in one world and a different spin in a second world; once you collapse (and we will avoid talking about what causes collapse specifically), then you know about both particles' states as you've selected a world and as the sum of the spins is fixed. Also, ostensibly this is described as not being non-local.

We should mention the Copenhagen interpretation, by which we really mean a maximally non-committal interpretation. It would then be understandably more popular, given that it is also the case that we currently do not have a way to distinguish between such an approach and MWI based on current experiments (if it is possible at all). By non-committal, we mean this "Copenhagen" approach is agnostic as to giving a name to the mathematical behavior (such as having many worlds). It's been debunked that Feynman has said this specifically, but there are people who have described the default stance of many in the field (which might clumsily fall under the name of Copenhagen) as "shut up and calculate". By avoiding choosing an interpretation that goes beyond just the math, one arrives at what I admit is already present in a clean way in the summary section of Feynman's low-intensity double slit lecture. He describes straightforwardly in words "first principles" that would be sufficient to describe the observed interference/non-interference based on what we know about alternatives that is fairly non-committal and thereby avoids the risk of having some future discovery that breaks our impasse and that could make our decorational term ("many worlds") seem excessive.

Quantum teleportation, used for transferring qubits, uses entanglement.

Quantum cryptography also uses entanglement.

Important features of quantum computers are superposition/indeterminacy and chaining. Armed with the MWI perspective, it becomes easier to imagine why in a sterile environment strategically using pre-collapse particles can be in multiple states at once. Also, depending on your computational approach, we might be entangling in a way specific to your problem and entanglement is something we spend (i.e. we must be able to re-entangle at will).

A result is that we now have a bridge towards understanding the basis for quantum computing. Specifically, we have a sense of why it is plausible that for certain problems quantum computers could lead to exponential speed-up. That is, we could have an incredible number of worlds contributing to a probability distribution. However, we still need to design the algorithm s.t. we recover an answer assuming that we will not spend O(1) time for each world (i.e. a permutation from the search space). Also, we have a sense of why it is plausible that the problems that we can now solve in polynomially-bounded time is still not all of NP.

More concretely, we may also like to start thinking about quantum algorithms.

Relevant resources:

* Topics from quantum mechanics covered briefly (Univ. of Toronto, 2010)

  https://faraday.physics.utoronto.ca/GeneralInterest/QM.html

* Key - Quantum interference (Univ. of Toronto)

  https://faraday.physics.utoronto.ca/GeneralInterest/Key/quinterf.htm

* Key - Quantum mechanics: a poor person's guide (Univ. of Toronto)

  https://faraday.physics.utoronto.ca/GeneralInterest/Key/qutheory.htm

* Harrison - Stern-Gerlach experiment (Univ. of Toronto, 2005)

  https://faraday.physics.utoronto.ca/GeneralInterest/Harrison/SternGerlach/SternGerlach.html

* Harrison - Quantum teleportation (Univ. of Toronto, 2004)

  https://faraday.physics.utoronto.ca/GeneralInterest/Harrison/QuantTeleport/QuantTeleport.html

* Feynman Lectures on Physics - Vol. III Ch. 1 - Quantum Behavior (1965)

  http://www.feynmanlectures.caltech.edu/III_01.html

* Quora - What is Einstein-Podolsky-Rosen paradox and its solution?

  https://www.quora.com/What-is-Einstein-Podolsky-Rosen-paradox-and-its-solution

* Quora - How does the many worlds interpretation of quantum mechanics explain the EPR paradox?

  https://www.quora.com/How-does-the-many-worlds-interpretation-of-quantum-mechanics-explain-the-EPR-paradox

* Quora - What is the Copenhagen interpretation?

  https://www.quora.com/What-is-the-Copenhagen-interpretation

* Mermin - Could Feynman have said this?

  https://physicstoday.scitation.org/doi/10.1063/1.1768652

## 2018-05-07

Parallelism.

parallelism for construction and memoization should probably work in same overall time; except, now that we possibly have parallelization for all phases, larger n should be more commonplace (due to more acceptable concrete time used) and we should be able to reach parts of the time curve where we are significantly more favorable, even after taking into account constant factors for our algorithm

What do the below resources mention?

Finished Pride and Prejudice on May 4th, 2018.

Got root canal done in China.

Relevant resources:

* Datta - Efficient parallel algorithms for geometric k-clustering problems (1994)
* Cole - Parallel merge sort (1986)

## 2018-04-07

I'm in China right now.

I figured I should note some things that I've come across recently.

Apparently, deep neural networks (DNN's) can be formulated in a way that makes heavy use of matrix multiplication, according to a recent article from EE Journal.

Also, an Abstruse Goose comic recently came out that talks about the link between lucrativeness, general AI, matrix math, undergraduate math, working "by one's self" in a bedroom.

Still doing remedial work.

Resources:

* Abstruse Goose - The $25,000,000,000,000 Matrix (April 2, 2018)

  http://abstrusegoose.com/583

* Leibson - EE Journal - Fifty (or Sixty) Years of Processor Development...for This? (March 29, 2018)

  https://www.eejournal.com/article/fifty-or-sixty-years-of-processor-developmentfor-this

## 2018-01-31

We should note that for rectangular matrix input case s.t. we have A as a n\_1 x n\_2 matrix and B as a n\_2 x n\_3 matrix, we have a more detailed cross-over condition that treats square matrix input case as a special case.

Before, brute-force time is O(m / n \* n ^ 2) = O(m \* n), where m is number of input non-zeroes. Rader-NTT-hybrid-related magic bits determination for fancy approach takes time O(n \* polylog(n)). Assuming O-tilde is O(n ^ 2) at worst, cross-over m is O(n) or O(n \* polylog(n)).

Then, with rectangular input matrices, brute-force time is O(m / (n\_1 + n\_3) \* (n\_1 \* n\_3)), where m is number of input non-zeroes in either A or B. Rader-NTT-hybrid-related magic bits determination for fancy approach takes time O(n\_2 \* polylog(n\_2)). So, what is cross-over m? Assuming O-tilde is O(n\_1 \* n\_3) at worst, O (non-tilde) is O(n\_1 \* n\_3 \* polylog(n\_1 \* n\_3)). Setting the brute-force time to O-tilde time based on max. output number of non-zeroes, we get m equal to O((n\_1 + n\_3) \* polylog(n\_1 \* n\_3)). Then, cross-over m is max((n\_1 + n\_3) \* polylog(n\_1 \* n\_3), n\_2 \* polylog(n\_2)). Note that this degenerates for square case s.t. for n\_1 = n\_3 = n\_2 == n, cross-over m is again O-tilde of n or O(n \* polylog(n)). We have one last step; we are wondering whether if we can't afford Rader-NTT-hybrid-related magic bits determination, that brute-force-designated time (i.e. left of cross-over after introducing the max operator) is still in O-tilde of n\_1 \* n\_3. Is this the case? No, it isn't. However, we still have time softly quadratic in max(n\_1, n\_3, n\_2) and this is satisfactory. To reiterate, the cross-over m that we give is possibly s.t. times resulting from being on brute-force-designated (i.e. left) side of boundary could be huge as n\_2 can be arbitrarily large, given that n\_2 is independent of n\_1 or n\_3.

We should remind ourselves that rectangular matrix product is also a case of sparse square matrix product.

High n\_2 relative to n\_1 and n\_3 means high left-of-boundary, relatively speaking. Low n\_1 and n\_3 relative to n\_2 means low right-of-boundary, relatively speaking.

## 2018-01-28

We somehow got a burst of reputation points for various StackExchange sub-organizations, so we have enough to start posting comments for CS Theory subject. We did so for a conversation between Blaeser and Jeffε.

We are unsure as to how to tackle sparsity. We know that if n\_{non-zeroes, A} and n\_{non-zeroes, B} (i.e. for input matrices A and B) are <= n, the worst-case output non-zeroes is n ^ 2 and time in O(n ^ 2). However, at the other extreme, if we are not unlucky, for this case, we have output non-zeroes equal to one and time in O(n). We just barely reach worst-case time of O(n ^ 2) with the two caps on number of non-zeroes for A and B, so when we surpass the caps, we can resort to our fancy algorithm, which guarantees time softly quadratic in n. Conveniently, also, magic bits for Rader-NTT-hybrid takes O(n \* polylog(n)) time to generate, which is close to the boundary we have erected between brute-force and our fancy approach. We should note that this could be not as big of a deal if we have many same-size input matrices to find product for as we can re-use the Rader-NTT-hybrid-related magic bits.

We should note a distinction between output trivial zeroes and non-trivial zeroes; the latter is due to cancellation. We don't actually use this concept much for our current f.p. MM approach, though, as we are not output-sensitive for this first pass.

In many papers, we see that so-called sparse approaches for MM don't actually seem to provide time better than O(n ^ 2) except brute-force, which guarantees O(n \* n\_non-zeroes) time. They seem to mainly have speed-up assuming omega is not two (i.e. our ability to attain omega approximately equal to two makes these approaches less appealing). This includes Lingas; Yuster and Zwick; Le Gall; Jacob and Stoeckel; Amossen and Pagh. On the other hand, we might be deceived s.t. the bounds involving O(n ^ 2) may not necessarily be tight.

We might wish to also consider output non-zeroes if we have a fast way of estimating. However, we are reluctant to use existing methods (e.g. from Cohen or Amossen et al.) because they are randomized and approximate (i.e. at any given time may be totally wrong or not totally wrong but not exact). How we might use this information is to be able to consider minimal number of A-row-B-column pairs s.t. dense approach can be informed by the need to only consider these pairs and we get perfect exploitation of sparsity and get good time, except we also have to consider time for one-time operations, like determining Rader-NTT-hybrid-related magic bits, and time for finding output non-zeroes. This said, having affordable way to find output non-zeroes consistently and exactly almost seems like it would be too good to be true.

We should note that rectangular matrix multiplication can be viewed as sparse square matrix multiplication.

Also, we should note that one way of concisely interpreting our first-pass approach that takes advantage of sparsity is that we have time roughly optimal across worst-case configurations with given number of input non-zeroes; i.e. we have a gap between n and n \* polylog(n) which we could ignore, partially because there is precedent in that omega ignores polylog(n) factors. Alternatively, we could instead of having a boundary at n\_non-zeroes = O(n), we can have one at n\_non-zeroes = O(n \* polylog(n)) and the cross-over in terms of time would be more seamless. Since it seems unreasonable to currently believe omega can be two (i.e. not softly) without polylog(n) factor, one way to reasonably refine the description of our behavior is to say we have O-tilde time that is optimal across worst-case configurations with given number of input non-zeroes s.t. O-tilde hides polylog(n) factor.

Brute-force approach leads to O(n \* n\_non-zeroes) time for square input matrices of size n x n because then (s.t. n\_{non-zeroes, avg.} is number of non-zeroes per A row or B column) n\_{non-zeroes, avg.} \* n ^ 2 = O(n\_non-zeroes / n \* n ^ 2) = O(n\_non-zeroes \* n). Evenly distributing non-zeroes across A rows and B columns leads to maximal blow-up in time and we argue that under no circumstances is uneven better than even for blowing up time. This time is corroborated by many sources - e.g. Yuster and Zwick; Lingas; Buluc and Gilbert.

Again, we can place less emphasis on the O-tilde time for boundary between brute-force and our fancy approach being compatible with time needed for Rader-NTT-hybrid-related magic bits determination given that it seems somewhat reasonable to expect that we deal with same-size matrices s.t. we can determine the Rader-NTT-hybrid-related magic bits once and re-use them.

We still have not attempted non-SIMD, i.e. multiple-instruction-stream (e.g. MIMD), parallelism; parallel construction of 2-D range tree with fractional cascading seems to be the main challenge and (at some level) it seems unlikely to not be possible; however, it is possibly not the best subject to spend our time on at the moment, as if the rest of the f.p. MM algorithm works out, it will still have been a good accomplishment. If we get the that point, then we can choose to keep MIMD on backburner and chip at it gradually.

Again, we plan on returning to CS 61A material; this spurt of effort should be considered out of the ordinary, as it was nagging at us to find some consistent strategy for at least marginally exploiting sparsity for f.p. MM. Also, again, it's great that we have a blog so that we can change subjects for our attention on a dime.

Conversation from StackExchange:

* Blaeser - StackExchange - Complexity of computing the discrete Fourier transform? - Answer (2011)

  https://cstheory.stackexchange.com/questions/8196/complexity-of-computing-the-discrete-fourier-transform

Sparse MM resources:

* Amossen and Pagh - Faster join-projects and sparse matrix multiplications (2009)
* Pagh - Compressed matrix multiplication (2013)
* Le Gall - Faster algorithms for rectangular matrix multiplication (2012)
* Yuster and Zwick - Fast sparse matrix multiplication (2005)
* Buluc and Gilbert - Highly parallel sparse matrix-matrix multiplication (2010)

Output non-zero estimation for MM resources:

* Amossen, Campagna, Pagh - Better size estimation for sparse matrix products (2010)
* Jacob, Stoeckel - Fast output-sensitive matrix multiplication (2015)
* Cohen - Structure prediction and computation of sparse matrix products (1998)

## 2018-01-18

A problem is that we are exploiting sparsity, but magic bits for Rader combined with NTT require time big-omega of m \* polylog(m) time; m \* polylog(m) is in O(n \* polylog(n)); this means that we might not be able to take advantage of when number of non-zeroes is around less than n; we are not exploiting sparsity as much as we could unless we can come up with Rader-NTT-hybrid magic bits more quickly, which may be possible, but requires further investigation.

Also, we should note that we have not begun to consider processor parallelism; we are partly embarrassingly parallel, but not entirely (e.g. construction of 2-D range tree; as opposed to queries, for which we are embarrassingly parallel).

Also, we should note that we are not yet taking advantage of caching.

We are going to take a break and address lower-hanging fruit. This means less fast MM, numerically robust 2-D order-1 Voronoi and order-k Voronoi. This also means that we will divert energy towards CS 61A material and CS 169 MOOC. We note that this decision is partially driven by the realization that our internal ETA for order-k Voronoi is essentially infinity at the moment. Thank goodness we have a blog to help us change course more nimbly.

## 2018-01-17

The Zhang article mentions that Ben-Kiki has described an O(1)-time algorithm for finding left-most set bit in a word.

We note that word RAM does not directly give us good f.p. MM time, but it gives us flexibility.

Zhang tells us how to convolve in word-packed manner without going through FFT. We use direct definition of linear convolution, which leads to a time-domain signal, and re-write in terms of "diagonals".

We might think we are stuck, but then we can refer to Rader's FFT algorithm, which defines DFT (and possibly NTT) in terms of cyclic convolution. We can then define cyclic convolution in terms of linear convolution using "cyclic prefixing". We use a prime size for cyclic convolution equal to or larger than our given size. An alternative is to use Bluestein's FFT algorithm.

We determine "magic bits" for Rader-related partner signal once for each layer, of which we have at most five; we re-use these signals quite often. So, it is okay for the work for these signals to not involve time that benefits from the values being word-packed.

Crisis averted! We might still be able to use Zhang and we do so to implement NTT.

We still need to know whether Rader can be combined with NTT; and we have to accept another requirement - i.e. that Rader needs a prime size.

Relevant resources:

* Ben-Kiki et al. - Towards optimal packed string matching (2014)
* Dunna - How do I convert circular convolution to linear convolution? (2017)
* Rader - Discrete Fourier transforms when the number of data samples is prime (1968)
* Wikipedia - Rader's FFT algorithm
* Wikipedia - Convolution - Discrete convolution
* Wikipedia - Cyclic prefix

## 2018-01-13

Thankfully, we are safe w.r.t. Zhang word-packed NTT-based convolution. The time, from perspective of our application (f.p. MM), is O(m / m' \* log(m) \* log(m / m' \* log(m)) = O(m / m' \* log(n) \* log(m / m' \* log(n))), which leads to bottleneck time of our algorithm at around O(n ^ 2 \* log(n) ^ 2 \* log(m / m' \* n)) (as opposed to O(n ^ 2 \* log(n) ^ 3)). Of course, if m = O(m'), as is often the case, then we have a time of O(n ^ 2 \* log(n) ^ 3), again.

## 2018-01-12

Our goal is to find out time for NTT with support for full range of values describable by a word-packed floating-point number. We should remember that we also care about absolute upper bound on number of words to support such input floating-point numbers. We will assume the word size is interchangeably m' or w.

For the following, we are in general discussing FFT.

We assume that a is input coefficient max. magnitude and b is vector length.

### Time for our application

For forward FFT (via WHT, complex, NTT), output coefficient magnitude is bounded by b \* a. For convolution of two time-domain signals with same input coefficient max. magnitude and vector length, output time-domain signal coefficient magnitude is bounded by b \* a ^ 2 (for intermediate calculation, magnitude is bounded by (b \* a) ^ 2).

Next, we add a detail: a == 2 ^ m.

T_1 = log(b ^ 2 \* a ^ 2) / m' = (2 \* log(b) + 2 \* log(a)) / m' = (2 \* log(b) + 2 \* log(2 ^ m)) / m' = O((log(b) + m) / m')

Then, we make an assumption: m = O(m').

=> T\_1' = O(log(b) / m')

And we would stop here, except if we make a second assumption: b and m are related s.t. b = O(m).

=> T\_1'' = O((log(m) + m) / m') = O((2 \* m) / m') = O(m / m') = O(1)

This means that if we make the two previous assumptions, FFT time is:

T\_2'' = O(b \* log(b) \* T_1'') = O(b \* log(b))

We note that if, instead of b, we prefer the letter n, we have time of O(n \* log(n)).

### Pitfall from a particular thread

We deviate from what turned out to be an assumption made by someone else that at one point in time made us worry that the time for FFT is possibly O(n \* log(n) ^ 2). We don't have enough karma to post a comment directly to someone else, so we are recording our logic for posterity here. We should note that the assumption of significand size b = O(log(n)) is totally arbitrary. An equally plausible situation is b = O(w). Then, assuming we have floating-point numbers that fit in a word (of size w) and assuming that word operations generally take O(1) time each, time will be O(n \* log(n) ^ k) with k == 1, given that we want to support all numbers representable by such a floating-point number. Also, of course, Blaeser is being generous to Jeffε s.t. technically O(n \* log(n)) is in O(n \* log(n) ^ 2).

Ultimately, the point is that they made a specific assumption that does not apply for our application; we should also note that they ascribe different meaning to the variable b; they have it as output significand size in bits and we say b is size of input vector.

### About conventions

A second source describes bound for each output coefficient for NTT-related convolution.

Nayuki adheres to convention that convolution is s.t. we take two time-domain vectors and return a time-domain vector.

Also, they say that if we have as input two vectors of length n s.t. each input coefficient is at most m, we have an upper bound on each output coefficient of m ^ 2 \* n.

They are talking about starting with pre-NTT vectors for the input and the output is after inverse NTT; we go from (n \* m) ^ 2 to m ^ 2 \* n because for inverse FFT, we divide coefficient upper bound by n.

### Next step

We can proceed with Zhang; we will need to justify the time and steps for it.

### Other

Also, due to Bertrand's postulate, we get good proximity to a prime for NTT.

Resources:

* Blaeser - StackExchange - Complexity of computing the discrete Fourier transform? - Answer (2011)

  https://cstheory.stackexchange.com/questions/8196/complexity-of-computing-the-discrete-fourier-transform

* Project Nayuki - Number-theoretic transform (integer DFT) (2017)

  https://www.nayuki.io/page/number-theoretic-transform-integer-dft

## 2018-01-10

We have to remember that we have two staircases for each point arrangement, of which we have two.

We realized that for a 2-D range tree, we don't have overall O(n) leaves for lower-level trees unless we use fractional cascading. Then, we will do so and choose an arbitrary lower-level leaf for each of O(n) points and make sure that we do so consistently. This cuts down range-tree contribution polylog(n) = O(log(n) ^ 2) to O(log(n)), which keeps the bottleneck polylog(n) factor at O(log(n) ^ 3). We note that we had a factor of O(log(n) ^ 2) already due to inflation from multiple passes of FFT.

A big problem is to be able to encode into or decode from binary RLE form for each memoized (not path-related) signal for nodes. We don't want to cause for time to have another O(log(n))-factor. Instead, we can convert signals into binary RLE form in time linear (and not involving a factor of O(log(n))) in number of non-all-zero words in signal. For conversion, we perform "spotting" (in the sense of the word "identifying") by skipping across all-zero or all-one words and eating into the interior side of a boundary word to get all-one or all-zero repeats quickly, which can be done via "bit-finding" operations: (1) O(m / m')-time (which is constant if m = O(m')) right-most one bit for NOT'd signal determination; or (2) left-most zero bit determination. For the former, we don't use Anderson and we do use Shankar, which uses XOR and AND and subtraction. For the latter, we normally have to reverse tiles which takes O(m / m' \* log(m')) time and use right-most one bit for NOT'd version of this reversed signal. This means we incur a cost of log(n) at a bottleneck, leading overall polylog(n) to be in O(log(n) ^ 4); instead, we reverse tiles immediately after multiple FFT passes are altogether done and maintain them so that we don't incur this extra O(log(n))-factor cost for RLE overlay operations when we are doing sum-related memoizing for lower-level leaves in 2-D range tree. Then, we incur an extra O(log(n))-factor cost for after multiple FFT passes altogether (which had overall polylog(n) = O(log(n) ^ 2)), leading the time for immediately after multiple FFT passes altogether to be overall polylog(n) = O(log(n) ^ 3), which is tolerable. We don't use expensive logarithm for the "bit-finding" operations; we go from shifted one-bit, which we get from "bit-finding" operation and go to mask directly, without finding binary offset from right or left edge of word.

An important step towards having this suitable time is to be able to find right-most one bit for NOT'd signal or left-most zero bit in constant time (or, specifically, O(m / m') time) instead of O(log(w)) (where we are interchangeably using m' and w). This allows us to replace runs with code-words efficiently, assuming that we have a threshold for turning repeated zeroes (or ones) into runs s.t. we do so if the number of repeats is at least w. The binary RLE form can also be a list without incurring asymptotically more space or time cost because of this threshold.

When we have binary RLE forms of signals, we can avoid encoding/decoding steps by being able to perform addition via overlay directly for two operand binary-RLE-form signals and we get back another binary-RLE-form signal. We estimate that the time for this will be linear in twice the number of non-zero words in the modifying RLE associated signal via middle-man code-words (we note that this needs a more detailed proof), assuming runs have min. length of w.

We are essentially dealing with topology for RLE-related encoding, overlaying, and trie preparation in the sense that we do for e.g. higher-order Voronoi via Zavershynskyi/Papadopoulou and their detailed circle events.

We note that a maximally-large sequence of adjacent non-runs is technically a code-word (i.e. it is a "glial" code-word).

We are starting to get some hope that we will attain time complexity of O(m / m' \* n ^ 2 \* log(n) ^ 3).

How do we prepare binary RLE trie and use it during a query to quickly get a final (i.e. totally completed for an output cell) floating-point scalar? This question is an urgent one; we mistakenly assumed that trie query will give us the final answer, when in fact we still have union-intersection arithmetic, which can involve subtraction and thus catastrophic cancellation. However, perhaps we can instead push adding of row or column "source sizes" to lower-level-leaf memoizing phase s.t. signals have sign negated and have row or column "source size" (based on whether we have for a leaf a point for a row or for a column) signal added.

For including row and column sizes during memoizing time, we have for O(n) children an operation that costs O([(m \* n) + (m \* n)] / m') = O(m / m' \* n) time; this is due to having first subterm via summing components for a row or column and second subterm via size of a one-bit run. This way, trie query will give us final answer without more muddling about with floating-point exactness.

Important remaining questions:

* How exactly do we "spot" and convert to binary RLE form quickly? (We know that it is probably possible, but we have to be very clear.)
* When do we apply Parseval's theorem multiple times?
* When do we apply (false?) interleaving/de-interleaving?

Edit: As for how we apply interleaving/de-interleaving, we do the following.

We should remember that we have false de-interleaving in between FFT passes; this leads to overall polylog(n) = O(log(n) ^ 3). However, while space inflation affects de-interleaving time, de-interleaving does not affect space inflation, so we can proceed with O(log(n))-time reversing for each word and still have overall polylog(n) = O(log(n) ^ 3).

We merge inflation-related signals as part of summing-memoizing for 2-D range tree nodes; we already factored in the time increase needed (of a factor of O(log(n) ^ 2)) as part of later steps; different same-component-same-row-or-column contributors are shifted by single powers of two; we benefit from each such signal being of size O(m) s.t. we still can take advantage of word-level parallelism and divide m by m'.

In a sense, because we use false interleaving and we are lucky with sizes being O(m), we don't need re-interleaving and can just shift and add; what about shifted word boundaries, though? We respond by having word-parallel bit-shift for these inflation-related size-O(m) signals.

We may now, then, have next the step of somehow finding word-packed NTT FFT via Zhang.

Edit: We haven't actually figured out if Zhang gives us convolution without FFT or it gives a faster FFT. The former is more tricky to make use of.

Relevant resources:

* Anderson - Bit twiddling hacks - Finding position of highest bit set (2005)
* Shankar - Stack Overflow - How to get position of right-most set bit in C (2016)

## 2018-01-09

We have made quite a bit of progress.

We have figured out a way to have exact floating-point arithmetic tailored for our application. It does not use Kahan summation or Kahan-Babuska summation or Demmel-Hida.

The key is we use binary run-length encoding (RLE) for signals stored at each node. The concern is that when we add, we are allowed to spend time related to the size of the modifying signal, but cascading overflow can be very expensive. This is not the case with RLE. For the boundary of the modifying signal, we eat into code-words within a boundary word (or spanning a small number of boundary words) and each code-word is quite small and has size related to n and m; we can also opt to only consider repeated 0's or 1's a run if they are at least the size of a word (in terms of bits).

Binary RLE can be used for not only addition, but subtraction; in the latter case, we possibly have cascading underflow and possibly repeated ones, which can be marked by a flag.

We memoize path-related values for each lower-level leaf in "union tree". There are O(log(n)) paths involving a lower-level leaf bleeding into both layers (lower and upper) and involving a node that is some descendant (or identical to) the upper root. Our main concern here is that the operation be affordable enough; our tactic is to sum signals for whole path (from a leaf to upper root) and then subtract starting at upper root and moving down to the specific leaf. This is a way of making sure our overall polylog(n) factor is in O(log(n) ^ 3); this time also takes into account inflation of signal size by a factor of O(log(n) ^ 2) due to multiple passes of FFT.

Also, for FFT, we note that if we wanted to collapse signals earlier (which we don't), we can do so cleanly if we require that vector sizes are powers of two (because then we reduce size of signal in a kind of application of inverse FFT via Parseval's theorem by bit-shifting right and we have satisfactory, i.e. unchanged, number of words or tiles involved after collapsing); this repeated rounding to nearest larger or identical power of two between logarithm applications affects binary iterated logarithm s.t. we have identical behavior as binary iterated logarithm because the right bound for each interval for a given output value in [0, 5] is itself a power of two. At any rate, we drop this aspect because we have a way of making determination of path-related memoized values for each lower-level leaf cheap enough already (as described in previous paragraph).

This trick that saves us time for path-related memoized values mentioned two paragraphs ago is our third instance of "inverting a universe", so to speak.

We have a way of pre-processing to speed up subtraction s.t. we can use it to combine two (possibly differently-signed) memoized values via addition (resp. subtraction) quickly enough for query time; for this, we use a compressed trie with edges corresponding to words (and not code-words from previous binary RLE). We have to return to this later.

Also, as we previously hinted, we want to avoid depending on having vectors have lengths that are powers of two. This is why we chose to have the path-related memoized values for each lower-level leaf determined using full sum and gradually subtracting as we move in a second pass from upper root to the leaf.

We don't use super-accumulator; we have no fear of overflow due to having binary RLE (though the details we need to go into again - addition-related cascading overflow never proceeds to the left past a zero and subtraction-related cascading underflow never proceeds to the right past a one and we can have repeating one bits for subtraction case, for which we can have a flag). However, we had widened bins so that we could temporarily avoid cascading overflow for a canonical number and this is similar to having super-accumulator; also, we figured out that larger offsets s.t. we have two bins for each power of two instead of O(log(n)) can be easier to work with. At any rate, we no longer pursue super-accumulator (because, again, we have binary RLE). And, of course, we are assuming that wherever necessary, we have word-level parallelism s.t. we divide time by w (or as we have taken a liking to saying instead - m').

An advantage of the fully-specified approach is that we have two values to combine for any given query; this way, we can straightforwardly use trie to find sum of the two values if the two values have opposite sign or some more straightforward way for if the two values have the same sign (i.e. in this case, there is no catastrophic cancellation).

We still have to figure out how to deal with repeating-one suffix flag that we may encounter for trie for query-time subtraction.

A problem that remains is how to convert to binary RLE form and back in bit-wise parallel.

## 2018-01-07

We currently have compressed trie with LCA with widened bins to avoid cascading overflow and tiles.

We thought we could replace this with sort-less Kahan summation with meta-floats and tiles, but we did not notice that the error is acceptable only if condition number is small. In practice, condition number can be huge. This is even if we carefully choose allowed relative error and machine epsilon, which both are based on significand size in terms of bits.

We believe we can make do with generalized Kahan-Babuska summation because while we do some sorting, it is very local; there is only one loop even with order equal to two. This means that the algorithm, even for higher orders, is embarrassingly parallelizable. This in turn means that it is more straightforward to divide work between nodes and later combine.

Edit: It turns out that Kahan-Babuska has accuracy not independent of condition number, as well. So, we are stuck.

Articles of interest:

* Klein - A generalized Kahan-Babuska-summation-algorithm (2005)
* Zhu et al. - A new distillation algorithm for floating-point summation (2005)

## 2018-01-05

We need to revise f.p. MM article and come up with diagrams. Unfortunately, I don't have access to a drawing tablet currently; so, we will have to draw on paper and then scan the pictures. Through this process, we will hopefully get a better picture of the details for the algorithm (e.g. in what manner do we apply FFT, take advantage of packing, and use bit de-interleaving and use tiles).

It snowed quite a bit yesterday and it is quite windy outside today.

## 2018-01-02

We had a small moment of doubt when it comes to Nuetzi hybrid de-interleave, but it turned out that we were double-counting a log(n) factor.

Zhang NTT FFT describes word-packed convolution; we can, if necessary or if only to make appropriating of the technique mentioned in the article easier, view Fourier transform as a special case of acyclic (or padded cyclic) convolution s.t. one vector is all ones.

Also, we note that Nuetzi hybrid approach that we mention requires that the vector size be a power of two; we can use zero-padding for this.

Also, we found copies of Anna Karenina and The Count of Monte Cristo.

## 2017-12-30

We believe we have an approach for floating-point MM that takes time O(m / m' \* n ^ 2 \* log(n) ^ 3).

We had to add a lot of details for having exact floating-point summation.

The result is that the cross-over point relative to brute-force MM is approximately c \* 981 for small c; c could be, say, 15.

## 2017-12-18

It turns out that we need to modify both our floating-point MM article and details previously added to this blog.

We wish to have p-way q-bit interleaving and de-interleaving and with history; as it turns out, our standard p-way q-bit approach does not have history. Also, false p-way q-bit interleaving (i.e. without any interleaving at all) supports history in a fairly straightforward way. Also, we have reason we like false approach irrespective of history support - it is free, as opposed to introducing a factor of log(n) ^ 2 to one of our bottlenecks, which prevents overall factor from becoming log(n) ^ 5, and keeps it at log(n) ^ 3.

Also, polylog(n) factor for repeated FFT passes and iterated logarithm is in O(log(n) ^ 2), not O(log(n)); this is a result of having at most around five FFT passes.

Also, we still have Demmel-Hida-related log(n) factor.

If we are still interested in showing time for standard p-way q-bit interleaving, we should assume (if we assume at all) that p = O(n) and q = O(m \* log(n) ^ 2), not that q is just in O(m \* log(n)).

Also, of relatively great importance is to note that narrowing of downward filter makes finding complements for a node affordable enough; this is not just for rational case; it is for floating-point case, as well. The concern is that in the worst case, we cannot just pre-maturely truncate, as finding complement (i.e. by subtracting union) means the result significand could move quite far to the right before we get a result one bit for later use for a query.

A current goal is to implement standard p-way q-bit bit interleaving and de-interleaving (s.t. we use magic bits) anyway.

## 2017-12-15

We can have p-way q-bit bit interleaving (i.e. n-d Morton code) via three possible ways:

* Brute-force - time is O(m / m' \* p \* q)

  We spend O(1) time per bit, of which there are p \* q. We are fairly fine-grained and we even generously assume we have blocking. This is too expensive.

* Nuetzi original - time is O(m / m' \* p ^ 2 \* log(p) \* log(q))

  This is good for d = 2 s.t. p == 2. We use pre-computed magic numbers, but we are too coarse by having expanded signals. This is too expensive.

* Nuetzi hybrid - O(m / m' \* p \* log(p) \* log(q))

  Presumably, we pre-determine calculate magic numbers for each unique level in the n-d Morton code call tree. This is cheap enough.

m is essentially q and m' is word size.

Nuetzi approach is 2-way q-bit bit interleaving.

The two Nuetzi approaches use divide and conquer.

These approaches have been for forward Morton code transform, but we can also have the same times for reverse Morton code transform as long as we replace 2-way q-bit bit interleaving with 2-way q-bit bit de-interleaving. The latter we have not come across a general approach for, though we can deduce what we would need by extrapolating existing approaches for certain fixed bit-sizes that we have come across.

Also, we don't quite understand how Zhang packed FFT works, but it is likely better than un-packed FFT or else they would not have published it.

Current resources of interest:

* Anderson - Bit twiddling hacks - Interleaving bits (2005)
* Giesen - Decoding Morton codes (2009)
* Nuetzi - How to compute a 3-d Morton number (interleave the bits of 3 ints) (2013)
* Nuetzi - Produce interleaving bit patterns (Morton keys) for 32-bit, 64-bit, and 128-bit (2013)

## 2017-12-10
Working on a number of projects.

The idea behind this is that, presumably, we have a tighter feedback loop s.t. we make changes more (even if just in sentences) and lower the threshold to making forward progress. On the other side, however, our changes are visible for all to see. At some level, though, this downside may be something that would have cropped up anyway by the time we came up with a more robust solution (with a history).

Projects

* Hoedt/Arndt/Giesen - p-way q-bit interleaving (i.e. n-d Morton code)
* Zhang - packed NTT
* Voronoi - sweep-line approach with numerical robustness, overlay, polygon pointers, point location
* order-k Voronoi - sweep-line approach by Zavershynskyi and Papadopoulou
* fast floating-point MM - with certain assumptions, we can have sub-cubic time
* portfolio - possibly use Flex with prism theme and state-transition diagrams	
* CS 61A (Fall 2007) - go through exercises and projects
* Close-prime-finding algorithm and time guarantee?
* edX - software engineering (i.e. CS 169) for SaaS and with agile and RoR - basics, advanced, certificate?
* coursera - func. prog. principles in scala
* collect documents about Addteq
* brush up on par. programming with intrinsics?
* follow up by contacting headhunters?
* ship sold book
* donate unsellable items (e.g. music cds, dated books)
* organize emails more
* update resume and job profile
* play piano
* watch bleach? (there are 16 seasons and four movies)
* organize photos
* finish assigned reading from senior year (Fall 2006 to Spring 2007) AP English Literature
* find classwork for high school junior/senior years and preserve/bundle (e.g. for AP Biology for junior year and Lit. 12 for senior year)

Papers

* Zhang - Fast convolutions of packed strings and pattern matching with wildcards (2017)
* Zavershynskyi and Papadopoulou - A sweepline algorithm for higher order Voronoi diagrams (2013)
* Fortune - A sweepline algorithm for Voronoi diagrams (1987)

There are, of course, many more papers for fast MM.

Questions

* Should we add more personal details - e.g. course history, apartment buildings lived at, books read?
* Should we attempt Project Euler?
* Which projects and for which classes should we go over again?
* Should we add past project details - e.g. fixing laptops, tactile interface, etc.?
* Should we add more projects - e.g. IoT kit, mirror interface, 3-d printing device?
* Should we write more about past internships - e.g. Alzatex, LTT, Cohorti?
* Should we write about certain company-specific HackerRank competition problems and our solutions for them?
* Should we write about job interviews and technical questions?
* Should we write about high school projects - e.g. for robotics, invention program, student government?
* Should we write about how we spend our leisure time - e.g. television, movies, music, sports, traveling, family?
* Should I keep a list of movies watched?

Miscellaneous

* BU book club (Fall 2017) - have read The Nightingale, In Cold Blood, Before the Fall, Persuasion, part of Boston Noir
* AP English Lit. reading - Brave New World, Pride and Prejudice (done), Oedipus, Heart of Darkness, The Return of the Native, Hamlet (done), Mythology (done), Uncle Vanya, Great Expectations (done), My Antonia (done), Macbeth (done), The Importance of Being Ernest (done), Crime and Punishment, Madam Bovary
* have not obtained - An Introduction to Fiction (Kennedy/Gioia, 9/10), Sound and Sense (Perrine, 9/10/11)

Private matters

* medication - clozapine (200mg nightly, dispensed at clinic), glycopyrrolate (2mg nightly), oxybutynin (5mg nightly), docusate (50mg occasionally), senna (8.6mg occasionally)
* phlebology - once every two weeks
* psychologist - once every two weeks
* family appointment for psychologist coming up (jan. 22, 2018 at 11am)
* make appointment to see endodentist for root canal and crown for tooth #15 (upper molar); attempt to compare prices given that current dental insurance does not cover these two operations at all

Addendum

We thought that we would need Rader FFT (which is noted to be compatible with NTT) given that we have unusual-size signals (i.e. not power of two). Instead, we can just zero-pad and take advantage of concavity and say that our time is worse by a factor of slightly more than two. The idea is that Fourier transform is defined even if signal size is not a power of two and if for some reason we want a non-padded post-Fourier-transform signal, this would imply that we ought to use Rader or Bluestein. Again, we are content with zero-padding the time-domain signals. 

The papers associated with Nevin that were of interest to us were:

* Rader - Discrete Fourier transforms when the number of data samples is prime (1968)
* Nevin - Application of the Rader-Brenner FFT algorithm to number-theoretic transforms (1977)

It occurred to us that we mistakenly took two articles about n-dimensional Hilbert transform as for n-dimensional Morton code. However, while we have encountered a setback, it also occurs to us that we might be able to define n-d Morton code via recursive application of 2-d Morton code transform, the implementation of which is more often mentioned. Also, we should note that the point is to use word-parallel approaches (i.e. those that use "magic numbers"). By using repeated 2-d Morton code transform, we may need to zero-pad, with an extra cost of around a factor of slightly more than two.

The papers associated with n-dimensional Hilbert transform that we were interested in were:

* Lawder - Calculation of mappings between one and n-dimensional values using the Hilbert space-filling curve (2000)
* Skilling - Programming the Hilbert curve (2004)

A final pressing concern is: is Zhang packed FFT really enough, given that the factor u is related to max. component magnitude and alphabet size, even if we are word-parallel?


