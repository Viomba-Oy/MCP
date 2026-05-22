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
| `viomba_creative_prediction` | Predict attention KPIs (seen %, view time) for a display ad |
| `viomba_heatmap_prediction` | Predict gaze heatmap for a display ad |
| `viomba_ad_slicer` | Slice an ad creative into timed PNG screenshots |

### Creative
| Tool | Description |
|---|---|
| `viomba_generate_creative` | Start an ad creative generation job |
| `viomba_refine_creative` | Iterate on a previously generated creative |
| `viomba_check_generation` | Poll status and retrieve results |
| `viomba_get_creative` | Fetch a generated creative with full HTML |
| `viomba_list_generations` | List your creative-generation requests |
| `viomba_cancel_generation` | Cancel a pending or running creative job |
| `viomba_generate_site_map` | Generate an attention-weighted site map for a set of domains |

### Video
| Tool | Description |
|---|---|
| `viomba_analyze_video` | Analyze a video for attention, audio/video events, and AVS sync score |
| `viomba_focus_prediction` | Predict visual attention heatmaps for a video ad |
| `viomba_request_upload` | Get a one-time browser upload URL for sharing a local video file |
| `viomba_check_upload` | Poll for upload completion; returns a token usable as `videoUrl` |

### Meta Marketing API
Connect a Meta credential in the Viomba dashboard, then drive your real ad library from MCP.

| Tool | Description |
|---|---|
| `viomba_list_meta_credentials` | List Meta credentials connected to your Viomba account |
| `viomba_set_meta_credential` | Activate a credential for this MCP session |
| `viomba_list_meta_ad_accounts` | List Meta ad accounts accessible to the active credential |
| `viomba_list_meta_ad_creatives` | List ad creatives within a Meta ad account |
| `viomba_get_meta_creative_prediction` | Trigger or poll attention prediction for a Meta ad creative |

### Usage & Account
| Tool | Description |
|---|---|
| `viomba_my_usage` | Usage stats and credit balance for your connected client |
| `viomba_history` | Paginated tool-call history |
| `viomba_request_detail` | Inspect a single historical tool call (request + result) |
| `viomba_tool_breakdown` | Per-tool call counts and latency |
| `viomba_fetch_image` | Fetch an image attachment returned by a previous tool call |

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
