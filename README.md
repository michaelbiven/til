# Maps

_A guide and collection of notes of how to apply maps to operations._ 

**Copyright** (c) 2019, Michael Biven. All rights reserved.

## Table of Contents
- [Introduction](#introduction)
- [Wardely Maps](#wardely-maps)
- [Graphviz](#graphviz)
- [References](#references)
- [Appendix A](#appendix-a)
- [Appendix B](#appendix-b)

## Introduction



## Wardely Maps

The **Where**, **Why**, **How**, **What**, and **When**. With **Where** and **Why** making up situational awareness and the **How**, **What**, and **When** making up the action.


> variety of skillsets within an organization to address varying activities ranging from research and invention (pioneer); to organization and productization (settler); to industrialization and standardization (town planner)

**Value Chain**: a chain of needs — (users, needs, and capabilities arranged and connected according to dependency) mapped against the four stages of evolution (Genesis, Custom, Product, and Commodity).

**Evolution**: Genesis (uncharted) » Custom » Product » Commodity (industrialized)

**Time Chain**: Invisible «» Visible

**Genesis**: chaotic, uncertain, unpredictable, changing, different, exciting, future worth, differential
to…

**Commodity:** ordered, known, measured, stable, standard, dull, low margin, essential

- Evolution = Change = Movement
- Purpose, landscape, climate, doctrine, and leadership.
- Evolve: early adopters versus lagards.
- Peace, War, Wonder
- Inertia from past success
- Uncertainty between What and When
- duplication versus bias
- Fast, Inexpensive, Simple, Tiny (FIST) Dan Ward Simplicity Cycle
- technical domain
- components

## Graphviz

https://graphviz.org/about/

```
$ brew update && brew install graphviz
$ dot -h
$ cat <<EOF >> graph.dot
digraph G {

	subgraph cluster_0 {
		style=filled;
		color=lightgrey;
		node [style=filled,color=white];
		a0 -> a1 -> a2 -> a3;
		label = "process #1";
	}

	subgraph cluster_1 {
		node [style=filled];
		b0 -> b1 -> b2 -> b3;
		label = "process #2";
		color=blue
	}
	start -> a0;
	start -> b0;
	a1 -> b3;
	b2 -> a3;
	a3 -> a0;
	a3 -> end;
	b3 -> end;

	start [shape=Mdiamond];
	end [shape=Msquare];
}
EOF
$ dot -Tpng graph.dot > graph.png
```

https://twitter.com/swardley/status/1087514858701185024

DOT Language

`dot -Tpng -ohello.png hello.dot`



`style=invis;`

graphs & digraphs

Rank
`rankdir=LR`

Record-based nodes


```
digraph g{
ranksep=0.2;

node[shape=box3d, width=2.3, height=0.6, fontname="Arial"];
n1[label="Incident Commander"];
n2[label="Public Information\nOfficer"];
n3[label="Liaison Officer"];
n4[label="Safety Officer"];
n5[label="Operations Section"];
n6[label="Planning Section"];
n7[label="Logistics Section"];
n8[label="Finance/Admin. Section"];

node[shape=none, width=0, height=0, label=""];
edge[dir=none];
n1 -> p1 -> p2 -> p3;
{rank=same; n2 -> p1 -> n3;}
{rank=same; n4 -> p2;}
{rank=same; p4 -> p5 -> p3 -> p6 -> p7;}
p4 -> n5;
p5 -> n6;
p6 -> n7;
p7 -> n8;
}
```


```
digraph {
  rankdir="LR"
  // the normal ranking algorithm doesn't know what to
  // do with clusters with rank="same".
  // If you opt in to the 'new' ranking algorithm, it
  // works as expected.
  newrank="true"

  // square brackets hold attributes
  A [ label="First Node" shape="circle" ]
  B [ label="Second Node" shape="square" ]

  // edges have attributes too
  A -> B [ arrowhead="halfopen" ]

  A -> B
  A -> C
  B -> C
  C -> D

  subgraph cluster_subs {
    label="Bs and Cs"
    rank="same"
    B
    C
  }




}

digraph {
  rankdir="LR"

  // Nothing points to A, so its rank is 1
  // A points to B, so B's rank is 2
  A -> B

  // B's rank is higher than A's, so C gets a rank
  // of 3 to be higher than B's rank
  A -> C
  B -> C

  // D gets a rank of 4
  C -> D
}
```

Vertices:
Vertex (Nodes): set of objects connected together
Edge: The connection between nodes
DAGs (Directed acyclic graphs)



## References

- [THE ARCHITECTURE OF COMPLEXITY](http://www2.econ.iastate.edu/tesfatsi/ArchitectureOfComplexity.HSimon1962.pdf), by HERBERT A. SIMON
- ["Scientific discovery and creative reasoning with diagrams"](https://pdfs.semanticscholar.org/4ed7/34560535df1b2789fa779cdf8618bcfe16ce.pdf)
- The challenge of the Computer Utility, Douglas Parkhill 1966

> Utility Computing is not a new concept. It involves organizing and providing a wide range of computing-related services as public utilities. Much like water, gas, electricity and telecommunications, the concept of computing as public utility was announced in 1955. Utility Computing remained a concept for near 50 years. Now some models and forms of Utility Computing are emerging such as storage and server virtualization, grid computing, and automated provisioning. Recent trends in Utility Computing as a complex technology involve business procedures that could profoundly transform the nature of companies’ IT services, organizational IT strategies and technology infrastructure, and business models. In the ultimate Utility Computing models, organizations will be able to acquire as much IT services as they need, whenever and wherever they need them. Based on networked businesses and new secure online applications, Utility Computing would facilitate “agility-integration” of IT resources and services within and between virtual companies. With the application of Utility Computing there could be concealment of the complexity of IT, reduction of operational expenses, and converting of IT costs to variable ‘on-demand’ services. How far should technology, business and society go to adopt Utility Computing forms, modes and models? — Ivan I. Ivanov

https://medium.com/@chrisvmcd/mapping-maturity-create-context-specific-maturity-models-with-wardley-maps-informed-by-cynefin-37ffcd1d315

https://medium.com/workday-engineering/detailing-the-evolution-of-the-workday-grid-through-wardley-mapping-affcf436a73c

http://web.mit.edu/outland/share/graphviz/doc/pdf/dotguide.pdf

https://martinfowler.com/bliki/AlignmentMap.html

http://larsbarkman.com/2015/08/26/alignmentmaps-with-graphviz/

https://leadingedgeforum.com/advisory/wardley-mapping/

https://medium.com/digital-anatomy/adding-context-to-the-wardley-map-of-data-flow-c818dc2960d6

https://read.acloud.guru/simon-wardley-is-a-big-fan-of-containers-despite-what-you-might-think-18c9f5352147

https://medium.com/@andy.callow/exploring-pioneers-settlers-and-town-planners-239be83ae37c

https://medium.com/@dinis.cruz/dot-language-graph-based-diagrams-c3baf4c0decc

https://hiredthought.com/2017/10/11/wardley-mapping-tools-and-techniques/

https://www.cio.co.uk/it-strategy/introduction-wardley-value-chain-mapping-3604565/

https://graphs.grevian.org/example

https://renenyffenegger.ch/notes/tools/Graphviz/examples/index

https://www.tonyballantyne.com/graphs.html#orgheadline14

https://www.graphviz.org/pdf/dotguide.pdf

https://www.graphviz.org/doc/info/attrs.html

https://explained.ai/decision-tree-viz/

https://medium.com/@dinis.cruz/dot-language-graph-based-diagrams-c3baf4c0decc

http://melp.nl/2013/08/flow-charts-in-code-enter-graphviz-and-the-dot-language/

https://www.tonyballantyne.com/graphs.html

https://www.worthe-it.co.za/programming/2017/09/19/quick-introduction-to-graphviz.html

https://graphs.grevian.org/example

https://www.graphviz.org/doc/info/attrs.html

https://blog.gardeviance.org/2017/05/is-my-diagram-map.html

## Appendix A

Herbet Simon

**Bounded rationality**: is the idea that rationality is limited when individuals make decisions: by the tractability of the decision problem, the cognitive limitations of the mind, and the time available to make the decision. Decision-makers, in this view, act as satisficers, seeking a satisfactory solution rather than an optimal one. Bounded rationality implies the idea that humans take reasoning shortcuts that may lead to suboptimal decision-making.

**Satisficing**: is a decision-making strategy or cognitive heuristic that entails searching through the available alternatives until an acceptability threshold is met. The term satisficing, a portmanteau of satisfy and suffice, was introduced by Herbert A. Simon in 1956

> "decision makers can satisfice either by finding optimum solutions for a simplified world, or by finding satisfactory solutions for a more realistic world. Neither approach, in general, dominates the other, and both have continued to co-exist in the world of management science" — Herbert A. Simon (1979) Nobel Prize in Economics speech

**Jevons Paradox**:

**Red Queen effect**: an evolutionary hypothesis (coevolution) that evolutionary changes in one species could result in the extinction of another. Coined by Van Valen to suggest that species would have to run in place (evolve) to stay in the same place (survive). Failing to do so would result in extinction.
> “Bees have to move very fast to stay still.” — David Foster Wallace


## Appendix B

**Graphs**
1. The vertices `u` and `v` are called the `end vertices` of the edge `(u,v)`
2. If two edges have the same `end vertices` they are `Parallel`
3. An edge of the form `(v,v)` is a `loop`
4. A Graph is `simple` if it has **no parallel edges and loops**
5. A Graph is said to be `Empty` if it has **no edges**. Meaning `E` is empty
6. A Graph is a `Null Graph` if it has **no vertices**. Meaning `V` and `E` is empty
7. A Graph with only **1 Vertex** is a `Trivial` graph
8. **Edges** are `Adjacent` if they have a common vertex. **Vertices** are `Adjacent` if they have a common edge
9. The **degree** of the vertex `v`, written as `d(v)`, is the number of **edges** with `v` as an end vertex. By convention, we count a loop twice and parallel edges contribute separately
10. **Isolated Vertices** are vertices with degree 1. `d(1)` vertices are isolated
11. A Graph is **Complete** if its edge set contains every possible edge between ALL of the vertices
12. A `Walk` in a Graph `G = (V,E)` is a finite, alternating sequence of the form  ViEiViEi  consisting of vertices and edges of the graph G
13. A Walk is `Open` if the initial and final vertices are different. A Walk is `Closed` if the initial and final vertices are the same
14. A Walk is a `Trail` if ANY edge is traversed atmost once
15. A Trail is a `Path` if ANY vertex is traversed atmost once (Except for a closed walk)
16. A Closed Path is a `Circuit` – Analogous to electrical circuits

