## 1. Purpose

Help the user discover available prompts and start one by replying with its menu number.

## 2. Context

- The standalone word `menu` opens the menu.
- A reply consisting of a single number selects an entry from the most recently displayed menu while a selection is pending.

## 3. Objectives

- Show the available prompts with a short description of each.
- Start the selected prompt when the user replies with its number.

## 4. Scope and boundaries

- Reserve `0` for showing the menu again.
- Exclude examples, general capabilities, and entries whose prompt instructions cannot be verified.

## 5. Sources and evidence

- Use [catalogue.yaml](catalogue.yaml) as the prompt registry. It maps each menu number to a title, description, Markdown file, and list of assigned tags.
- Use [tags.md](tags.md) for the available tag names and their meanings. For remote access, open the [raw GitHub tag definitions](https://raw.githubusercontent.com/h111359/prompts/main/tags.md).
- Read the catalogue from the local checkout when available. Otherwise, open the [raw GitHub catalogue](https://raw.githubusercontent.com/h111359/prompts/main/catalogue.yaml).
- Verify that each registered prompt file is available before listing it.
- Use the selected file as the source of instructions for the task.

### Accessing prompt files

- When using a local catalogue, read each prompt at its registered `file` path relative to the repository root. If the local file is unavailable, try its raw GitHub URL.
- When using the raw GitHub catalogue, open each prompt through its raw GitHub URL.
- Build the raw URL by appending the exact registered `file` path to `https://raw.githubusercontent.com/h111359/prompts/main/`. Use a concrete file path in place of `*.md`.
- Open the raw URL in a browser or fetch it with an HTTP-capable tool to read the Markdown. For example, the registered path `00003-prompt-engineer.md` opens [Prompt Engineering](https://raw.githubusercontent.com/h111359/prompts/main/00003-prompt-engineer.md).
- If neither source can provide a needed file, tell the user which file is missing and ask them to attach it or paste its contents.

### Maintaining the catalogue by hand

1. Add or edit the prompt's Markdown file. Then copy or update its entry under `prompts` in [catalogue.yaml](catalogue.yaml). The comments at the top explain each field and its indentation.
2. Choose applicable tags from [tags.md](tags.md). Define any new tags there before assigning them in the catalogue.
3. If you rename or move a prompt file, update its `file` path and keep its menu number. If you remove a prompt, delete its catalogue entry.
4. Type `menu` to refresh the list, then select the edited entry by number to check that it opens the intended prompt.

## 6. Rules

- On `menu` or `0`, rebuild the menu from the catalogue and open a new selection.
- Resolve a selection against the menu that the user saw.
- For a valid prompt selection other than `0`, read the selected file and follow its instructions. The number serves as the prompt's trigger.
- For a prompt tagged `template`, use the selected file to help the user draft or revise a prompt.
- If the selected prompt requires an input the user has yet to provide, ask for that input and continue with the selected prompt when they reply.
- If a number is absent from the displayed menu, show the available choices again and ask for a valid number.
- If the selected file has become unavailable, tell the user and refresh the menu.
- Close the pending menu selection when a prompt starts or the user moves on to another request.

## 7. Response requirements

- Display the heading **Menu** followed by entries in ascending numerical order.
- Format each entry as a bullet with its number, prompt name, and a brief description so the numbers display exactly as assigned in the catalogue.
- For prompts loaded from GitHub, link each prompt name to its raw file URL.
- End with **Reply with the number of the prompt you want to follow.**
- If the catalogue is unavailable or no other prompt files are available, display only `0` and explain why.

## 8. Completion criteria

- Every displayed entry maps to one verified prompt file.
- Each valid prompt selection starts the corresponding prompt or requests its missing input.
- Selecting `0` displays the current menu.
