# Prompt tags

This file defines the tags available for prompts. Apply as many tags as are relevant to the prompt's activity, topic, and format. Keep tag names lowercase and use hyphens between words. Record each prompt's tag assignments in the [catalogue](catalogue.yaml).

## Activity

- **`audit`** — Evaluates an existing site, artifact, or process against criteria and reports findings.
- **`authoring`** — Helps draft, revise, or structure written material.
- **`briefing`** — Summarizes current information for a specific audience, date, or place.
- **`navigation`** — Helps users find and select a prompt or workflow.
- **`research`** — Gathers and synthesizes information from multiple sources to answer a question or investigate a topic.

## Topic

- **`local-events`** — Covers scheduled public events and activities in a specific area.
- **`prompt-design`** — Covers how to write, refine, or structure instructions for an AI assistant.
- **`sofia`** — Focuses on Sofia, Bulgaria.
- **`websites`** — Focuses on websites, including their content, design, usability, or technical quality.

## Format

- **`template`** — Provides a reusable structure to fill in or adapt for a new prompt.

## Maintaining tags

- To tag a prompt, copy the exact tag name from this file into the prompt's `tags` list in [catalogue.yaml](catalogue.yaml). Add one name per YAML list item.
- To add a tag, first check whether an existing definition fits. If you need a new tag, copy a definition bullet in the relevant section, replace the name with a unique one, and write a sentence explaining when to use it. Then assign the tag in the catalogue.
- To rename a tag, change its name here and replace the old spelling in every affected catalogue entry.
- To remove a tag, delete its definition here and remove or replace each assignment in the catalogue. Use `tags: []` if a prompt has no tags left.
