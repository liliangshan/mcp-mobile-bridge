# mcp-mobile-bridge 🚀

**Empowering Gemini Mobile with decentralized, direct SSE-MCP integration. Bridging mobile AI with private standards and public tools via zero-proxy, client-side requests.**

---

## 💡 The Vision

The Model Context Protocol (MCP) is the "USB-C for AI." Currently, mobile AI assistants operate as "Isolated Brains," lacking access to private, structured project contexts. We propose that the **Gemini Mobile App** should natively support **Direct, Decentralized SSE (Server-Sent Events) MCP integration**.

## 🎯 Key Proposal: Zero-Proxy Architecture

Unlike traditional cloud-to-cloud integrations, this repository advocates for a **Direct Request Architecture**:

1. **Bypass Middlemen**: The Gemini App makes direct HTTPS/SSE requests from the mobile client to the MCP endpoint.
2. **Data Sovereignty**: Private engineering standards and sensitive data never touch third-party transit servers.
3. **Latency & Reliability**: Eliminating proxies reduces Round-Trip Time (RTT), critical for Gemini Live multimodal interactions.

### Technical Architecture Diagram


sequenceDiagram
    autonumber
    participant App as Gemini Mobile App
    participant Local as Private MCP (SSE)
    participant Public as Public MCP (SSE)

    Note over App: Step 1: Direct Handshake
    App->>Local: GET /sse (Direct)
    Local-->>App: Tools Discovery
    
    Note over App: Step 2: Global Knowledge
    App->>Public: Fetch Real-time Data
    Public-->>App: Structured Metadata

    Note over App: Step 3: Standards Sync
    App->>Local: Call Tool: get_project_structure
    Local-->>App: Directory Map (Context Caching)


---

## 🛠️ Implementation Case: Software-Defined Standards (SDS)

Using our reference implementation `@liangshanli/mcp-server-project-standards` as a benchmark, this integration enables:

* **Namespace Isolation**: Using `PROJECT_PREFIX` to prevent context pollution between different projects.
* **Hierarchy Mapping**: A "dehydrated" directory tree that reduces token consumption by up to **90%** via Gemini 3 Context Caching.
* **Instructional Imprint**: Forcing the AI to adhere to specific engineering protocols even when working from a mobile device.

---
## 📝 RFC (Request for Comments)

We invite the Google Gemini Engineering team and the global MCP community to discuss:

1.  **SSE Client Implementation**: Native `EventSource` support within the mobile app.
2.  **Dynamic Discovery**: Auto-mapping `list_tools` to Gemini's function-calling layer.
3.  **Security**: Support for standard `Authorization` headers and `CORS` for secure E2E connections.

---
## 🤝 Call to Action

* **Star this repo** to show support for the decentralized AI movement.
* **Join the Discussion**: [Open an Issue](https://github.com/liliangshan/mcp-mobile-bridge/issues) to share your feedback.
* **Connect**: Mention **@LoganKilpatrick** or the Gemini DevRel team on social media to highlight this proposal.

---
*Created by @liliangshan - Advocating for an open, decentralized AI infrastructure.*
