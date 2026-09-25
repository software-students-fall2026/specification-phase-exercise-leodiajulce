# Feature List

## 1. Presenter Notes Sidebar

Lecturers bring their own speaker notes and see them while they talk, instead of facing a blank screen while slides generate.

- Upload or type notes as a bullet list when preparing a lecture, in the same popup of where the seed material goes but has its own textbox. The notes also serve as seed material, so slides are generated with them in mind.
- During the lecture, notes appear in a separate presenter view (like PowerPoint's), so they are never visible on the window or tab being shared. If the presenter shares their whole screen, the app warns that notes may be visible.
- The presenter can edit, reorder, or check off points by hand while speaking.
- If notes fail to load, the lecture continues and the sidebar offers a retry.
- No AI cost: notes are stored text.
- **Step up (pending professor): auto tick-off.** Points are crossed off automatically as the lecturer covers them. A free version matches the live transcript against the notes by keyword; a more accurate version uses the AI and adds cost to the presenter's plan.

## 2. Study Modes and Downloads

Every lecture can be read in two/(three) modes, in this order: **Slides**, (**Notes**), **Transcript**. The modes overlap on purpose; each holds the whole lecture, shaped differently, and the reader picks the one that suits them.

- **Slides:** the deck as it is today.
- **Transcript:** everything said in the lecture, timestamped and grouped by slide, including students' questions. No approval step; an LLM can tell speakers apart from context. Last in order, since it is least useful on its own.
- **Downloads:** slides as PDF, transcript as Markdown (.md), or both bundled. Markdown drops straight into a ChatGPT or Claude project folder, so a student's AI tutor stays up to date with exactly what the professor said, without searching the web or adding redundant information.
- The app sends nothing new to any model: it already transcribes all speech to generate slides, and downloading is the student's own action.
- Instructor setting "Students may download," on by default.
- If downloads are off or Notes are not ready yet, the tab or button says why instead of disappearing.
- Fixes the broken Share button along the way (reported as a bug, not claimed as a feature).
- **Step up (pending professor): Notes mode.** Two or three pages of structured notes combining the slides and the transcript, for quick review. Generated only when the owner publishes the deck, once, and reused for every student, so cost does not grow with class size. Billed to the owner's plan; the owner can turn it off or regenerate after editing.

## 3. Saved Projects and People

Instructors organize lectures into projects and share one link with their class. Anyone with the link, or anyone who finds a project on Discover, can save it to their homepage, like a Google Drive shortcut.

- Saved projects appear as folder on the homepage.
- Users can also save a person, such as an instructor, to see all of their public projects.
- No class list is created: the save lives only on the student's own account. The project stores no list of who saved it, and the instructor sees no names and no count. Access is unchanged; anyone with the link can open it.
- If a project is deleted or made private, the saved card shows "No longer available" and offers to remove it.
- Pending professor: confirm that per-student bookmarks do not count as a roster under FERPA.

## 4. Auto-Pause

Recording pauses on its own after long silence or when the lecture tab is left, so a forgotten microphone cannot burn through a month of credits (happened to Leo).

- An on-screen countdown starts first; if nothing happens, transcription pauses.
- Nothing already captured is lost. One click, or saying "resume," continues the session.
- Timeouts are adjustable or can be turned off per project, since some lecturers present from a second window. Whiteboard mode can use a longer timeout.
- If detection fails, the session behaves exactly as it does today.
- Saves money; needs no AI calls.

## 5. Text Formatting Toolbar

A formatting toolbar like Word or PowerPoint, so lecturers can make key points stand out instead of leaving every slide as plain title and bullets.

- Bold, italic, underline, font, font size, text color, and highlight on selected text.
- Undo and redo.
- If Refine or the AI regenerates a slide the lecturer already formatted, the manual formatting is kept, or the app warns before overwriting it.
- No AI cost.

## 6. Finish and Publish Flow (potenital)

When a lecture ends, a short guided flow takes the lecturer from raw slides to a published deck. Nothing becomes public until they press Publish.

1. **Review** the generated slides.
2. **Refine** with the existing AI tools (skippable).
3. **Format** with the toolbar from feature 5.
4. **Place** the lecture in a project.
5. **Publish** as Private, Link only, or On Discover. Publishing triggers Notes generation (feature 2).

Publishing rules it brings in:

- New lectures start as Link only: shareable right away, but not listed on Discover.
- Appearing on Discover is a separate Publish step and requires a real title, so "Untitled lecture" test runs never show up publicly.
- New setting in Account Settings, Privacy: "New lectures start as" Private or Link only, with clearer wording on the profile toggle.
- The auto-created "Default project" starts private.
- If the tab is closed mid-flow, the lecture stays Link only and the flow resumes next time. If publishing fails, the lecture stays less public, never more, and the lecturer is told why.

## Maybe

- **Publish preview and public name:** before publishing, see exactly what strangers will see and choose full name, initials, or a display name.
- **Visibility badges:** Private / Link only / On Discover shown on every lecture card and deck header.
- **Media sidebar:** browse uploaded images and place a specific one on a specific slide, instead of the AI deciding.
- **Discover filters:** filter Discover by course, subject, or instructor.
- **Better search:** rank exact title matches first and highlight where each result matched.
- **Sections and slide numbers:** split long decks into sections for easier navigation.
- **Live usage meter:** minutes used and remaining shown during recording.
- **Live Q&A marking:** mark a student question during the lecture so it becomes a question slide, not a stated fact.
- **Co-presenter mode:** mark several speakers as presenters so a co-lecturer is not treated as a student.
- **Collaborative whiteboard:** students draw and annotate on a whiteboard slide live; saved with the lecture.
