# Content Engine Integration — Pet Services Vertical

This repo is a **vertical** component of the AgentOS Content Engine
(hub: `mcp-idea-publisher`). The on-demand pet grooming marketplace model
feeds one Instagram page:

| Channel | Category | Cadence |
|---|---|---|
| @find.petboarding | Pet Supplies | every 6h |

The manifest is [`content.component.yaml`](./content.component.yaml); the hub
mirrors it in `channels.yaml`. As this repo grows (service tiers, groomer
onboarding, city playbooks), add those documents to `seed_sources` so the
engine grounds content in real product thinking instead of generic pet facts.

Generate a post from the hub:

```bash
curl -s -X POST localhost:8000/channels/find.petboarding/generate \
  -H "Content-Type: application/json" -d '{}'
```

Full architecture and licensing: `mcp-idea-publisher/docs/CONTENT_ENGINE.md`.
