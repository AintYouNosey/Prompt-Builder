🎨 Style Organizer tab
What it does: Loads your CSV style files and displays them as a visual card grid so you can browse and pick styles without scrolling through a dropdown.
How to use it:

Hit ⊕ Load CSV to import any Forge/A1111 style CSV file
Cards are grouped by category automatically — LIGHTING_Golden_Hour goes under LIGHTING, STYLE_Watercolor goes under STYLE
Click a card to select it — its prompt gets added to the footer
Click again to deselect
★ on a card to favourite it
Right-click a card to copy its prompt, edit it, or delete it
Click a category header (▼/▶) to collapse/expand it — the app remembers which ones you had collapsed

Source toggles (top bar): each loaded CSV file gets its own toggle pill. Click to turn it on/off. You can have 5 CSVs loaded but only show 2 at once. ★ Favs and 🕑 Recent filter on top of whatever's toggled.
Sidebar: click any category to see only that category's cards.
Search: filters cards by name or prompt content across all visible sources.

👤 Character Builder tab
What it does: Structured fields for building a character description. Everything you type gets automatically formatted with context so you don't have to.
Example: Type red in Hair Colour → outputs red hair. Type 12 in Age → outputs 12 years old. Type sidecut in Hair Style → outputs sidecut hairstyle.
Fields available:

Body: Gender, Species, Age, Build, Height, Skin/Fur
Face: Eye colour, Eye shape, Nose, Lips, Facial hair, Expression
Hair: Colour, Style, Length, Texture
Clothing: Top, Bottom, Footwear, Accessories, Outfit style
Extra Positive: Free-type anything that doesn't fit the fields above
Character Negative: Things to exclude for this character (goes into the negative prompt)

🐾 Furry Mode toggle: flips Skin/Fur to Fur Colour, outputs red fur instead of red skin, and prepends anthro automatically if no species is specified.
Saved characters: Hit Save, give it a name, and the whole character is stored. Load it back any time — useful if you regularly generate the same character. All fields including furry mode and free-form notes are saved.

✚ Style Builder tab
What it does: Create new styles from scratch and add them to any of your loaded CSVs, or a brand new one you create here.
How to use it:

Type a Category (e.g. LIGHTING) and a Style name (e.g. Sunset) — the full name becomes LIGHTING_Sunset
The category field autocompletes from your existing categories
Type tags in the Positive or Negative tag fields — the tag autocomplete searches your tags.json as you type

Tag search modes (checkboxes above the field):

Default — searches tag names only
Similar — also matches synonyms, so typing woman can surface 1girl
Category — filter by tag category (Subject, Hair, Attire, etc.) with descriptions shown

Clicking a suggestion:

Normal click → inserts 1girl
⚖ Weighted toggle on → inserts (1girl)1.0 ready to adjust the weight
⚡ Brute Force toggle on → inserts 1girl, single girl, one woman, solo character (expands to all synonyms, for tags that have them)

Save to: dropdown lets you pick which CSV to add the style to — or create a brand new one with ✚ New CSV.
CSV Editor (bottom of this tab): pick any loaded CSV, browse all its styles, delete individual ones, and hit ⬇ Export CSV to save it as a shareable file. This is how you'd build and export something like pokemon.csv to share with friends.

🎲 Wildcards tab
What it does: Random prompt variation using .txt wildcard files. Put your wildcard files in a wildcards\ folder next to the exe.
How to use it:

Each .txt file appears as a row (e.g. Accessory, Lighting, Outfit)
＋ → picks a random line from that file and adds it to your positive prompt (row turns green)
－ → picks a random line and adds it to your negative prompt (row turns red)
You can have both ＋ and － active on the same wildcard at once
Click ＋ or － again on an active wildcard → re-rolls to a different line
🎲 Re-roll All → re-randomizes every active wildcard at once
×＋ / ×－ → remove just that side

If you have accessory.txt and accessory_negative.txt they automatically pair into one row — ＋ uses the positive file, － uses the negative file.
Wildcard contributions appear in the main footer prompt alongside your styles.

The footer (bottom, always visible)
This is where your full assembled prompt lives no matter which tab you're on.
Prompt order:

Quality words (editable in Character Builder tab)
Character fields
Selected styles (one block per style)
Wildcard picks

Copy buttons:

⎘ Copy Positive — just the positive prompt
⎘ Copy Negative — just the negative prompt
⎘ Copy Block — both together formatted as POSITIVE:\n...\n\nNEGATIVE:\n... for easy pasting

Weight Editor: if any selected styles contain weighted tags like (watercolor)1.3, sliders appear so you can nudge weights up or down without editing text. Each slider has a ↺ reset button.
Conflict detection: if two selected styles contradict each other (e.g. one adds flat lighting and another adds dramatic lighting) a red warning banner appears above the prompts telling you exactly which tags are clashing.

Header buttons (always visible)

🔍 Duplicates — scans all loaded styles for duplicate names or identical prompts across CSVs. Shows results with a Delete button for each duplicate found
🎲 Random — picks one random style from whatever you're currently viewing
🔀 Constrained — picks a random style but won't pick a second one from a category you already have selected
💥 Chaos — ignores your styles entirely, pulls random raw tags straight from tags.json with a slider for how many (1–30)
✕ Clear — deselects all selected styles


Example workflow

"I want to generate a red-haired wolf girl in a fantasy outfit with soft lighting"


Character Builder → Gender: female, Species: wolf, Hair Colour: red, Hair Style: long flowing, toggle 🐾 Furry Mode on → outputs female, wolf, red fur, long flowing hairstyle
Style Organizer → click STYLE_Fantasy + LIGHTING_Soft
Wildcards → hit ＋ on Outfit to randomly pick a fantasy outfit variation
Footer shows the full combined prompt
Hit ⎘ Copy Block → paste into InvokeAI → generate
