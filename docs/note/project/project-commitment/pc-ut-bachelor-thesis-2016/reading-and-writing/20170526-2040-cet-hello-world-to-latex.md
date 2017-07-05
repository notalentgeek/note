* Some LaTex related knowledges.
* [http://tex.stackexchange.com/questions/101593/empty-space-after-adding-an-image](http://tex.stackexchange.com/questions/101593/empty-space-after-adding-an-image), prevent space after adding image.
* The problem.

```markdown
\begin{figure}[ht]
  \begin{center}
    \includegraphics[width=9cm,height=5.5cm]{example-image-a}
  \end{center}
  \begin{center}
    \caption[ddd]{ddd}
  \end{center}
\end{figure}
```

* Here is the solution.

```markdown
\begin{figure}[ht]
  \centering
  \includegraphics[width=9cm,height=5.5cm]{example-image-a}
  \caption[ddd ]{ ddd }
\end{figure}
```

* There was a problem which my LaTex document could not handle `\chapter{}`.
* It was because `\chapter{}` is only for `\documentclass{book}` or `\documentclass{book}`.
* Check this link, [http://tex.stackexchange.com/questions/117151/undefined-control-sequence-and-chapter-error](http://tex.stackexchange.com/questions/117151/undefined-control-sequence-and-chapter-error)
* Basic LaTex setup, [https://www.latex-tutorial.com/tutorials/beginners/how-to-use-latex/](https://www.latex-tutorial.com/tutorials/beginners/how-to-use-latex/).
* Screenshot.

![./20170526-2040-cet-hello-world-to-latex-1.png](./20170526-2040-cet-hello-world-to-latex-1.png)

* Just add additional line break to add paragraph.
* Example on how to add image, [https://www.sharelatex.com/learn/Inserting_Images](https://www.sharelatex.com/learn/Inserting_Images).

![./20170526-2040-cet-hello-world-to-latex-2.png](./20170526-2040-cet-hello-world-to-latex-2.png)

* Example on sectioning your LaTex document, [https://www.sharelatex.com/learn/Sections_and_chapters](https://www.sharelatex.com/learn/Sections_and_chapters).

![./20170526-2040-cet-hello-world-to-latex-3.png](./20170526-2040-cet-hello-world-to-latex-3.png)