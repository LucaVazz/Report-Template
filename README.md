# DHBW - LaTeX - Template
Please use XeLaTeX or LuaLaTex for building.



## Features
- all formal layout-properties of the document are in accordance to the requirements given by the Technical Faculty of DHBW Mannheim.
- Titlepages for Internship Reports, Study Reports and Bachelor Thesis in accordance to these requirements included

<img alt="various Titlepages" src="http://i.imgur.com/ddOe000.png" width="70%">

- Fully customizable coloring

<img alt="Coloring" src="http://i.imgur.com/TGjZShi.png" width="70%">

- Easy switching between the (default) *english* and *german* version of the document



## How to Setup and Use
1. inside `./usersetup.tex`:
    - choose the type of your Report
    - choose if you want to write your report in english or german
    - fill out the fields for your informations
    - choose your desired color theme or define your own
2. places the entries for your bibliography into `./resources/references.bib`
3. place the `.tex`-files containing your content into `./content` and define the structure of your content inside `./content/structure.tex`
4. fill your acronyms and custom macros as needed into `./content/acronyms.tex` and `./content/macros.tex`
5. save your image files into `./resources`
    - you can then use them easily by just referencing `\includegraphics{asdf}` if you saved your file at `./resources/asdf.png`



## Included Custom Elements for Ease of Use
**Note:** `<asdf>` inside the general code denotes a placeholder


#### striped Tables
```Latex
\begin{stripedacenttable}
    {<caption>}
    {\label{tab:<label>}}
    {<formating>}
    {<Headings-Content>}
    <row definitions>
\end{stripedacenttable}

\begin{stripedtable}
    {<caption>}
    {\label{tab:<label>}}
    {<coloring>}
    {<formating>}
    {<Headings-Content>}
    <row definitions>
\end{stripedtable}
```

- *<label>* needs to be enclosed inside `\label` to keep the auto-completion functionality of your editor working correctly
- formating should have the form `x^x^x^...` where `x` specifies the alignment for the column
    + possible aligments: `l`: left-aligned , `c`: centered , `r`: right-aligned

> *Example (with captions):*
> ```Latex
\begin{stripedacenttable}
    {A plain but nice looking table}
    {\label{tab:ex1}}
    {c^l^l}
    {Quarter & asdf & foobar}
    prev. Year & 42 & 17 \\
    Q1 & -3 & -7 \\
    Q2 & +7 & -1 \\
    Q3 & -4 & +12 \\
    Q4 & +2 & +2 \\
\end{stripedacenttable}

>Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Ut purus elit, vestibulum ut, placerat ac, adipiscing vitae, felis.

>\begin{stripedtable}
    {A colorful, nice looking table}
    {\label{tab:ex1}}
    {Green}
    {c^l^l}
    {Quarter & asdf & foobar}
    prev. Year & 42 & 17 \\
    Q1 & -3 & -7 \\
    Q2 & +7 & -1 \\
    Q3 & -4 & +12 \\
    Q4 & +2 & +2 \\
\end{stripedtable}
```

> <img alt="Tables" src="http://i.imgur.com/8FzhRYr.png" width="65%">


#### Code Listings
```Latex
\begin{lstlisting}[
    caption={<description of your program>},
    label={lst:<label>},
    captionpos=b,
    language=<language-name>
]
<your code>
\end{lstlisting}
```

> *Example:*
> ```Latex
\begin{lstlisting}[
    caption={The Classic, realized in Python},
    label={lst:python1},
    captionpos=b,
    language=Python
]
> # classic
>
> hi = "Hello Wolrd"
print(hi)
\end{lstlisting}
```

> <img alt="Code Lisitng" src="http://i.imgur.com/8zXqzOZ.png" width="70%">


#### Boxed Text
```Latex
Nam dui ligula, fringilla a, euismod sodales, sollicitudin vel, wisi. Morbi auctor lorem non justo. Nam lacus libero, pretium at, lobortis vitae, ultricies et, tellus.

\begin{notebox}{<border-color>}{<icon>}
<your text>
\end{notebox}

\begin{infobox}
<your text>
\end{infobox}

\begin{warnbox}
<your text>
\end{warnbox}
```

> *Example:*
> ```Latex
Nam dui ligula, fringilla a, euismod sodales, sollicitudin vel, wisi. Morbi auctor lorem non justo. Nam lacus libero, pretium at, lobortis vitae, ultricies et, tellus.

>\begin{notebox}{Green}{\faStar{}}
>Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Ut purus elit, vesti- bulum ut, placerat ac, adipiscing vitae, felis. Curabitur dictum gravida mauris. Nam arcu libero, nonummy eget, consectetuer id, vulputate a, magna. Donec vehicula augue eu neque.
>\end{notebox}

>Nam dui ligula, fringilla a, euismod sodales, sollicitudin vel, wisi. Morbi auctor lorem non justo. Nam lacus libero, pretium at, lobortis vitae, ultricies et, tellus.

>\begin{infobox}
>Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Mauris ut leo. Cras viverra metus rhoncus sem. Nulla et lectus vestibulum urna fringilla ultrices. Phasellus eu tellus sit amet tortor gravida placerat.
>\end{infobox}

>Nam dui ligula, fringilla a, euismod sodales, sollicitudin vel, wisi. Morbi auctor lorem non justo. Nam lacus libero, pretium at, lobortis vitae, ultricies et, tellus.

>\begin{warnbox}
>Integer sapien est, iaculis in, pretium quis, viverra ac, nunc. Praesent eget sem vel leo ultrices bibendum. Aenean faucibus. Morbi dolor nulla, malesuada eu, pulvinar at, mollis ac, nulla. Curabitur auctor semper nulla. Donec varius orci eget risus.
>\end{warnbox}

>Nam dui ligula, fringilla a, euismod sodales, sollicitudin vel, wisi. Morbi auctor lorem non justo. Nam lacus libero, pretium at, lobortis vitae, ultricies et, tellus.
```

> <img alt="Code Lisitng" src="http://i.imgur.com/7inW1M0.png" width="70%">


#### Fancy Symbols
The FontAwesome Package is bundeled into this repository, so you can use [all the nice symbols.](http://mirrors.ctan.org/fonts/fontawesome/doc/fontawesome.pdf).

> *Example:*
> ````Latex
> \faFileTextO{} \faStar{}\faStar{}\faStar{}\faStar{}\faStar{} $=$ \faGraduationCap{}
> ````

> <img alt="Code Lisitng" src="http://i.imgur.com/wZAVaom.png" width="14%">

The MarVoSym-Package is also loaded to provide [additional symbols](http://texdoc.net/texmf-dist/doc/fonts/marvosym/marvodoc.pdf).

> *Example:*
> ````Latex
> \Estatically{} \Forward{} \Printer{} \ \ \MVRightArrow{} \ \ \EyesDollar\EyesDollar\EyesDollar
> ````

> <img alt="Code Lisitng" src="http://i.imgur.com/lZ64aQA.png" width="14%">


#### Citations in the Footnotes
````Latex
\footnotecite{<source-reference>}
```


#### Mark Incomplete Things You Need To Do
````Latex
\incompletemarker{<note>}
```

> <img alt="Code Lisitng" src="http://i.imgur.com/eSQSoao.png" width="40%">


#### Prevent Pagebreaks absolutely, definitively
```Latex
\begin{absolutelynopagebreak}
    <content>
\end{absolutelynopagebreak}
```



---



## Contributing
I'm open for all forks, feedback and Pull Requests ;)


## License
This project is licensed under the terms of the *GNU General Public License v3.0*. For further information, please look [here](http://choosealicense.com/licenses/gpl-3.0/) or [here<sup>(DE)</sup>](http://www.gnu.org/licenses/gpl-3.0.de.html).
