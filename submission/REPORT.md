
# CrewAI Build Report

**Name:** Veronica Broadway  
**Topic I used:** AI in Building Energy Efficiency

## 1. What I changed

I modified the `main.py` file in the CrewAI starter kit by adding a fourth agent called Fact Checker. The original workflow had three agents: a Research Analyst, Technical Writer, and Editor. I wanted to add a step that would review the research before it was used to write the final explanation.

I created the Fact Checker agent with instructions to identify unsupported claims, questionable statistics, and information that needed additional verification. I also created a task for this agent and added both the agent and task to the CrewAI workflow. The updated workflow runs the Research Analyst first, followed by the Fact Checker, Technical Writer, and Editor.

I chose this change because I often work with data and analytics, where accuracy is important. I also used AI in Building Energy Efficiency as my topic because it relates to my EcoBuild capstone project. I wanted to see whether adding a review step would make the final output more reliable.


## 2. How CrewAI Works

CrewAI is a framework that allows multiple AI agents to work together to complete a larger task. Each agent has a specific role, goal, and backstory that tells it what kind of work to perform. A task defines what the agent needs to accomplish and what the expected output should look like.

In my project, the Research Analyst starts by gathering information about AI in Building Energy Efficiency. The Fact Checker then reviews that research and identifies claims that may need supporting evidence. The Technical Writer uses the information to create an explanation, and the Editor reviews the writing and identifies claims that still need sources.

The crew is what connects these agents and tasks. I used the sequential process, meaning the tasks run in a specific order and information from earlier tasks is available to later ones. This allows the agents to build on each other's work rather than completing unrelated activities.

My change worked because I added the Fact Checker to both the agents list and the tasks list in `main.py`. This gave CrewAI an additional step to execute between research and writing. The terminal output confirmed that the new agent completed its review before the Technical Writer started.

This helped me understand that CrewAI does not automatically verify information. The quality of the results depends on how the agents and tasks are designed.


## 3. Evidence

I ran both versions of CrewAI using the topic "AI in Building Energy Efficiency" so I could compare the results.

In the original run (`run1_original.txt` and `explainer_run1.md`), the Research Analyst collected information, the Technical Writer created an explanation, and the Editor reviewed it. The final output discussed energy prediction, HVAC optimization, fault detection, and data privacy. The Editor flagged several claims that needed sources.

In the modified run (`run2_changed.txt` and `explainer_run2.md`), I added the Fact Checker between the Research Analyst and Technical Writer. The biggest difference was that the Fact Checker produced a detailed report evaluating individual claims. It questioned several statistics, including reported energy savings and prediction accuracy, and explained what evidence would be needed to support them.

The final explanation still contained claims marked as needing sources, but the additional agent provided a more detailed review of the research.

One challenge was that the Technical Writer initially returned empty responses. I also encountered a Groq API rate-limit error. I allowed CrewAI to retry, and eventually all four agents completed successfully.

This showed me that adding a Fact Checker can help identify potential problems, but it does not guarantee factual accuracy without access to reliable external sources.


## 4. Choosing a Framework

I would choose CrewAI for a project like mine because it makes sense to divide the work among different agents with specific responsibilities. I like that each agent has a defined role and task, similar to how people work together on a team. It was also fairly easy to add another agent without having to rewrite the entire program.

For my EcoBuild project, I could see CrewAI being useful for reviewing research, explaining machine learning results, and preparing information for people who may not have a technical background. For example, one agent could summarize model predictions, another could identify limitations, and another could explain the findings in plain language.

Another framework we covered was LangGraph. From the instructional video, I understand that LangGraph organizes workflows using nodes and edges, similar to a flowchart. This could be useful for projects that need more control over the order of operations or decisions about which step should happen next.

I think CrewAI would be easier for my current project because the agents can follow a straightforward sequence. LangGraph might be better for a more complicated process with different paths or conditions, but I would need to spend more time learning how to design those connections.

Both frameworks can support multi-step AI workflows, but CrewAI seems like a better starting point for what I wanted to accomplish.


## 5. Verification and AI Use

I verified the workflow by reviewing the terminal output and confirming that all four agents completed their tasks. I also compared the original and modified results to understand how the additional Fact Checker changed the output.

The Fact Checker identified several claims that required additional evidence. Since the starter kit does not have web access, I understand that the results are not independently verified. I reviewed the output for consistency and reasonableness, but I did not independently validate every statistic.

I used ChatGPT as a reference for some of the setup instructions, Python modifications, troubleshooting, and report organization. I performed the changes in VS Code, ran the workflows, reviewed the results, and checked that the modified program behaved as expected.

This assignment helped me understand how adding an agent changes a workflow and why human review is still important when working with AI-generated information.
