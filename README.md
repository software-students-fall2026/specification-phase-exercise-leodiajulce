# Specification Phase Exercise

A little exercise to get started with the specification phase of the software development lifecycle. In this exercise, your team specifies a set of improvements and new features for [The Slide Machine](https://theslidemachine.com) - see the [instructions](instructions.md) for detail, and the [background](background.md) for an introduction to the software product you are tasked with extending.

## Team members

- Carina-Ana-Maria Ilie, [GitHub](https://github.com/carinutza)
- Leonid (Leo) Gurevich, [GitHub](https://github.com/Leonid2004)
- Abubakar Diallo, [GitHub](https://github.com/Dialloni)
- Julian Leitersdorf, [GitHub](https://github.com/Jrleitersdorf)

## Review of the Current Application

### Strengths

1. Slide makers can control the freedom of AI. During the slide generation from speech, the instructor can set how much "freedom" the model is given rather than just accepting a single fixed behaviour. This allows the instructor to create a better presentation by deciding whether the slides need strict adherence to prepared material or if it could benefit from looser interpretetion. 
2. System health and plan usage are visible without being intrusive and disruptive. The "API ok" and "Free plan ok" status bar shows two different pieces of state, whether AI services are reachable, and whether the account is still within plan. The information is displayed in a simply-looking single line that doesn't compete for attention with the rest of the app.
3. Generated slides are visually consistent with each other. Every slide in the deck follows the same design template, so a presentation created one slide at a time from an unscripted speech still holds together as one piece work.
4. A lecture can be given context before it starts. A project can be "seeded" ahead of time with some prepared material, like outline, key terms, objectives, style, etc. So the system starts the lecture with some context behind, therefore being able to generate more accurate and relevant content.

### Weaknesses

5. The account-type prompt never appears. AUTH-6 specifies a one time prompt shown after the registration, asking whether the account belongs to a student, an educator, or another kind of user. Delievery Roadmap shows AUTH-6 as shipped. A newly created account was never shown this prompt at any point.
6. Accounts that never answer question (from finding 5) keep public defaults, so students are exposed to public by default. AUTH-6 intends public defaults only for educators, however due to the absence of the question (from finding 5) students keep public by default as well, therefore publishing their work without ever having made this choice.
7. Discover is cluttered with what appear to be accidental test lectures and other material with no value to readers. A large portion of presentations in discover section are named "Untitled Lecture" and most of them sit in "Default Project", the untitled project the app seem to create for the user's first lecture. The pattern suggests there are first run experimements that authors likely did not intend to publish. Most of them are useless to readers and genuinly interesting and useful courses might be lost among them.
8. A lecture's visibility is not shown anywhere on the lecture itself. The only plce visibility appears at is inside the lecture's settings, which read "Public (visible to eveyrone)." Additionally to that, the owner does not see their own public lecture in discover so there is no way to confirm how others see the presentation.
9. The profile privacy setting is worded ambiguosly. The toggle reads "Publuc profile - others can see your public and shared lectures." This suggests that a lecture shared privately with one individual might still become visible to everyone by way of the profile page, which would make private sharing unsafe. A setting that configures privacy should be explained unambiously with no room for self interpretation.
10. Live capture left in a background tab records until the allowance is gone. After starting a session and switching to a different browser tab, trancription continued with no prompt, countdown, or timeout until the limit was hit.
11. Search returns results unrelated to the query. Searching for a lecture by its exact title, or by words taken directly from its slides mostly return lectures with no relationship to the query. This is a defect in shipped functionality rather than a missing feature.
12. The home page looks too empty and offers no guidance to new users. A new account sees a welcome message, a "+" sign and a "New Lecture" button that to do the same thing, and otherwise empty space. Nothing explains that a lecture can be given a prior context, or what will happen when microphone is turned on.

### Gaps

13. Discover cannot be filtered by course, subject, or instructor. Our own SE lectures for example, sit mixed with unrelated presentations and can be reached only by scrolling or searching (when search engine gets fixed).

14. The lecture transcript cannot be read or taken out. The system keeps what was said. The system stores what was said (SPEC): a full transcript for presentation and source speech. Exporting the deck gives you the slides, but not the speech.

## Prior Art & Originality

We checked Future Work (§18) abd Open Questions (§19) in the Software Design Document and the delivery roadmap including its risks and cut line. Two things we considered turned out to be taken: the MCP interface for outside AI assistants, which is listed as future work, and is already live in the app, allowing to be used as a connector, and pulling quiz answers back into the app. Everything that we actually propose is new. We are also not claiming bug fixes as our proposals: the missing account-type question and unreliable search bugs in the existing features, so we filled them as issues instead of proposing them as new work.


## Stakeholders

For transcripts of interviews, checkout [this folder](Interviews/)

#### Stakeholder: Prof A.M. (instructor)

*Goals & Needs*

- <u>Integrate existing lecture material into presentations:</u> Prof. A.M. wants to be able to modify the AI-generated slides using content from the uploaded PDFs, notes, formulas, figures, and other course materials.

- <u>Control what information the AI prioritizes:</u> He wants a way to indicate which parts of his source material are important so that key information, such as formulas and figures, is more likely to appear on generated slides.

- <u>Use existing visuals during slide generation:</u> He would also like to upload a separate library of images and figures that both him and The Slide Machine can draw from while generating slides. Ideally, he would like to be able to click on the AI-suggested image and easily switch it out for another pre-uploaded image.

- <u>Use AI-generated slides alongside his normal teaching workflow:</u> He wants The Slide Machine to complement the material he already uses while teaching. Preferably, he would like to be able to see the notes he uploaded to the side of the slides so he can keep on track.

*Problems and Frustrations*

- Uploaded reference material is not visible during the presentation.

- Visual generation of charts, formulas and photos is inconsistent with what he would like to reference on the slide.

- There is limited control over what the AI considers important.

- Instructors cannot provide a dedicated image library.

- Automatically selected images are difficult to replace with instructor-provided alternatives.

*Observations from Using The Slide Machine*

While testing the live application, Prof. A.M. initially expected his uploaded PDF/reference slides to appear within the presentation interface. When he first noticed that was not the case, he reported that slide generation felt a little weird and not natural.

Overall, he responded positively to the AI-generated slides. He acknowledges that the slide genration significantly lowers the amount of time he would need to spend creating the slides.

To improve The Slide Machine, he reported that his preferred workflow would allow him to provide different types of source material separately: a PDF or set of notes containing lecture content and a library of approved images/figures. The Slide Machine could then select from those sources while he lectures, while still allowing him to replace or edit the generated content. He considers these followed by the ability to view the uploaded notes on the side of the slides central to transform The Slides Machine into a tool he could incorporate into his day-to-day.

#### Stakeholder: Prof. B.C.B. (instructor)

*Goals & Needs*

- <u>Turn spoken explanation into slide-ready text:</u> Prof. B.C.B. writes far more than a slide can hold and currently cuts it down by hand, one slide at a time. She wants the app to do that condensing for her, and more importantly she says that this single capability is what would make her switch away from PowerPoint.

- <u>Keep the formatting control she already has:</u> She wants to be able to change background colors, insert images, and style text directly, just like she does in PowerPoint, rather than accepting the generated design as final.

- <u>Get the images she asked for:</u> She wants the images the app sources to match her spoken request closely enough to use, and an easy way to replace one when it does not.

- <u>Work in an interface that reads as a presentation tool:</u> After PowerPoint, she wants the main controls along the top and a toolbar that is visually distinct from the browser around it, so that the app's own controls are not confused with her browser's.

- <u>Fit the app into an established workflow:</u> Her current process runs from Word to PowerPoint to a PDF, with YouTube links standing in for embedded video. She wants The Slide Machine to fit into that sequence rather than require her to abandon it.

*Problems and Frustrations*

- The main menu sits along the side rather than the top, which is disorienting coming from PowerPoint which is the tool she is most used to.

- The export and settings icons resemble browser and Gmail controls, so it is not obvious which controls belong to the app.

- She could not find how to change the background color, add an image, or style text.

- An image requested by voice - "a Native American artist engaging with an AI tool to create digital artwork" - returned an unrelated picture, and she had to search for a usable one by hand.

*Observations from Using The Slide Machine*

Prof. B.C.B. used the live application in person on 23 September 2026, doing a presentation on the topic of Native arts and AI. She gave the app 6.5 out of 10, noting that her limited experience with AI may have lowered that score.

Most of her concerns and comments were regarding the text length. Because writing too much and then cutting it back is the most laborious part of her current process. She treated the ability of app to optimize this process as the base for judgement, and was uncertain what it was actually doing with her speech. She said explicitly that she would move off PowerPoint if the app did this part well.

The interface itself was the second most importnat theme. The side menu, the browser-like toolbar icons, and the absence of any formatting controls she could find meant that several things she knows how to do in PowerPoint she could not do here. Her difficulty was not with the generation of slides but with recognizing the tools around them.


#### Stakeholder: Dr. K.S. (instructor / postdoctoral researcher)

*Goals & Needs*

- <u>Reliable generation of slides from speech:</u> Dr. K.S. wants the core function which is converting speech to slides to work consistently before anything else is added to the product. He is explicit that reliability comes first and new features second.

- <u>Direct control over where text sits on a slide:</u> He wants to move, resize, and center text boxes the way he can do it in PowerPoint, rather than accepting the position the app chose.

- <u>Decide who can see his work:</u> He wants slides to be private by default, with an explicit switch or share button to make one public, so that nothing of his is visible to others until he chooses so.

- <u>Recover work deleted by mistake:</u> He wants deleted slides held in a trash bin for around thirty days rather than removed immediately, so that a misclick or a genuine mistake is not permanent.

- <u>Support for the languages his colleagues and students actually use:</u> He wants coverage well beyond the five languages currently offered. He named English, Chinese, Spanish, French, Russian, Hindi, Arabic, Portuguese, and Bengali, pointing out that NYU operates campuses worldwide, including Ghana and Abu Dhabi.

- <u>Find things and get help inside the app:</u> He wants a search function and a help menu, mentioning PowerPoint's search and built in assistance as the model.

*Problems and Frustrations*

- Speech-to-slide generation stopped partway through, ignored portions of what he said, and behaved differently from one topic to the next. He observed it working during a professor's class but failing repeatedly for him, and believes the cause is an API or connection fault rather than his own network.

- Text is pinned to the left of the slide and cannot be moved or centered.

- The export control appears in two separate places, where one would be clearer.

- Other users can see his slides without his permission, and he found no sharing settings to prevent it.

- On the homepage, "About Us" is buried at the bottom and the layout does not use the full width of the screen, so the sections that matter are not where he looks first.

- Deletion is permanent, so work can be lost by accident with no way back.

- Only five languages are supported.

- There is no search and no help menu.

- Handwritten formulas cannot be read by the app; the pen and highlighter tools are a partial workaround at best.

- The mobile version carries the same problems as the desktop one, and the app is usable mainly on desktop.

*Observations from Using The Slide Machine*

Dr. K.S. tried the application on desktop on 26 September 2026. His session was dominated by generation failures: slides stopped appearing mid-lecture and parts of his speech produced nothing at all, with results changing by topic in a way he could not account for. Having seen the same feature work in a classroom, he attributed the difference to the application's connection to its AI services rather than to his own setup, and said he would want that resolved before any new capability was added.

The privacy issue was the one he raised unprompted and returned to. Finding that his slides were visible to other users without his permission to do so, and finding no setting to change it, he described the behavior he expected instead: private by default, with a deliberate action required to publish.

His remaining comments were those of someone comparing the application against a tool he already knows well. Fixed text position, a duplicated export control, a homepage that does not surface its own contents, no search, no help, and no way to undo a deletion were each described in terms of what PowerPoint does instead.

#### Stakeholder: Alex H. (student)

*Goals & Needs*

- <u>Join a class and see all of its lectures in one place:</u> Alex's largest request. He wants to join a class from his homepage and find every deck his professor has given in it, rather than browsing for that professor's folder every single time. If several of his professors used the application, he would join each class and study all their material from a single place.

- <u>Keep a local copy of a deck:</u> He wants to download decks as PDFs and keep them on his own machine, primarily so he can upload them to ChatGPT, the assistant he studies with.

- <u>Get the full lecture transcript:</u> He wants the transcript of an entire lecture as a student, so that he can use the assistant that is most convinent for him and that he studies with to work with what was actually said in the room. He described wanting a tutor that stays anchored to the lecture rather than going beyond it.

- <u>Study from slides that vary:</u> He wants slides whose layout reflects what is being said, rather than the same title-and-bullets shape repeating down the deck, because a uniform deck is dull to revise from.

- <u>Share a deck that he or a classmate can open:</u> He expects the share control to work when he uses it.


*Problems and Frustrations*

- The share button does not work. A second student stakeholder reported the same failure independently.

- Slide layouts are repetitive - almost always a title followed by bullet points - which makes a deck monotonous to study from.

- Layouts have to be changed one slide at a time by hand. Speaking from the lecturer's side, he thought the application should be able to infer a suitable layout from what is being said.

- There is no way to download a deck as a PDF and keep it locally.

- Finding a particular professor's material means hunting for their folder each time, since nothing organizes decks by class. He noted that organizing by project is possible today but it is not easy nor obvious and thought class-based organization would help professors as much as students.

- Students cannot obtain the lecture transcript at all.


*Observations from Using The Slide Machine*

Alex used the live application on 24 September 2026. As a student he found the interface straightforward to navigate, and he liked playing a deck aloud, describing it as a second pass through the lecture.

What he returned to was organization. His account of studying from the application was one of searching for material rather than reading it, and the fix he described was unprompted and clear: joining a class, as he would in any course tool (like Brightspace), and finding that class's lectures gathered together (possibly sorted by date).

He also wanted a local PDF and he wanted the transcript, in each case so that he could take the lecture into the assistant he already studies with and study on his own. He was not asking the application to tutor him, but was asking it to hand over the material so that something else could.

#### Stakeholder: Ilyas M. (student; also presents professionally)

*Goals & Needs*

- <u>Export a deck and keep it:</u> Ilyas wants to export decks as PDF or Google Slides, both to review them in his own way and to feed them into the AI tools he already uses. He described his study method as putting material into an assistant, getting a map of the essential points, and then breaking those down.

- <u>See the notes alongside the slides:</u> He asked for a notes view presented next to the deck rather than only the slides, so he can pick out the key points without reading through everything. He was explicit that he wants both views, not one instead of the other.

- <u>Slides that show rather than transcribe:</u> He wants slides to show visuals that match what is being said, not to write down every word. When he takes notes in a lecture he writes about a fifth of what he hears, only the parts that are not already on the slide. A deck that holds everything gives him nothing to add.

- <u>Navigate a long deck:</u> He wants sections and slide numbers. The deck he was shown ran to 109 slides as one continuous sequence, and he could find no way to tell where he was in it or where one topic ended and the next began.

- <u>Emphasis that carries meaning:</u> He wants the application to mark or highlight the important parts of a slide as it generates. Additionally, he wants manual control over bold, italic, color, and size, so that a dense slide still signals which parts matter.

*Problems and Frustrations*

- The share button does not work. He raised this unprompted while trying to save a deck, and a second student stakeholder reported the same failure independently.

- Google Slides export failed with an error when attempted during the session. He noted that even when such exports do work, formatting and typography often do not survive the transfer anyway.

- Slides are too text-heavy. His summary was that if the slide holds everything that was said, "I might as well just get notes."

- A 109-slide deck has no slide numbers and no sections, making it effectively unnavigable.

- There is no color coding and no manual text styling, so nothing on a crowded slide stands out.

- Generated images cannot be refined by further instruction. Asking for a photosynthesis diagram produced a reasonable result, but a follow-up request for more cellular detail was not understood, with the only recourse was to pick a different image from a list.

- Mathematical notation renders poorly.

- The existence of plans and usage limits was not apparent until it was pointed out in account settings.

*Observations from Using The Slide Machine*

Ilyas was interviewed over Zoom with a full recording. He studies film at Pratt and spent a year at a creative design agency where he presented every few weeks, so he came to the application as both a student and a practiced presenter.

He first asked why the app generates slides live instead of building them from a transcript after the lecture. He dropped the objection once he understood that nothing has to be uploaded beforehand, so the first class to hear a lecture gets slides just like every later one. It is still worth noting that a capable user did not see the point of the product until someone clearly explained it to him.

Most of his commentary concerned the deck as an object to study from rather than the act of generating it. Text density, missing sections and slide numbers, and the inability to export all lead in the same way - he wanted the lecture in a form he could navigate, and repeatedly described taking material out of the application and into something else.

On positioning, he was clear and unprompted. He judged the application strongest for professors, and for students studying from a recorded lecture, and weaker for a prepared work presentation - because a presenter with a fixed agenda relies on the deck to remind them what to cover, and a deck generated from speech cannot do that. He currently uses Granola to turn work meetings into summary emails and sees that as a different need. He also responded enthusiastically to the idea of a lecturer view where prepared notes are ticked off as each point is covered.

## Product Vision Statement

See instructions. Delete this line and place your Product Vision Statement here — one sentence describing the improvements and new features your team is proposing for The Slide Machine.

## User Requirements


#### Instructors


- As an *instructor*, I want *every new lecture to be defaulted to private* so that *unfinished or test lectures are not accidentally visible to students or in Discover*.


- As an *instructor*, I want *AI live transcription to automatically pause when the lecture tab is inactive or no speech is detected*, so that I *do not accidentally consume my plan allowance when I am no longer presenting*.


- As an *instructor*, I want to *see my notes in on the side as I start presenting* so that I can *reference my them and know that I am on track with the key points I want to make*.


- As an *instructor*, I want *to be able to edit the color, font, and size of the text on the slides* so that I can *make sure the presentation stylistically aligns with my view*.


- As an *instructor*, I want *to be able to invite
students to my whiteboard*, so that I *can coordinate in-class interactive activities for my online classes*.

- As an *instructor*, I want *to see under every peresentation I create weather or not it is private, link-only, and on Discover* so that I can *quickly tell who can see my work*. 

- As an *instructor*, I want *to have a separate folder for image library when uploading my initial documents for the slides* so that *I can choose exactly which photo goes on which slide.*

- As an *instructur*, I want *to have the ability to insert graphs to my slides after they are genrated* so that *I can make sure my examples are accompanied by the proper visual representation.*

- As an *instructor*, I want to *have an easily accessible ribbon above the slide deck* so that *I can make changes fast and without having to go through multiple clicks.*

- As an *instructor*, I want *to be able to create a folder that can be access only by people who have the link* so that I can *ensure only my target audience sees my lectures*.


#### Students


- As a *student*, I want to *download a transcript of the presentation* so that *I can use it to generate my own notes to study*.


- As a *student*, I want to *download lecture notes in plain text or Markdown when the instructor permits it* so that I can *study offline or use the material with my preferred study tools*.


- As a *student*, I want to *search and filter lectures by course, subject, instructor, title, and slide content* so that I can *find relevant study material without scrolling through unrelated lectures.*

- As a *student* I want to *be able to pin folders* so that I *can access them easily from the home page*.

- As a *student*, I want to *bookmark individual slides within a lecture* so that I *can quickly return to important concepts when studying.*

- As a *student*, I want *to see which slide is currently being discussed in the downloaded transcript* so that I *can connect the instructor's explanation with the correct slide.*

- As a *student*, I want an *easily accessible downalod button* so that I can *export every lecture as a PDF.*

- As a *student*, I want to *see my recently viewed silides first in the search bar* so that I *can access them faster when trying to search for them.*

- As a *student*, I want the *presentation to remember which slide I was viewing last* sp that I can *continue studying where I left off.*

- As a *student*, I want to *be able to pin and see all of the folder that I have been invited to in one place on the home screen* so that I can *organize all my courses and view their materials easily.*

## Features

Check out [feature_list.md](feature_list.md) for a detailed description of all of the features we implimented, as well as a list of honorable mentions!

## Activity Diagrams

See instructions. Delete this line and place images of your UML Activity diagrams here, each with the text of the user story it illustrates.

## Wireframes

[Check out our wire frames in PDF format!](wireframes/)

[Link to view the wire frames in Figma!](https://www.figma.com/design/mlf8u95E7CA0X92tNmsISR/Leojuice?node-id=24-2615&t=vB9ZM69wefO0HPLa-1)

## Clickable Prototype

Link to our clickable prototye: [clickable prototype](https://www.figma.com/proto/mlf8u95E7CA0X92tNmsISR/Leojuice?node-id=16-794&p=f&t=XrNkxpCda7IyMjr6-1&scaling=scale-down&content-scaling=fixed&page-id=24%3A2615&starting-point-node-id=16%3A753&show-proto-sidebar=1)

## Stakeholder Demo

See instructions. Delete this line and place a link to the deck The Slide Machine generated during your presentation here, after you have presented.

## Exit Ticket

See instructions. Delete this line and place a link to the exit-ticket quiz you generated from your demo deck and distributed to the class, along with a short note on what — if anything — you had to correct in the generated questions before publishing.