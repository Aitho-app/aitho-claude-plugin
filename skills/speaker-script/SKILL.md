---
name: speaker-script
description: Write, shorten or improve the speaker script for a talk in Aitho, slide by slide, so it sounds natural spoken out loud. Use when the user wants speaker notes, a talk track, a teleprompter script, to cut a talk to a time limit, to fix transitions between slides, or to rewrite a script that sounds like reading.
---

# Write or improve a speaker script in Aitho

## Steps

1. **Pick the talk** with `aitho_list_talks`, then read it with `aitho_get_talk` to see each slide's text and any existing script.
2. **Agree the target.** Ask for the time limit and the audience. A spoken pace of about 130 words a minute is a reasonable default for estimating length; tell the user it's an estimate.
3. **Write for speaking, not reading.** One short paragraph per slide. Lead with the point, use the user's own words where they gave them, and end each slide with a sentence that sets up the next slide. Avoid reading the slide aloud.
4. **Review together.** Show the full script with slide numbers and the estimated time. Make the user's edits.
5. **Save it** with `aitho_attach_script`: a JSON array with one string per slide, in slide order, the same length as the slide count, with no slide markers inside the text. If a slide is a video the user talks over, set `clips[slide].narrate_over` to true.
6. **Rehearse.** Tell the user to open the talk at https://present.aitho.app/app and rehearse out loud; the script follows their voice.

If a tool replies that Presenter Pro is needed, explain the free plan's one-talk limit, link https://aitho.app/pricing, and mention that scripts can also be edited for free in the Aitho app.
