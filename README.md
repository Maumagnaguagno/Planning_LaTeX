# Planning LaTeX
**Latex listing for planning formalisms**

Add PDDL, JSHOP and HDDL snippets to your Tex files by making a copy of each listing configuration file to your LaTeX project.
An example is available on [Overleaf](https://www.overleaf.com/read/dntpdgmtpwxr).

```tex
\usepackage{listings}
\input{PDDL}
\input{JSHOP}
\input{HDDL}

\begin{lstlisting}[
  float=!htb,
  caption={PDDL move operator.},
  label={lst:pddl},
  language=PDDL]
(:action move
  :parameters (
    ?agent - agent
    ?from ?to - hallway ; Both ?from and ?to are hallways
  )
  :precondition (and
    (at ?agent ?from)
    (not (at ?agent ?to))
    (adjacent ?from ?to)
  )
  :effect (and
    (not (at ?agent ?from)) ; This line is usually forgotten
    (at ?agent ?to)
  )
)
\end{lstlisting}
```