| Term | Meaning | Example/Usage |
|------|---------|---------|
| AI (Artificial Intelligence) | Broad umbrella for systems that mimic human-like intelligence. | Recommendation engines, spam detection |
| ML (Machine Learning) | A subset of AI where models learn patterns from data instead of being explicitly hard-coded. | Predict CPU failure from logs/metrics |
| DL (Deep Learning) | A subset of ML using neural networks with many layers. | Vision, speech, NLP |
| NLP (Natural Language Processing) | AI for understanding and generating human language. | Chatbots, summarization, translation |
| LLM (Large Language Model) | A deep learning model trained on massive text/code data to predict the next token and generate language/code. | OpenAI, Anthropic models |
| Foundation Model | A large pretrained model that can be adapted for many tasks. LLMs are foundation models, but foundation models also include image/video/audio models. | GPT-like text model, multimodal model |
| Gen AI (Generative AI) | AI that creates content rather than just classifying or predicting. | Text, images, audio, video generation |
| Prompt | The instruction or context you give the model. | “Summarize this incident and propose RCA” |
| Prompt Engineering | Designing prompts so the model behaves better. | Role prompting, step-by-step, output schema, few-shot examples, constraints |
| Token | A chunk of text/code the model processes; not exactly a word. Impacts cost, length, context, and latency. | “OpenAI” may split into multiple tokens |
| Context Window | How much text/code the model can “see” in one interaction. | 8K, 128K, or 1M token context |
| Embedding | A numeric vector representation of text/code/document meaning used in semantic search, RAG, similarity, clustering, deduplication. | King → [1.0, 0.95], Queen → [-1.0, 0.95] |
| Vector DB | Stores embeddings for semantic retrieval. | Chroma, pgvector |
| RAG (Retrieval-Augmented Generation) | Before answering, the system retrieves relevant documents and injects them into the prompt so the answer is grounded in docs. | User asks → retrieve docs → send docs to LLM → grounded answer |
| Chunking | Breaking documents into smaller pieces for embedding and retrieval. | Split a PDF into 500-token chunks |
| Reranking | After retrieval, another model sorts the best chunks more accurately. Usually different from the initial retrieval model. | Top 20 retrieved chunks reranked into top 5 |
| Grounding | Forcing model outputs to be based on trusted data sources. | Answer only from company knowledge base |
| Hallucination | When the model invents facts, APIs, fields, commands, or behavior. | Returning a nonexistent API endpoint confidently |
| Agent | A system that understands a goal, plans steps, uses tools, observes results, iterates, and stops/escalates. Usually = LLM + memory + tools + loop + autonomy. | Read logs → run command → analyze → fix suggestion |
| Agentic AI | AI that acts toward goals instead of only answering prompts. | “Take this Jira bug, inspect logs, find failing API, propose fix, create regression tests, open PR draft.” |
| Workflow | A fixed, deterministic sequence of steps. | Parse OpenAPI → generate tests → run → report |
| Orchestrator | The component coordinating multiple agents, tools, or tasks. | API analysis agent + UI test generation agent + performance agent |
| Planner | Sub-component that breaks a goal into steps. | “First inspect logs, then test API, then compare traces” |
| Executor | Sub-component that performs the steps using tools, code, APIs, terminal, browser, etc. | Run pytest, call REST API, open browser |
| Tool Use / Function Calling | Model can invoke external tools with structured arguments. | Read file, run tests, query Jira, open browser |
| ReAct Pattern | Reason + Act + Observe loop. | Think → use tool → inspect result → continue → finish |
| Multi-Agent System | Multiple specialized agents collaborate on one goal. | Test Strategy Agent + Test Data Agent + Performance Agent + Defect Triage Agent |
| Subagent | A delegated smaller agent used for a focused sub-task. | “Review only the auth module and return security findings.” |
| Agent Memory | What the system remembers across a session or across tasks. Includes short-term, long-term, episodic, and semantic memory. | Remember prior failures, repo facts, or previous fixes |
| Autonomy Level | How much freedom the agent has. | Suggest only / Ask before tool use / Auto-run safe tools / Auto-edit code / Auto-open PR |
| Human-in-the-Loop (HITL) | Human approvals or checkpoints inserted before risky actions. | Ask approval before deleting files or opening a PR |
| Guardrails | Rules and controls to keep the model safe and reliable. | JSON schema validation, PII filters, safe tool allowlists, approval gates, output checks |
| Eval / Evaluation | Systematic measurement of agent quality. | Correctness, coverage, hallucination rate, tool success rate, retry rate, cost per task, time saved |
| Observability for AI / Agent Observability | Tracing agent steps, prompts, tool calls, errors, costs, latencies, and decisions. | View prompt traces and failed tool calls in a dashboard |
| AI Coding Assistant | Helps with autocomplete, chat, explanation, and code generation. | Early-stage Copilot-style assistant |
| Coding Agent | More autonomous than an assistant; reads repo, plans changes, edits files, runs tests, fixes errors, opens PRs. | GitHub Copilot agent mode, Claude Code, Cursor-like agents |
| Agent Mode | An operating mode where the coding tool autonomously works toward a goal. | Determine files, suggest commands, iterate until task completion |
| Coding Agent PR Flow | Typical flow where the agent implements a task, tests it, creates a PR, and a human reviews. | Issue → agent implements → tests → PR → human review |
| Code Review Agent | AI reviews diffs/PRs for bugs, style, security, tests, performance, and maintainability. | Copilot PR review or AI PR review bot |
| CLI Agent | An agent that lives in the terminal. | Claude Code, GitHub Copilot CLI |
| MCP (Model Context Protocol) | An open protocol for connecting LLM apps/agents to tools, data sources, APIs, files, and services. | Connect an LLM to GitHub, Jira, Postgres via MCP |
| MCP Server | A server that exposes tools, resources, or prompts to an AI client. | GitHub MCP server, Jira MCP server, Slack MCP server, Postgres MCP server |
| MCP Client | The app that consumes MCP servers. | Claude Code, enhanced coding agent clients |
| MCP Resources / Tools / Prompts | Resources = exposed data, Tools = executable actions, Prompts = reusable templates/commands. | Read issue (resource), create ticket (tool), /review (prompt) |
| MCP Apps | A newer direction where UI-capable components become pluggable into agent experiences. | Embedded UI widgets inside agent workflows |
| A2A (Agent-to-Agent Protocol) | Protocol for agent-to-agent communication (not just tool access). MCP = agent ↔ tool, A2A = agent ↔ agent. | Security agent coordinating with testing agent |
| Agent Card | A machine-readable description of an agent’s identity, capabilities, endpoints, and contracts. | JSON/YAML metadata describing an agent |
| Agent Interoperability | Different agents built by different vendors/frameworks can collaborate. | A LangGraph agent talking to another vendor’s agent |
| Hooks | Deterministic extension points around agent lifecycle events. | Before tool use, after tool use, on prompt submit, on stop |
| Slash Commands | Command-like shortcuts exposed in agent UI/CLI. | /review, /fix-tests, /perf-check, /mcp__jira__get_issue |
| Skills | Packaged reusable capabilities for an agent. | “Generate Playwright regression pack”, “Run API contract checks” |
| Plugin / Marketplace | Installable capability packs for coding agents. | Add a Jira integration or browser automation plugin |
| Custom Instructions / AGENTS.md | Repo-local instructions that consistently steer coding agents. | “Always run tests before PR” in AGENTS.md |
| Eval Harness | Automated test suite for prompts or agents. | Run benchmark tasks after every prompt change |
| Agent Security / Policy Layer | Controls around allowed tools, writable files, reachable environments, secret masking, and actions needing approval. | Block production DB writes, mask API keys |
| Temperature | Controls how random/creative/predictable the model’s next-token selection is. Lower = more consistent, higher = more diverse. | 0.1 for deterministic tests, 0.8 for brainstorming |
| Chain of Thought (CoT) | The model breaks a problem into intermediate reasoning steps. | Solve a debugging problem step by step |
| QuAKE for LLM | Usually refers to QuAKE (benchmark/research context), often used around question answering or knowledge-enhanced evaluation depending on the paper/repo. | LLM benchmark/research dataset context |
| LangGraph | Framework for building stateful, multi-step AI agents as a graph/workflow. | Multi-agent orchestration with state transitions |
| LangChain | Framework to connect LLMs with prompts, data, tools, and workflows. | Build RAG pipelines and tool-calling apps |
| n8n | Visual automation platform for connecting tools, APIs, and AI workflows. | Trigger workflow when a Jira issue is created |
| Hugging Face | Popular open ecosystem for AI models, datasets, and ML tools. Includes model hub, datasets, Transformers, inference APIs, Spaces, evaluation resources. | Download an open-source model or host a demo in Spaces |
| Sentence Transformer | Model that converts a sentence/paragraph into a dense vector (embedding) so similar meanings are close in vector space. | Convert incident summaries into vectors for semantic search |
| Retrieval | Finding the most relevant documents/chunks from a knowledge base for a user query. | Fetch top 5 relevant runbooks for an incident |
| Precision | Of retrieved items, how many are actually relevant. Formula: Relevant Retrieved / Total Retrieved. | 8 relevant out of 10 retrieved = 80% precision |
| Recall | Of all relevant items available, how many were retrieved. Formula: Relevant Retrieved / Total Relevant Available. | 8 retrieved out of 20 relevant = 40% recall |
