## 1. Purpose

Help the user discover available prompts and start one by replying with its menu number.

## 2. Context

- The repository stores prompts in Markdown files with numeric filename prefixes.
- The standalone word `menu` opens the menu.
- A reply consisting of a single number selects an entry from the most recently displayed menu while a selection is pending.

## 3. Objectives

- Show the available prompts with a short description of each.
- Start the selected prompt when the user replies with its number.

## 4. Scope and boundaries

- Reserve `0` for showing the menu again.
- Exclude examples, general capabilities, and entries whose prompt instructions cannot be verified.

## 5. Sources and evidence

- Use the numbered Markdown files in this repository to discover available prompts.
- Read each candidate file to verify its purpose and write its description.
- Use the selected file as the source of instructions for the task.

## 6. Rules

- Use each task prompt's filename prefix as its menu number, dropping leading zeroes.
- Osn `menu` or `0`, rebuild the menu from the available files and open a new selection.
- Resolve a selection against the menu that the user saw.
- For a valid selection, read the selected prompt and follow its instructions. The number serves as the prompt's trigger.
- If the selected prompt requires an input the user has yet to provide, ask for that input and continue with the selected prompt when they reply.
- If a number is absent from the displayed menu, show the available choices again and ask for a valid number.
- If the selected file has become unavailable, tell the user and refresh the menu.
- Close the pending menu selection when a prompt starts or the user moves on to another request.

## 7. Response requirements

- Display the heading **Menu** followed by entries in ascending numerical order.
- Format each entry as a bullet with its number, prompt name, and a brief description so filename-derived numbers display exactly as assigned.
- End with **Reply with the number of the prompt you want to follow.**
- If no task prompts are available, display only `0` and tell the user that no task prompts are available.

## 8. Completion criteria

- Every displayed task entry maps to one verified prompt file.
- Each valid number starts the corresponding prompt or requests its missing input.
- Selecting `0` displays the current menu.
