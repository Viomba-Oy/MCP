# Viomba MCP

[![MCP](https://img.shields.io/badge/MCP-2025--11--25-blue)](https://modelcontextprotocol.io)

Viomba MCP brings attention prediction, creative generation, and video analysis into your AI workflow. Give your assistant a creative, a URL, or a video — and get back real attention data, heatmaps, and scored outputs without leaving your client.

**Built on real gaze data**

Viomba's predictions are powered by neural models trained on Tobii infrared gaze fixation data, collected from real users in real browsing environments across markets. This means *seen* and *viewtime* metrics reflect genuine fixations — not loose viewability proxies. The distinction matters: Tobii infrared separates true fixations from saccades at the measurement level, which is why Viomba numbers often differ from other attention tools.

---

## Tools

### Attention & Analytics
| Tool | Description |
|---|---|
| `viomba_creative_prediction` | Predict attention KPIs for an ad creative |
| `viomba_heatmap_prediction` | Predict gaze heatmap for a display ad |
| `viomba_focus_prediction` | Predict visual attention heatmaps for a video ad |
| `viomba_ad_slicer` | Slice a ad creative into timed PNG screenshots |

### Creative Generation
| Tool | Description |
|---|---|
| `viomba_generate_creative` | Start an ad creative generation job |
| `viomba_refine_creative` | Iterate on a previously generated creative |
| `viomba_check_generation` | Poll status and retrieve results |
| `viomba_get_creative` | Fetch a creative with full HTML |
| `viomba_list_generations` | List your generation requests |

### Video Analysis
| Tool | Description |
|---|---|
| `viomba_analyze_video` | Analyze a video for attention, audio/video events, and AVS sync score |

### Site Intelligence
| Tool | Description |
|---|---|
| `viomba_generate_site_map` | Generate an attention-weighted site map for a set of domains |

### Usage & Account
| Tool | Description |
|---|---|
| `viomba_my_usage` | Usage stats for your connected client |
| `viomba_history` | Paginated tool-call history |
| `viomba_tool_breakdown` | Per-tool call counts and latency |

---

## Getting Started

Add the server URL to your MCP client and connect — that's it. The OAuth flow
runs automatically on first connect. If you don't have an account yet, you'll be
guided through registration during sign-in.

**Claude Desktop** — open Settings → Connectors → Add connector and paste
`https://mcp.viomba.com/mcp`. The sign-in prompt opens in your browser automatically.

**Cursor / VS Code** — add the URL in your MCP server settings and connect.
The sign-in prompt opens in your browser automatically.

**n8n** — add an MCP node with URL `https://mcp.viomba.com/mcp` and select
OAuth as the credential type.

Once signed in, the connection is live and your credits are linked automatically.

---

## Manual token (advanced)

If your client doesn't support OAuth or you need a long-lived token for
automation, you can issue a **Persistent Access Token (PAT)** from the
[dashboard](https://mcp.viomba.com) and pass it as a Bearer header:

```json
{
  "mcpServers": {
    "viomba": {
      "type": "streamable-http",
      "url": "https://mcp.viomba.com/mcp",
      "headers": {
        "Authorization": "Bearer <your-token>"
      }
    }
  }
}
```

---

## Compatible Clients

- [Claude Desktop](https://claude.ai/download)
- [Cursor](https://cursor.com)
- [VS Code (Copilot MCP)](https://code.visualstudio.com)
- [n8n](https://n8n.io)
- Any client supporting MCP Streamable HTTP transport (spec 2025-11-25)

---

## Pricing

Usage is credit-based — each tool call deducts credits from your Viomba account.
See [viomba.com/pricing](https://viomba.com/pricing) for rates.

---

## Links

- [Dashboard](https://mcp.viomba.com)
- [Viomba](https://viomba.com)
- [Viomba-Id](https://id.viomba.com)
- [MCP Specification](https://modelcontextprotocol.io)
