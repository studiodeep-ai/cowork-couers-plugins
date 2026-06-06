# Cowork Course Plugins

A Claude Code plugin marketplace built for the Studio Deep Cowork course. Each plugin groups a set of skills around a professional domain — install a plugin and Claude gets a set of new, specialized capabilities tailored to that domain.

Plugins and skills in this marketplace are designed for owners and creative leads of small creative agencies in the Benelux. They connect to external tools (Apify, LinkedIn) and follow opinionated tone-of-voice and workflow guidelines built into the skill files.

---

## Plugins

### Social Media

Skills for creating and coaching social media content.

| Skill | Description |
|---|---|
| [linkedin-post-proposal](#linkedin-post-proposal) | Scrapes industry voices on LinkedIn, identifies trending topics, and generates three on-brand post proposals in your tone of voice. Then coaches you to a final post. |

---

## Skill reference

### linkedin-post-proposal

**Plugin:** Social Media

Monitors what the right voices are posting on LinkedIn, picks the three most relevant topics, and writes three post proposals — in Dutch (Flemish), in first person, following a strict tone-of-voice guide. After you pick a proposal, the skill stays active as a writing coach until the post is done.

**Trigger phrases:**
- "write me a LinkedIn post"
- "what should I post on LinkedIn"
- "give me a LinkedIn idea"
- "help me with a post"
- "write something for LinkedIn"

**What it does:**
1. Shows you the curated list of LinkedIn profiles it will scrape and asks for confirmation
2. Scrapes the last 3 posts from each profile using Apify (`harvestapi/linkedin-profile-posts`)
3. Identifies the top 3 topics, prioritising new tool releases over techniques over opinions
4. Writes three post proposals following the Studio Deep tone-of-voice guide (hook, context, uitleg, CTA, hashtags)
5. Lets you pick a proposal
6. Coaches the chosen post to completion, citing tone-of-voice rules with each suggestion

**Reference files inside the skill:**
- `references/linkedinprofiles.md` — the list of profiles to scrape; edit this to add or remove voices
- `references/tone-of-voice-linkedin.md` — the full writing guide the skill follows

**Requirements:** Apify MCP connector must be active in your Claude Code session.

---

## Structure

```
.claude-plugin/
  marketplace.json
plugins/
  social-media/
    .claude-plugin/
      plugin.json
    skills/
      linkedin-post-proposal/
        SKILL.md
        references/
          linkedinprofiles.md
          tone-of-voice-linkedin.md
```
