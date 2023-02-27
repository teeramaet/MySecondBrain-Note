
## Relationship between logical and physical model
	Many systems analysts create a physical model of the current system and then develop a logical model of the current system before tackling a logical model of the new system. Performing that extra step allows them to understand the current system better. Many analysts follow a four-model approach, which means that they develop a physical model of the current system, a logical model of the current system, a logical model of the new system, and a physical model of the new system. The major benefit of the four-model approach is that it provides a clear picture of current system functions before any modifications or improvements are made. That is important because mistakes made early in systems development will affect later SDLC phases and can result in unhappy users and additional costs.

## Explain data flow diagrams
	DFD shows how data moves through an information system but does not show program logic or processing steps. A set of DFDs provides a logical model that shows what the system does, not how it does it. That distinction is important because focusing on implementation issues at this point would restrict the search for the most effective system design.

## How to draw 4 basic data flow diagram
![[Pasted image 20230227230927.png]]

## 6 guidelines used when drawing dataflow diagrams
![[Pasted image 20230227231119.png]]
## How to draw context diagrams
	Start by placing a single process symbol in the center of the page. The symbol represents the entire information system, and it is identified as process 0 (the numeral zero, and not the letter O). Then place the system entities around the perimeter of the page and use data flows to connect the entities to the central process. Data stores are not shown in the context diagram because they are contained within the system and remain hidden until more detailed diagrams are created. To determine which entities and data flows to place in the context diagram, begin by reviewing the system requirements to identify all external data sources and destinations. During that process, identify the entities, the name and content of the data flows, and the direction of the data flows. If that is done carefully, and the job of fact-finding was done well in the previous stage, drawing the context diagram should be relatively easy. Now review the following context diagram examples.

	Spontaneous generation. The APPLY INSURANCE PREMIUM process, for instance, produces output but has no input data flow. Because it has no input, the process is called a spontaneous generation process. • Black hole. CALCULATE GROSS PAY is called a black hole process, which is a process that has input but produces no output. • Gray hole. A gray hole is a process that has at least one input and one output, but the input obviously is insufficient to generate the output shown. For example, a date of birth input is not sufficient to produce a final grade output in the CALCULATE GRADE process

	A DFD shows only external entities that provide data to the system or receive output from the system.
## How to draw diagram 0 data flow diagrams

## How to draw lower-level data flow diagrams

## How to level and balance data flow diagrams

## How to create a data dictionary

## How to apply process description tools in modular design

