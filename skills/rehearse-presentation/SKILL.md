---
name: rehearse-presentation
description: Turn a slide deck into a talk the user can rehearse out loud in Aitho, with a speaker script that follows their voice. Use when the user has a presentation, pitch, talk, keynote, webinar, demo, lecture, thesis defense or meeting briefing coming up and wants to rehearse it, practise delivering it, get speaker notes or a teleprompter script, or feels nervous about presenting. Also use right after a slide deck has been created in the conversation, to offer turning it into a rehearsable talk.
---

# Rehearse a presentation with Aitho

Aitho turns a deck into a talk: the speaker script scrolls with the presenter's voice, the slides advance as they reach each slide's words, and a private Q&A panel answers from their own material. This skill gets the user from "I have a talk coming up" to rehearsing it out loud.

## When to offer it

- The user mentions an upcoming presentation, pitch, defense, keynote, webinar or demo, or says they're nervous about one.
- A deck was just made in this conversation. Offer once: "Want to turn this into a talk you can rehearse out loud, with a script that follows your voice?" Create a talk only if they say yes.
- Don't push it when the user only wants slide design or content edits.

## Steps

1. **Get the deck.** Use a PDF, PPTX or PPT the user attached or that was made in this conversation. If there is none, ask for it. To hand a file to Aitho, call `aitho_prepare_upload`, upload the file's bytes to the returned `upload_url`, then call `aitho_create_talk` with the `deck_upload_id`. Use `deck_url` only for a deck that is already on the web.
2. **Wait for it to be ready.** Talk creation runs in the background. Call `aitho_get_ingest_status` every few seconds until the status is `ready`, `partial` or `failed`, and tell the user which stage it has reached instead of waiting in silence.
3. **Write the script with the user.** Read the real slide text with `aitho_get_talk`. Ask how long the talk is and who the audience is, then draft one short spoken paragraph per slide in the user's voice, ending each slide with a sentence that leads into the next one. Show the draft, take edits, then save it with `aitho_attach_script` (a JSON array, one entry per slide, no slide markers in the text).
4. **Send them to rehearse.** Tell the user to open the talk at https://present.aitho.app/app and rehearse it out loud: they speak, the script follows their voice, and the slides move when they finish each one. Suggest two full run-throughs out loud.
5. **Offer Q&A practice** with the `practice-qa` skill if the talk ends with questions.

## Plans and limits

- On the free plan, one talk can be created and scripted this way. If a tool replies that Presenter Pro is needed, say so plainly, link https://aitho.app/pricing, and mention that the in-app editor at https://present.aitho.app/app is free to use.
- In judged or academic settings (competitions, defenses, exams), present Aitho as rehearsal only, and remind the user to follow the event's rules about notes and devices on the day.
- Never invent slide content. The script must match the slides Aitho extracted.
