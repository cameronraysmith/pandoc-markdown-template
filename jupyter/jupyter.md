---
title: Analysis of differential equations in Julia
authors: Cameron Smith
jupyter:
  jupytext:
    cell_metadata_json: false
    formats: ipynb,jl:percent,md
    notebook_metadata_filter: all
    text_representation:
      extension: .md
      format_name: markdown
      format_version: '1.2'
      jupytext_version: 1.6.0
  kernelspec:
    display_name: Julia 1.5.1
    language: julia
    name: julia-1.5
  language_info:
    file_extension: .jl
    mimetype: application/julia
    name: julia
    version: 1.5.1
  rise:
    scroll: true
    theme: black
  toc-autonumbering: true
  toc-showcode: false
  toc-showmarkdowntxt: false
---

<!-- #region slideshow={"slide_type": "slide"} -->

# Simple examples of ODEs

<!-- #endregion -->

```julia
@time 1+1
```

# Simple examples of PDEs


```julia
1+2
```

This text is before the figure rendered with TikZ.

\[\begin{figure}
\centering

\begin{tikzpicture}[scale=1.8, auto,swap]
    \tikzstyle{vertex}=[circle,fill=black!50,minimum size=20pt,inner sep=0pt]
    \tikzstyle{edge} = [draw,thick,-]
    \tikzstyle{weight} = [font=\small]
    
    % draw the vertices
    \foreach \pos/\name in {
                            {(0,0)/1},
                            {(1,1)/2},
                            {(3,1)/6},
                            {(2,0)/4},
                            {(1,-1)/3},
                            {(2,-1)/5}}
        \node[vertex] (\name) at \pos {$\name$};
    
    \node[] (0) at (-1,0) {};
    \node[] (end) at (4,1) {};
    % connect vertices with edges and edge labels
    \foreach \source/ \dest /\weight in { 
            2/6/D,
            1/2/A,
            2/4/A, 
            4/6/C,
            1/3/B,
            3/4/C,
            3/5/B
        }
        \draw [->, line width=1.5pt] (\source) -- node[weight] {$\weight$} (\dest);
        
    \draw [->, line width=1.5pt] (0) -- node[weight] {$A$} (1);
    \draw [->, line width=1.5pt] (6) -- node[weight] {$D$} (end);

\end{tikzpicture}
\caption{Example spacetime diagram of interacting individual histories. The edges of the graph represent individuals labeled by abstract types and the nodes represent interactions. The graph depicts the following history, in terms of the mathematical formalism, \(I = \{A,B,C,D\}\): 1. $A$ gives rise to $A$ and $B$, which could be interpreted as an instance of cell division at interaction vertex $1$.  2.  Similaryly, $A$ gives rise to $A$ and $D$. 3. $B$ gives rise to $B$ and $C$. 4. $C$ eliminates $A$. 5. $B$ ceases to exist. 6. $D$ eliminates $C$.}
\label{fig:st-ind}
\end{figure}\]

This text is after the figure rendered with TikZ.
