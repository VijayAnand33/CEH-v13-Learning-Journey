 # ShellGPT

 ## Overview

 ShellGPT (SGPT) is an AI-powered command-line assistant that integrates Large Language Models (LLMs) into the terminal. It assists users by generating shell commands, explaining technical concepts, automating repetitive tasks, and providing contextual guidance during cybersecurity assessments and system administration.

 ---

 ## Purpose

 The primary purpose of ShellGPT is to improve productivity by assisting users with command generation, troubleshooting, concept explanation, and workflow automation. During penetration testing, it serves as an intelligent assistant that supports learning and operational efficiency while still requiring human validation.

 ---

 ## Key Features

 - AI-powered command generation
 - Technical concept explanation
 - Shell command assistance
 - Terminal integration
 - Context-aware responses
 - Workflow automation support
 - Interactive learning

 ---

 ## Installation

 ### Python / pip

 ```bash
 pip install shell-gpt
 ```

 Alternatively using `pipx`:

 ```bash
 pipx install shell-gpt
 ```

 ### Configure API Key

 Set your OpenAI API key before using ShellGPT.

 Linux / macOS (bash/zsh):

 ```bash
 export OPENAI_API_KEY="<Your_API_Key>"
 ```

 Windows PowerShell:

 ```powershell
 setx OPENAI_API_KEY "<Your_API_Key>"
 ```

 ---

 ## Common Options / Commands

 | Command | Description |
 |--------|-------------|
 | `sgpt "<Prompt>"` | Send a natural-language prompt to ShellGPT and receive guidance, command suggestions, or explanations. |
 | `sgpt --shell "<Prompt>"` | Request shell command(s) tailored to the prompt (returns suggested commands). |
 | `sgpt --code "<Prompt>"` | Request code snippets or small scripts (e.g., Bash, Python). |
 | `sgpt --chat` | Start an interactive chat session with ShellGPT in the terminal. |
 | `sgpt --version` | Print the installed ShellGPT version. |
 | `sgpt --model <name>` | Specify the LLM model to use for the request (overrides default). |
 | `sgpt --temperature <0-1>` | Control response creativity (lower = deterministic, higher = creative). |

 ---

 ## Typical Workflow

 ```mermaid
 %%{init: {'theme': 'base', 'themeVariables': {'primaryColor': '#E3F2FD', 'primaryTextColor': '#0D47A1', 'primaryBorderColor': '#1565C0', 'lineColor': '#546E7A', 'secondaryColor': '#E8F5E9', 'tertiaryColor': '#F3E5F5'}}}%%
 flowchart TD
	 A[Define Objective] --> B[Prompt ShellGPT]
	 B --> C[Receive Commands / Guidance]
	 C --> D[Review AI Response]
	 D --> E{Accept Suggestion?}
	 E -->|Yes| F[Execute Approved Commands]
	 E -->|No| G[Refine Prompt]
	 G --> B
	 F --> H[Analyze Results]
	 H --> I[Document Findings]
	 I --> J[End]

	 classDef start fill:#E8F5E9,stroke:#2E7D32,stroke-width:2px,color:#1B5E20;
	 classDef process fill:#E3F2FD,stroke:#1565C0,stroke-width:1.5px,color:#0D47A1;
	 classDef decision fill:#FFECB3,stroke:#FF9800,color:#BF360C;
	 classDef end fill:#F3E5F5,stroke:#6A1B9A,stroke-width:2px,color:#4A148C;

	 class A start;
	 class B,C,D,F,H,I process;
	 class E decision;
	 class J end;
 ```

 ---

 ### Verify Installation

 ```bash
 sgpt --version
 ```

 ---

 ## Basic Syntax

 ```bash
 sgpt "<Prompt>"
 ```

 Example:

 ```bash
 sgpt "Generate an Nmap command to detect service versions."
 ```

 ---

 ## CEH Practical Example

 During **Module 14 – Web Application Hacking**, ShellGPT was used as an AI assistant to support web application security testing. It helped generate security-related commands, explain penetration testing concepts, and assist with vulnerability assessment activities. The AI-generated responses were reviewed and validated before being applied during the assessment.

 ---

 ## Advantages

 - Improves productivity.
 - Reduces time spent searching for commands.
 - Assists with technical explanations.
 - Supports learning while performing practical tasks.
 - Integrates directly with the terminal.

 ---

 ## Limitations

 - AI-generated responses may be inaccurate or incomplete.
 - Requires internet connectivity and API access.
 - Should not replace professional judgment.
 - Generated commands should always be reviewed before execution.

 ---

 ## Best Practices

 - Review every AI-generated command before executing it.
 - Never assume AI responses are always correct.
 - Avoid sharing sensitive information in prompts.
 - Use ShellGPT as an assistant rather than a replacement for technical knowledge.
 - Validate all security findings manually.

 ---

 ## Used In

 - Module 14 – Web Application Hacking

 *(This list will be expanded as additional modules are completed.)*

 ---

 ## Related Tools

 - Nmap
 - Burp Suite
 - Wapiti
 - cURL

 ---

 ## References

 - Official GitHub Repository: https://github.com/TheR1D/shell_gpt