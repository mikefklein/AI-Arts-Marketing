# How we built this site with an LLM

A working record of what it took to make the Marketing the Arts class website with an AI model, written so someone else can repeat it for their own site.

## The short version

The AI did the typing. The humans did the deciding. The site came out well because the brief was specific, the source content was real, and a person reviewed the result before it went anywhere.

## What you need before you start

| Ingredient | What we used | Why it matters |
| --- | --- | --- |
| A written brief | A one-page Google Doc: who the site is for, the brand personality, the look, the tone, the must-haves | The model can only hit a target you describe. This doc did most of the work. |
| Real content | The course syllabus | Stops the model from inventing facts. Dates, topics, guests and assignments all came from the syllabus. |
| Brand decisions made by people | The class took a "What's Our Brand??" quiz. The result: excitement as the personality, a worn canvas tote as the logo, a guerilla flyer-on-a-lamppost look, warm and witty writing. | Taste and identity are the human part. The model executes a brand; it should not pick one for you. |
| Sample writing | A finished welcome paragraph | One good sample teaches tone better than a list of adjectives. |
| Hard requirements | Alt text on images, text at 12 point or larger, high contrast, a playlist link titled "What We're Listening To" | Requirements you can check with a yes or no get met. Vague wishes do not. |
| An AI tool that can make files | Claude Code, connected to Google Drive so it could read the brief and syllabus directly | A plain chat window also works: paste the brief and syllabus in, then copy the code out. |
| A free place to host | GitHub Pages | Free, no ads, and you own the files. |

## The prompt, more or less

The request was a few sentences. What made it work was what it pointed to.

> In that folder there is a website parameters doc. It shows what the website should entail. The syllabus is in there too, so you have better content to build it out. We'll build it and then host it on GitHub so it's free.

If you are using a chat window with no file access, the same request looks like this:

> Build a single-page website for my graduate course. I'm pasting two things below: a brief that describes the audience, brand and requirements, and the course syllabus to use for content. Use only facts from the syllabus. Put everything in one HTML file so I can host it on GitHub Pages. Tell me anything you were unsure about.
>
> [paste the brief]
>
> [paste the syllabus]

## What the AI did, in order

1. **Read the sources.** The brief, the syllabus and the lecture talking points. It could not open the Google Form quiz, so it worked from the brand summary in the brief.
2. **Sorted the content for the audience.** The syllabus is written for enrolled students. The site is for prospective ones. So grading rubrics, late policies and university boilerplate stayed out. Topics, guests, projects and the welcome went in.
3. **Turned the look into concrete design choices.** "A flyer on a lamppost" became: a dark wall with a pole down the middle, paper flyers held up with masking tape and tilted a little, photocopy grain, a gig-poster lineup for the schedule, and tear-off tabs at the bottom for contact links.
4. **Drew the logo in code.** The tote bag is an SVG drawing written by hand in the page, with stains, stitching and a screen-printed starburst. No image generator and no stock art.
5. **Wrote the copy.** The welcome text is the instructor's, word for word. Everything else was rewritten from the syllabus in the brand voice.
6. **Built in the accessibility rules.** Body text is 18 pixels (about 13.5 point). The smallest text is 16 pixels (12 point). Text is near-black on paper, yellow or pink, or white and yellow on black, all above the WCAG AA contrast ratio of 4.5 to 1. Both images have text descriptions. There is a skip link, visible keyboard focus, and animation switches off for people who ask their device to reduce motion.
7. **Checked its own work.** It opened the page in a real browser at desktop and phone widths, took screenshots, and fixed what it saw: a logo that was too faded to read, a label that broke oddly, a headline that said "stapled" on a flyer that was taped.

## What a human still has to check

This list is the real lesson. None of it can be skipped.

- **Facts.** Are the dates, room, guest names and links right? The AI copied them from the syllabus, but syllabi change.
- **Permission.** Guest speakers are named and linked. Do they know they are on a public page? Is the instructor happy to have an email address listed?
- **Voice.** Does it sound like the class? A few lines were invented to fit the tone, such as the instructor blurb and the playlist intro. Rewrite anything that does not sound true.
- **Claims.** The page says there is no final exam, based on the grading table. Confirm it.
- **Links the AI could not test.** The build environment could not reach the Spotify playlist or the American University program page, so those two links were not clicked. Click them.
- **Accessibility with real tools.** Run the published page through WAVE (wave.webaim.org) and try it with only a keyboard.
- **Disclosure.** The footer says the site was built with AI and checked by people. Decide whether that wording is how the class wants to say it.

## Putting it online with GitHub Pages

1. Create a free account at github.com.
2. Click **New repository**. Name it (for example `marketing-the-arts`), set it to **Public**, and create it.
3. Click **uploading an existing file**, drag in `index.html`, `favicon.svg` and `.nojekyll`, and commit.
4. Go to **Settings**, then **Pages**. Under "Build and deployment", choose **Deploy from a branch**, pick `main` and `/ (root)`, and save.
5. Wait a minute or two. The site appears at `https://YOUR-USERNAME.github.io/marketing-the-arts/`.
6. To change the site later, edit `index.html` on GitHub (the pencil icon) or upload a new copy. The page updates on its own.

## What made the difference

- **Specific beats long.** "Like someone passed a flyer on a lamppost" is a better instruction than a paragraph about being edgy.
- **Give it your real material.** A syllabus in, real course details out. Nothing in, plausible fiction out.
- **Say who it is for.** "Prospective arts management students" decided what to keep and what to cut.
- **Put the rules in writing.** The accessibility list was three lines and every line got built.
- **Ask what it was unsure about.** The most useful output after the site itself was the list of things to verify.
- **Iterate out loud.** "Make the logo bigger", "this line is not us", "cut that section" are all fair prompts. The first draft is a draft.

## What this cost

- Money: nothing for hosting. The AI tool is the only possible cost, and a free tier can do a one-page site.
- Time: about one working session, most of it the AI's. Budget an hour of human review.
- Skills: knowing what you want, and reading the result with a critical eye. No coding.
