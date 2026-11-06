# LLM Agent Platform Database

An SQL assignment and its solution (Oracle SQL). Users build AI agents on top of
large language models, give the agents tools, and run them on tasks. Every run
and every tool call is stored in the database.

![ER diagram](LLM_Agent_Platform_ER_Diagram.png)

## Files

| File | What it is |
|---|---|
| `LLM_Agent_Platform_Database.pdf` | The assignment: tables, relationships, constraints, sample data and required queries |
| `LLM_AGENT_PLATFORM_DATABASE.sql` | The solution: creates the tables with their constraints, inserts the sample data, runs 15 queries |
| `LLM_Agent_Platform_ER_Diagram.png` / `.webp` | The ER diagram |

## Tables

| Table | Rows | Holds |
|---|---|---|
| `USERS` | 5 | People who use the platform |
| `MODELS` | 4 | Language models with their prices per 1M tokens |
| `AGENTS` | 6 | Agents: owner, model, system prompt, temperature |
| `TOOLS` | 6 | Tools agents can use (search, code, database, API, file) |
| `AGENT_TOOLS` | 12 | Which agent may use which tool (many-to-many) |
| `RUNS` | 10 | Each task given to an agent, with status and token counts |
| `TOOL_CALLS` | 15 | Each tool call made during a run |

Model names, providers and prices are made up.

## How to run

Run `LLM_AGENT_PLATFORM_DATABASE.sql` from top to bottom in Oracle (SQL Developer,
Oracle Live SQL or SQL\*Plus). It was tested on Oracle Database 23ai Free: all
statements run without errors, and invalid rows (duplicate email, temperature 3,
unknown tool type, end time before start time and so on) are rejected by the
constraints.
