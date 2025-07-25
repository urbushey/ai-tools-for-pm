# AI Tools for Product Management & Light Development Work 🦾

Some notes about what works for me. The concepts are more interesting than any one specific tool.

See this project for specific prompts. 

## Key Principles

**Context is everything:** The more relevant context you give AI tools, the better they work. Anytime I find myself adding context to a conversation, I ask myself if it could go in a re-usable prompt that is embedded into a project. 

**Connect your tools:** Multiple MCP servers in a single client are magic: Pull context from one system, use it to create new content for another system, and announce the update in slack, all from a single prompt. 

**Be Explicit:** These tools are evolving fast. What doesn't work today might work perfectly in a month.

## Product Management Stack

### Spec Writing & Communication
**My setup:** [Claude](https://claude.ai) + [Claude Projects](https://www.anthropic.com/news/projects) as a context-loaded AI assistant with company knowledge

**The approach:** Dump your company knowledge base, API docs, marketing stuff, meeting notes into projects for context
- Whitelist URLs from your marketing site and GitHub repos 
- Set up prompts for your voice as a PM and whatever corporate voice you need

**Examples:**
- "Build me a product spec for this problem, here are some meeting notes..."
- "Create the release notes for this epic..."
- "Find and draft updates for any kb article related to this project..."
- "Create a quick LinkedIn announcement with exciting emoji for this product release..."

**Alternatives:**
ChatGPT + [Custom GPTs](https://openai.com/index/introducing-gpts/) does basically the same thing - it's just pre-loaded context (ie simple "RAG" / "retrieval augmented generation").

### Meetings
**My Setup:** Record everything, feed transcripts to AI
- Google Meet + Gemini for internal stuff
- [Avoma](https://www.avoma.com/) for customer meetings (love the clip feature)
  - Meeting note taking tools are all pretty similar, the feature Avoma has that I love is Clips: jump to specific points in a customer convo or demo, make a clip of the relevant content, and send the URL out to anyone for reference
- Feed transcripts into AI discussions with Claude above

### Workflow Automation
**My setup:** Claude Desktop + MCP Servers to connect AI directly to work tools

**The approach:** Instead of copy/pasting between AI and your tools, let AI read and write directly to your project management, docs, etc.

**My MCP servers:**
- [Shortcut MCP](https://help.shortcut.com/hc/en-us/articles/36443434285844-MCP-Server) - read and create epics/stories for projects. We use shortcut, [JIRA](https://www.atlassian.com/blog/announcements/remote-mcp-server)) also has a great MCP server.
- [Notion MCP](https://developers.notion.com/docs/mcp) - create and update product specs in our Product Backlog database
- [Narrative MCP](https://github.com/narrative-io/data-collaboration-mcp/tree/main) - custom server we're building for our platform

**Examples:**
- "Find my most recent convo in Slack with my boss and create a big ticket, make sure to attach the screenshot"
- "Create a new epic in Shortcut for the SDK refactor project"
- "Extrapolate the todos from these meeting notes and update the product spec in Notion with new requirements"
- "Pull all the stories from this epic and create release notes"

**Why this works:** These 3 combined let me create specs, release notes, LinkedIn posts, etc. without constantly switching between tools and copy/pasting.

### Research & Strategy  
**My setup:** [ChatGPT Deep Research](https://openai.com/index/introducing-deep-research/) for competitive and strategic research (Claude's [Research feature](https://www.anthropic.com/news/research) is also great, I find my results are slightly more nuanced and predictable with ChatGPT)

**The approach:** Use AI's research capabilities for stuff that would take you hours of manual digging

**Examples:**
- Competitive analysis: "Research our top 5 competitors and their recent product announcements"
- Partnership opportunities: "Find smaller startups in the data space that might be good integration partners"
- Board prep: "Pretend you are a board member for my company. What questions are you going to ask about Q3..."

### Technical Concept Digestion
**My setup**: [Google Notebook LM](https://notebooklm.google/) for pulling together hard technical concepts or market research notes that I'm finding difficulty concentrating on in written form. Ask for a podcast to explain the concept to me. This also works nicely with our own press releases, because it can help you figure out what's interesting and what's not - kind of like having a third party play back your thoughts for you to see how they are coming off to someone else.
**Examples**:

- Upload dense technical documentation and get a conversational explanation
- Feed in market research reports and get a podcast-style summary
- Upload your own press releases to see how they sound to an outsider

### Bug Reporting
**My setup**: [Gemini Live](https://gemini.google/overview/gemini-live/) - screen share me clicking through our UI to generate a bug report and throw it into Shortcut/JIRA. Also works with ChatGPT (upload the video after the fact and give it a prompt). Wish Claude had this feature.
**Examples**:

- Screen record a bug, have AI write up the reproduction steps
- Walk through UI flows and get usability feedback
- Generate detailed bug reports with screenshots automatically

## Developer / Vibe Coding Stack

### Code Generation & Editing
**My setup:** 
- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) (CLI) for nost coding tasks
- Cursor as my main editor
- Same MCP servers from above for workflow integration

**Why Claude Code:** It can see your entire project structure and make changes across multiple files. Way better than copying code snippets from ChatGPT.

**Why Cursor:** This is just what I started with. Better than CoPilot in that you can swap out the model you're using, and the integration with Claude Code is nice (Claude Code can run in the Cursor terminal, and will display files it wants to edit for you in the Cursor editor.) 

### Task Management Integration
**My setup:** [Claude Code Slash Commands](https://docs.anthropic.com/en/docs/claude-code/slash-commands) for project workflow automation

**The approach:** Connect coding directly to your project management workflow

**Examples:**
- `/ticket` - "Flesh out a JIRA ticket"
- `/start` - "Start work on this JIRA ticket" 
- `/pr` - "Create a Pull Request from the current state of the project"
- `/docs` - "Update the documentation"

**Why this works:** No context switching between your terminal, JIRA, GitHub, etc. Everything flows together.

