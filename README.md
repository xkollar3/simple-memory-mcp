# simple-memory-mcp
Repository contains an implementation of a simple memory system for AI agents to store artifacts

## Architecture

- Server written in Java utilizing langchain4j exposing MCP tools to interact with the memory
- Agents interact with MCP and add memories which can be retrieved later when switching contexts
- Server supports directories to organize closely related memories
- Memories are currently directly stored in elastic search because of querying functionality
- Later MCP will write memories to a git repository and commit them, a pre commit hook will sync the memories with elasticsearch indices
- Search is implemented via BM25 + RAG using Reciprocal rank fusion to produce best retrieval results

## Motivation and vision
- Main motivation is to instruct agent to save interesting information found after completing work, for other agents to retrieve in an effort to avoid repeating mistakes due to various gotcha/unexpected behaviours
- This project was created as a simple effort to accommodate context switching among multiple repositories for agents to be able to pull memories after a other agent has completed some work
- For now only used in experimental purposed as a private utility with no plan to formally bench mark and evaluate improvement to agent performance
