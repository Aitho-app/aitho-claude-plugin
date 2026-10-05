---
name: practice-qa
description: Practise the questions an audience, panel, judges or investors are likely to ask after a presentation, with answers grounded in the presenter's own slides and documents in Aitho. Use when the user is worried about Q&A, asks what questions they might get, wants a mock Q&A or pitch grilling, or is preparing for a defense, board update, investor pitch or interview-style presentation.
---

# Practise Q&A with Aitho

## Steps

1. **Find the talk.** Call `aitho_list_talks` and confirm which talk with the user. If they have none yet, use the `rehearse-presentation` skill first.
2. **Read the material.** Call `aitho_get_talk` for the slide text. If the user has supporting documents (a report, a data sheet, an RFP), offer to attach them with `aitho_add_documents` so answers can draw on them.
3. **Build the question list.** From the slides, write 6 to 10 questions this audience is likely to ask: at least two hard ones (weak points, numbers, risks, "why not X"), one they're probably dreading, and one off-topic one. Ask the user who will be in the room to tune them.
4. **Run the practice.** Ask one question at a time and let the user answer in their own words first. Then give brief feedback: was it under 30 seconds, did it answer the question first, what to cut.
5. **Show a grounded answer when useful.** Call `start_presentation` for the talk, then `ask` with the question to get an answer drawn from their own material, and compare it with theirs. `ask` uses the plan's copilot meter and may run a web lookup when their material doesn't cover the question, so use it for the hard questions rather than every one.
6. **Finish** with the three questions they should rehearse out loud again, and their best one-sentence answer for each.

## Notes

- Keep feedback specific and short. The goal is a calm, three-sentence answer, not a perfect one.
- In judged or academic settings, this is preparation only; follow the event's rules on the day.
