AI (Artificial Intelligence ) - Broad umbrella for systems that mimic human-like intelligence. Ex: Recommendation engines, Spam Detection
ML (Machine learning) - A subset of AI where models learn patterns from data instead of being explicitly hard-coded. Ex: Predict CPU failure from logs/metrics
DL (Deep Learnnig) - A subset of ML using neural networks with many layers.Ex: Vision, Speech, NLP
NLP (Natural Langugage processing ) - AI for understanding/generating human language. Ex: Chatbots, Summarization, Translation
LLM (Large Langugage Model) - A deep learning model trained on massive text/code data to predict the next token and generate language/code.Ex: Open AI, Anthropic
Fondational Model - A large pretrained model that can be adapted for many tasks.LLMs are foundation models, but foundation models also include image/video/audio models.
Gen AI (Generative AI) - AI that creates content rather than just classifying or predicting. Ex: Text/Images/Audio/Video.
Prompt - The instruction/context you give the model.Ex: “Summarize this incident and propose RCA”
Prompt Engineering - Designing prompts so the model behaves better. Ex: Role prompting,Step-by-step,Output schema,Few-shot examples,Constraints
Token - A chunk of text/code the model processes. Not exactly a word. (Cost, Length , Context, latency)
Context Window - How much text/code the model can “see” in one interaction.
Embedding - A numeric vector representation of text/code/document meaning. Used in Semantic search,RAG,Similarity,Clustering,Deduplication Ex: Imagine representing words based on two features: Gender (-1 for Female, +1 for Male) and Royalty (0 to 1 scale). King:  [1.0,0.95] (Male, High Royalty)
               Queen: [-1.0,0.95] (Female, High Royalty)
Vector DB: Stores embeddings for semantic retrieval. Ex: Chroma , pgvector
RAG (Retrival Augemented Generation)-Before answering, the system retrieves relevant documents and injects them into the prompt.User asks → retrieve docs → send docs to LLM → answer grounded in docs Ex: Reduces hallucinations
Chunking - Breaking documents into smaller pieces for Embedding + Retrieval - 
Reranking - After retrieval, use another model to sort the best chunks more accurately. In a typical RAG pipeline, reranking is almost always done with a different model than the one used for initial retrieval.
Grounding - Forcing model outputs to be based on trusted data sources.
Hallucination - When the model invents facts, APIs, fields, commands, or behavior. A hallucination happens when an AI generates information that sounds confident and fluent but is factually incorrect or nonexistent
Agent - Understand goal/Plan steps/Use tools/Observe results/Iterate/Stop when done (or escalate) - LLM + memory + tools + loop + autonomy.
Agentic AI - AI that acts toward goals instead of only answering a prompt. Ex: “Take this Jira bug, inspect logs, find failing API, propose fix, create regression tests, open PR draft.”
Workflow - A fixed, deterministic sequence.Ex: Step 1: parse OpenAPI → Step 2: generate tests → Step 3: run → Step 4: report
Orchestrator - The component coordinating multiple agents/tools/tasks. Ex: API analysis agent,UI test generation agent,Performance agent,Security lint agent
Planner - Sub-component that breaks a goal into steps.
Executor - Sub-component that performs the steps (via tools, code, API calls, terminal, browser).
Tool Use/ Function Calling - Model can invoke external tools with structured arguments. Read file/Run tests/Query Jira/Open browser
ReAct Pattern - Reason + Act + Observe loop.Think → use tool → inspect result → continue → finish
Multi-Agent System - Multiple specialized agents collaborate.Ex: Test Strategy Agent/Test Data Agent/Performance Agent/Defect Triage Agent
Subagent - A delegated smaller agent used for a sub-task.Ex-“Review only the auth module and return security findings.”
Agent Memory - What the system remembers across a session or across tasks.Ex - Short-term memory (current session)/Long-term memory (persistent repo/org knowledge)/Episodic memory (what happened previously)/Semantic memory (facts about codebase/project)
Autonomy Level - How much freedom the agent has.Ex: Suggest only/Ask before tool use/Auto-run safe tools/Auto-edit code/Auto-open PR
Human-in-the-Loop (HITL)-Human approvals/checkpoints are inserted before risky actions.
Guardrails - Rules and controls to keep the model safe and reliable. Ex - JSON schema validation/PII filters/Safe tool allowlists/Approval gates/Output checks/Policy checks/OpenAI’s Guardrails framework is an example of this pattern.
Eval / Evaluation - Systematic measurement of agent quality. Ex: Correctness/Coverage/Hallucination rate/False positives/Tool success rate/Retry rate/Cost per task/Time saved
Observability for AI / Agent Observability - Tracing agent steps, prompts, tool calls, errors, costs, latencies, decisions.
AI Coding Assistant - Helps with autocomplete, chat, explanation, generation.Example: early-stage Copilot style
Coding Agent - More autonomous than an assistant:Reads repo/Plans changes/Edits files/Runs tests/Fixes errors/Opens PR. Ex - GitHub Copilot agent mode / coding agent /Claude Code/Codex-style agents/Cursor-like agents
Agent Mode - An operating mode where the coding tool autonomously works toward a goal. -GitHub says Copilot’s agent mode can determine files, suggest commands, and iterate until task completion.
Coding Agent PR Flow - Issue/task → agent implements → tests → PR created → human review . GitHub documents that Copilot coding agent can make changes and open a pull request, then request review.
Code Review Agent -AI reviews diffs/PRs for bugs, style, security, tests, performance, maintainability.GitHub supports Copilot code review in PRs and via CLI.
CLI Agent - Agent living in terminal.Ex: Claude Code / GitHub Copilot CLI
MCP (Model Context Protocol)- An open protocol for connecting LLM apps/agents to tools, data sources, APIs, files, services.
MCP Server - A server that exposes tools/resources/prompts to an AI client.  Ex: GitHub MCP server/Jira MCP server/Slack MCP server/Postgres MCP server/Browser MCP server
MCP Client -The app that consumes MCP servers.Ex: Claude Code/ GitHub Copilot agent mode (via MCP enhancements)
MCP Resources / Tools / Prompts - Resources = data exposed/Tools = executable actions/Prompts = reusable templates/commands
MCP Apps - Newer direction where UI-capable components become pluggable into agent experiences.
A2A (Agent2Agent Protocol)-Protocol for agent-to-agent communication (not just tool access).MCP = agent ↔ tool/A2A = agent ↔ agent
Agent Card -A machine-readable description of an agent’s identity, capabilities, endpoints, and contracts.
Agent Interoperability - Different agents built by different vendors/frameworks can collaborate.
Hooks - Deterministic extension points around agent lifecycle events.Ex: In Claude code - Before tool use/ After tool use/ On prompt submit/On stop /On subagent stop
Slash Commands -Command-like shortcuts exposed to the agent UI/CLI.Ex: /review , /fix-tests , /perf-check , /mcp__jira__get_issue
Skills - Packaged reusable capabilities for an agent.Ex - “Generate Playwright regression pack” / “Run API contract checks”/ “Do performance smoke analysis”
Plugin / Marketplace  - Installable capability packs for coding agents.
Custom Instructions / AGENTS.md - Repo-local instructions that steer coding agents consistently.
Eval Harness - Automated test suite for prompts/agents.
Agent Security / Policy Layer - Controls around:Which tools are allowed/Which files are writable/Which environments are reachable/Which secrets are masked/Which actions need approval
Temparature - Controls how random/creative/predictable model's next -word selection. At low temp - more consistent. At High temp - more diverse.
Chain of Though - COT - Model breaks problem into intermediate reasoning steps. 
Quake for LLM usually refers to QuAKE (often stylized as QuAKE: Question Answering over Knowledge-Enhanced Evaluations or similar benchmark naming depending on the paper/repo context).
Langgraph - LangGraph is a framework for building stateful, multi-step AI agents as a graph/workflow.
Langchain - framework to connect LLMs with prompts, data, tools, and workflows
N8n- visual automation platform for connecting tools, APIs, and AI workflows
Hugging Face - most popular open ecosystem for AI models, datasets, and ML tools.open-source model hub/datasets/Transformers library/inference APIs/Spaces (AI demos/apps)/model evaluation resources
Sentence Transformer - Model that converts a sentence (or paragraph) into a dense vector/embedding so that similar meanings are close together in vector space.
Recall & Precision & Retrieval - Finding the most relevant documents/chunks from a knowledge base for a user query,Precision = Relevant Retrieved / Total Retrieved, Recall = Relevant Retrieved / Total Relevant Available



