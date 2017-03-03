# Planning LaTeZ
**Latex listing for planning formalisms**

Add PDDL and JSHOP snippets to your Tex files by making a copy of each listing configuration file to your LaTeX project.

```tex
\usepackage{listings}
\input{PDDL}
\input{JSHOP}

\begin{lstlisting}[
  float=!tb,
  caption={Move operator.},
  label={lst:pddlmove},
  language=PDDL]
(:action move
  :parameters (
    ?bot - robot
    ?source ?destination - hallway
  )
  :precondition (and
    (at ?bot ?source)
    (not (at ?bot ?destination))
    (connected ?source ?destination)
  )
  :effect (and
    (not (at ?bot ?source))
    (at ?bot ?destination)
  )
)
\end{lstlisting}
```