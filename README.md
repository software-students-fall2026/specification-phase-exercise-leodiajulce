# Specification Phase Exercise

A little exercise to get started with the specification phase of the software development lifecycle. In this exercise, your team specifies a set of improvements and new features for [The Slide Machine](https://theslidemachine.com) — see the [instructions](instructions.md) for detail, and the [background](background.md) for an introduction to the software product you are tasked with extending.

## Team members

See instructions. Delete this line and replace with a list of the names of your team members, including links to each one's GitHub profile.

## Review of the Current Application

##Strengths
1. Slide makers can control the freedom of AI. During the slide generation from speech, the instructor can set how much "freedom" the model is given rather than just accepting a single fixed behaviour. This allows the instructor to create a better presentation by deciding whether the slides need strict adherence to prepared material or if it could benefit from looser interpretetion. 
2. System health and plan usage are visible without being intrusive and disruptive. The "API ok" and "Free plan ok" status bar shows two different pieces of state, whether AI services are reachable, and whether the account is still within plan. The information is displayed in a simply-looking single line that doesn't compete for attention with the rest of the app.
3. Generated slides are visually consistent with each other. Every slide in the deck follows the same design template, so a presentation created one slide at a time from an unscripted speech still holds together as one piece work.
4. A lecture can be given context before it starts. A project can be "seeded" ahead of time with some prepared material, like outline, key terms, objectives, style, etc. So the system starts the lecture with some context behind, therefore being able to generate more accurate and relevant content.

##Weaknesses

5. The account-type prompt never appears. AUTH-6 specifies a one time prompt shown after the registration, asking whether the account belongs to a student, an educator, or another kind of user. Delievery Roadmap shows AUTH-6 as shipped. A newly created account was never shown this prompt at any point.
6. Accounts that never answer question (from finding 5) keep public defaults, so students are exposed to public by default. AUTH-6 intends public defaults only for educators, however due to the absence of the question (from finding 5) students keep public by default as well, therefore publishing their work without ever having made this choice.
7. Discover is cluttered with what appear to be accidental test lectures and other material with no value to readers. A large portion of presentations in discover section are named "Untitled Lecture" and most of them sit in "Default Project", the untitled project the app seem to create for the user's first lecture. The pattern suggests there are first run experimements that authors likely did not intend to publish. Most of them are useless to readers and genuinly interesting and useful courses might be lost among them.
8. A lecture's visibility is not shown anywhere on the lecture itself. The only plce visibility appears at is inside the lecture's settings, which read "Public (visible to eveyrone)." Additionally to that, the owner does not see their own public lecture in discover so there is no way to confirm how others see the presentation.
9. The profile privacy setting is worded ambiguosly. The toggle reads "Publuc profile - others can see your public and shared lectures." This suggests that a lecture shared privately with one individual might still become visible to everyone by way of the profile page, which would make private sharing unsafe. A setting that configures privacy should be explained unambiously with no room for self interpretation.
10. Live capture left in a background tab records until the allowance is gone. After starting a session and switching to a different browser tab, trancription continued with no prompt, countdown, or timeout until the limit was hit.
11. Search returns results unrelated to the query. Searching for a lecture by its exact title, or by words taken directly from its slides mostly return lectures with no relationship to the query. This is a defect in shipped functionality rather than a missing feature.
12. The home page looks too empty and offers no guidance to new users. A new account sees a welcome message, a "+" sign and a "New Lecture" button that to do the same thing, and otherwise empty space. Nothing explains that a lecture can be given a prior context, or what will happen when microphone is turned on.

##Gaps

13. Discover cannot be filtered by course, subject, or instructor. Our own SE lectures for example, sit mixed with unrelated presentations and can be reached only by scrolling or searching (when search engine gets fixed).

14. The lecture transcript cannot be read or taken out. The system keeps what was said. The system stores what was said (SPEC): a full transcript for presentation and source speech. Exporting the deck gives you the slides, but not the speech.

## Prior Art & Originality

We checked Future Work (§18) abd Open Questions (§19) in the Software Design Document and the delivery roadmap including its risks and cut line. Two things we considered turned out to be taken: the MCP interface for outside AI assistants, which is listed as future work, and is already live in the app, allowing to be used as a connector, and pulling quiz answers back into the app. Everything that we actually propose is new. We are also not claiming bug fixes as our proposals: the missing account-type question and unreliable search bugs in the existing features, so we filled them as issues instead of proposing them as new work.




## Stakeholders

See instructions. Delete this line and replace with the name(s) of the stakeholder(s) you interviewed and lists showing their goals/needs, and problems/frustrations. Note which type of user each stakeholder represents. You may use pseudonyms or partial names to maintain their privacy, but you must privately share their full names and contact information as part of your submission of this exercise

## Product Vision Statement

See instructions. Delete this line and place your Product Vision Statement here — one sentence describing the improvements and new features your team is proposing for The Slide Machine.

## User Requirements

See instructions. Delete this line and place a list of your User Stories here, grouped by type of user. These should describe functionality that is new or changed, not functionality the app already has.

## Activity Diagrams

See instructions. Delete this line and place images of your UML Activity diagrams here, each with the text of the user story it illustrates.

## Wireframes

See instructions. Delete this line and place your wireframe diagrams here, covering every new screen and every existing screen your proposal changes, for every type of user.

## Clickable Prototype

See instructions. Delete this line and place a publicly-accessible link to your clickable prototype here.

## Stakeholder Demo

See instructions. Delete this line and place a link to the deck The Slide Machine generated during your presentation here, after you have presented.

## Exit Ticket

See instructions. Delete this line and place a link to the exit-ticket quiz you generated from your demo deck and distributed to the class, along with a short note on what — if anything — you had to correct in the generated questions before publishing.
