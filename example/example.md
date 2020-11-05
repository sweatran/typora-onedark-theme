---

---

# Example for OneDark Theme

[toc]

## Headers

### h3

Markdown is a lightweight markup language with plain-text-formatting syntax. Its design allows it to be converted to many output formats, but the original tool by the same name only supports HTML. Markdown is often used to format readme files, for writing messages in online discussion forums, and to create rich text using a plain text editor.

#### h4

Since the initial description of Markdown contained ambiguities and unanswered questions, the implementations that appeared over the years have subtle differences and many come with syntax extensions.

##### h5

In MediaWiki, it is implemented in the currently unmaintained MarkdownExtraParser parser function extension

###### h6

Implementations of Markdown are available for over a dozen programming languages.

## Quote

> Most UI components including tooltip, dialog and buttons are painted by HTML. And you only need to change those part when you find the UI components are incompatible with your editor theme after finishing steps above. HTML files from the toolkit includes most common UI components for you to easily debug.

## Font Style

**Bold**, *italic*, ~~delete~~

<u>underline</u>, [Link](typora.io)

H~2~O, E=mc^2^

<span style="color:red">colored text</span>, ==highlight==

emoji: :smile:

- [ ] checkbox

## Codeblock

```python
# hello_world.py
class HelloWorld():
	def __init__(self):
        self.text='hello world!'
    
    def show(self,word):
        print(f'{word}, {self.text}')
        
test=HelloWorld()
test.show()
```

Run terminal then enter: `python hello_world.py`

## KBD

* bold：<kbd>Ctrl/Command</kbd> + <kbd>B</kbd> 

* italic：<kbd>Ctrl/Command</kbd> + <kbd>I</kbd> 

## MathJax

Given two populations, $x_1$ and $x_2$ , with logistic dynamics, the Lotka–Volterra formulation adds an additional term to account for the species' interactions. Thus the competitive Lotka–Volterra equations are:
$$
\begin{cases}
\cfrac{dx_1}{dt}=r_1x_1\bigg(1-\cfrac{x_1+\alpha_{12} x_2}{K_1}\bigg)\\ 
\cfrac{dx_2}{dt}=r_2x_2\bigg(1-\cfrac{x_2+\alpha_{21} x_1}{K_2}\bigg)
\end{cases}
$$
Here, $\alpha_{12}$ represents the effect species 2 has on the population of species 1 and  $\alpha_{21}$represents the effect species 1 has on the population of species 2. 

## Order

1. first item
2. second item
   1. first item
   2. second item
3. third item

---

* first item
* second item
  * first item
    * first item
* fourth item

## Table

| Cinderella   |   11 | glass       | transparent |
| :----------- | ---: | :---------- | :---------- |
| Name         | Size | Material    | Color       |
| All Business |    9 | leather     | brown       |
| Roundabout   |   10 | hemp canvas | natural     |

## Footnote

You can create footnotes like this[^fn1] and this[^fn2]. 

[^fn1]: Here is the **text** of the first ***\*footnote\****. 
[^fn2]: Here is the **text** of the second ***\*footnote\****.

## Image, Video

<img src="D:\Project\typora-onedark-theme\example\image.jpg" alt="Cosmos08" style="zoom:15%;" />

<video src="./video.mp4" />

<table>
  <tr>
   <td>Bash command
   </td>
   <td>Description
   </td>
  </tr>
  <tr>
   <td>ls
   </td>
   <td>List directory contents
   </td>
  </tr>
  <tr>
   <td>cd
   </td>
   <td>Change directory
   </td>
  </tr>
  <tr>
   <td>cp
   </td>
   <td>Copy files
   </td>
  </tr>
  <tr>
   <td>mv
   </td>
   <td>Move files
   </td>
  </tr>
</table>

## Graph

### sequence

```sequence
Alice->Bob: Hello Bob, how are you?
Note right of Bob: Bob thinks
Bob-->Alice: I am good thanks!
```

### flow

```flow
st=>start: Start
op=>operation: Your Operation
cond=>condition: Yes or No?
e=>end

st->op->cond
cond(yes)->e
cond(no)->op
```

### mermaid

#### Flowchart

```mermaid
graph TD
    Start --> Stop
```
```mermaid
graph LR
	A([A]) --- B(B) -- C --- C{C}
    C -- D --> D[[D]]
    C -.->|E| E[E]
    C -. F .-> F[(F)]
    C ==>|G| G((G))
    B == edge ==> H>H]
    B --> I{{I}}
    subgraph sub [subgraph]
    I -->|J| J[/J/]
    I -->|K| K[\K\]
    I -->|L| L[\L/]
    I -->|M| M[/M\]
    end
```


#### Sequence diagram

```mermaid
%% Example of sequence diagram
sequenceDiagram
	participant A
	participant B
	participant C
	Note right of B: note
	Note over A,B: note
	A->B: a
	activate B
	A-->B: b
	activate B
	A->>B: c
	deactivate B
	A-->>B: d
	deactivate B
	rect rgba(128,0,0,0.5)
	A-xA: e
	end
	loop loop
        A--xB: f
    end
    alt alt
        B->>A: g
    else else
        B->>A: h
    end
    par par
    	A->C: i
    and and
    	A->B: j
    	par nest
    		B->C: k
    	end
    end
    
```

#### Class diagram

```mermaid
classDiagram
    A <|-- B: label
    A "1" *-- "1.." C
    A "*" o-- "0..1" D
    C <-- E
    C -- F
    D <.. G
    D <|.. H
    D .. I
    A: +int i1
    A: -String s1
    A: #List~int~ l1
    A: ~f1(arg) bool
    A: +f2()*
    A: +f3()$
    class B {
   		<<enumeration>>
        RED
        GREEN
        BLUE
    }
    class D {
    	<<interface>>
    	int i1
    	f1()
    }
```

#### State diagram

```mermaid
stateDiagram
    [*] --> Still
    Still --> [*]

    Still --> Moving
    Moving --> Still
    Moving --> Crash
    Crash --> [*]
```

```mermaid
stateDiagram
	state fork_state <<fork>>
    state "This is A" as A
    [*] --> fork_state
    [*] --> D
    D --> fork_state
    note right of D
    	note for D
    end note
    note left of A: note for A
    fork_state --> A
    fork_state --> B
    A --> C: trans
    B --> C
    C --> [*]
    state C {
    	[*] --> C1: test
    	C1 --> C2
    	C2 --> C3
    	C3 --> [*]
    	state C2 {
    		[*] --> C21
    		C21 --> [*]
    		state C21 {
    			[*] --> C211
    		}
    	}
    	C1: This is C1
    	--
    	[*] --> T
    }
```

```mermaid
stateDiagram-v2
	state fork_state <<fork>>
    state "This is A" as A
    [*] --> fork_state
    [*] --> D
    D --> fork_state
    note right of D
    	note for D
    end note
    note left of A: note for A
    fork_state --> A
    fork_state --> B
    A --> C: trans
    B --> C
    C --> [*]
    state C {
    	[*] --> C1: test
    	C1 --> C2
    	C2 --> C3
    	C3 --> [*]
    	state C2 {
    		[*] --> C21
    		C21 --> [*]
    		state C21 {
    			[*] --> C211
    		}
    	}
    	C1: This is C1
    	--
    	[*] --> T
    }
```

#### Entity Relationship Diagram

```mermaid
erDiagram
    A |o--o| B : b
    B ||--|| C : c
    A }o..o{ D : d
    D }|..|{ E : e
```

#### User Journey Diagram

```mermaid
journey
    title My working day
    section A
        A1: 5: Me
        A2: 3: Me
        A3: 1: Me, Cat
```

#### Gantt

```mermaid
%% Example with slection of syntaxes
gantt
dateFormat  YYYY-MM-DD
title Adding GANTT diagram functionality to mermaid

section A section
Completed task            :done,    des1, 2014-01-06,2014-01-08
Active task               :active,  des2, 2014-01-09, 3d
Future task               :         des3, after des2, 5d
Future task2               :         des4, after des3, 5d

section Critical tasks
Completed task in the critical line :crit, done, 2014-01-06,24h
Implement parser and jison          :crit, done, after des1, 2d
Create tests for parser             :crit, active, 3d
Future task in critical line        :crit, 5d
Create tests for renderer           :2d
Add to mermaid                      :1d

section Documentation
Describe gantt syntax               :active, a1, after des1, 3d
Add gantt diagram to demo page      :after a1  , 20h
Add another diagram to demo page    :doc1, after a1  , 48h

section Last section
Describe gantt syntax               :after doc1, 3d
Add gantt diagram to demo page      : 20h
Add another diagram to demo page    : 48h
```

#### Pie Chart

```mermaid

pie
    title Pie Chart
    "A" : 1
    "B" : 2
    "C" : 3
    "D" : 4
    "E" : 5
    "F" : 6
    "G" : 7
    "H" : 8
```