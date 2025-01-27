# Competitive Programming Solver

Inspired by this tutorial by LangChain: https://langchain-ai.github.io/langgraph/tutorials/usaco/usaco/
Based on this paper: https://arxiv.org/abs/2404.10952v1

This LM agent was built with LangChain to solve programming problems with retrieval from past USACO problems. The graph visualization of the agent is shown below:

![image](https://github.com/user-attachments/assets/ad64fd88-8b34-4a3a-b4a3-32904f242abe)

The agent first produces a draft solution with an LM. The BM25 retriever uses the problem description and the draft solution to find the 2 most similar examples among past USACO problems. The agent then feeds the problem description and the solutions to the two retrieved examples to an LM, which attempts the problem. The result of this attempt is evaluated by another LM, which will give feedback. This process (solution attempt and feedback) will continue until the problem is solved.

The USACO past problems made a perfect dataset for this project for several reasons. Firstly, each problem has a consistent format and has been catalogued with a specific difficulty level. Second, each problem has an official solution with both logical reasoning/explanation in natural language as well as an example Java/C++ implementation. Finally, for each problem, there are 10-20 high-quality test cases that usually contain some tricky edge cases.
