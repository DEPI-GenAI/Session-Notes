![[Pasted image 20260314091945.png]]
- understand => decompose => tool selection(from these 4 categories) => exec+feedback.
1.  Decomposition:
	- Goal
	- Subtasks
	- Execution
	- make sure that i need to decomposeee in the first place?
	- Building Task Composition:
		![[Pasted image 20260314093933.png]]
		- LLM-Based Planner(Dynamic Planning): user goal => llm generate plan => system exec tasks
		- Static => functional calling
		- Dynamic + Static => Hybrid
			- check
			- validate
			- execute

2. Dependency Managment:
	- one task can't run before another
	- kind of dictionary or treee for handling dependencies.

3. Agentic AI Design Patterns

	1. Reflection Pattern: Self improvement/correction
		1. model generates => then evaluate itself(using other llm) to improve it
		2. generate => reflect => improve => output
		3. more on code generation, long reasoning tasks
			1. long reasoning tasks: summary what we did so far => reflection 
			2. it has many ways => search.
		4. ![[Pasted image 20260314095342.png]]

	2. Tool Use Pattern: legal assistant => single actions
	3. ReAct Pattern: Reason-Act
		![[Pasted image 20260314100641.png]]
		- Dynamic workflow
		- used in: sequential reasoning/actions => different outputs depending on user's input+model reasoning
			- بفكر لكل ستيب لوحدها وأعملها execution ولما أخلصها أفكر للي بعدها وهكذا
	4. Planning Pattern: pre-execution thinking
		1. user => planner => task list => execute => check => continue
		2. if task ain't 1 step + has complete workflow.
		3. بعمل تفكير كامل وليست للتاسكات بعدين execute ليهم كلهم
	5. Multi-Agent Pattern

4. guidelines
	1. measure task complexity: can it be solved in 1 step?
	2. check if the workflow is known in advance => planing
	3. evaluate the need for adaptation during execution => ReAct\
	4. 
	5. avoid over-engineering => each added layer increase latency, cost, difficulty
	6. use multi agent ONLY when tasks are separable

---

1️⃣ Problem Decomposition

- What is the system trying to achieve?
	- answer employee questions accurately
- What steps are required?
	- access company's documents
	- store them in RAG system
	- retrieve info sufficiently based on user questions 
	- re-evaluate
- Are the steps dependent on each other?
	- yes => as ordered.

2️⃣ Pattern Selection

- Choose ONE pattern only.
- planing
    

3️⃣ Engineering Justification (Most Important)  
Explain technically:

- Why this pattern fits the workflow
    
- Why other patterns are NOT suitable
    
- What level of complexity is actually needed
    

4️⃣ Architecture Thinking  
Describe:

- What the Agent does
    
- What tools/models/data it interacts with
    
- How execution flows
    

5️⃣ Overengineering Analysis  
Explain:

- Why using a more complex pattern would be unnecessary
    
- What risks it would introduce (latency, cost, complexity, etc.)

