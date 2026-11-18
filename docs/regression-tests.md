# Editorial regression tests

Use the current [SKILL.md](../SKILL.md) in a fresh session for each case. Give the agent only the request and input. Check the final text and any editorial notes against the expected behavior. Wording can vary. Record the agent, model, skill commit, and failed checks so another reviewer can repeat the run.

The cases use made-up facts and isolated files. No live sites or detector scores are needed.

## 1. Missing details in a finished draft

**Request**

> Polish this public notice. The sign-up page is https://example.org/classes. I don't have the room number yet.

**Input**

> The class starts May 8 in room [room number]. Register at [link]. Please verify all details before publishing this.

**Expected behavior**

- Keep May 8 and fill the registration link from the request.
- Keep the unresolved room visible and call it out separately. Never guess the room number.
- Move the generic publication instruction out of the public copy.

## 2. The same blank in a reusable template

**Request**

> Copyedit this reusable class notice template. Keep its fields.

**Input**

> The class starts [date] in room [room number]. Register at [link].

**Expected behavior**

- Keep all three fields verbatim. A reusable template needs no missing-details note.

## 3. Markup in two destinations

**Request A**

> Copyedit this README section for GitHub.

**Request B**

> Copyedit the same section for a MediaWiki draft. Convert the heading and link to wikitext.

**Input**

```markdown
## Tickets

The desk sells tickets for £8. See the [opening hours](https://example.org/hours).
```

**Expected behavior**

- A retains valid Markdown.
- B uses `== Tickets ==` and `[https://example.org/hours opening hours]` in the wikitext. It keeps the £8 price and original destination.

## 4. A mismatched source and a source that belongs

**Request**

> Polish this reference article and check the two citations against these supplied records. The DOI record for citation 1 is “Water use in glasshouses”. The print handbook in citation 2 says on page 46 that spare batteries should be stored at 15–20 °C. These are the only source records available.

**Input**

> The bridge opened in 1974 [1]. The handbook recommends storing spare batteries at 15–20 °C [2].
>
> [1] *Mossbank Bridge: Construction and opening*, DOI 10.9999/bridge.1974.
>
> [2] *Maintenance Handbook*, p. 46.

**Expected behavior**

- Flag citation 1 as a mismatch based on the supplied records. Keep 1974 and the reference together and leave the correction for the author.
- Keep the supported temperature range, its attribution, and the page number. A print source needs no invented URL. Never guess a replacement DOI.

## 5. Evidence limits and attribution

**Request**

> Edit this short museum article for clarity without any new research.

**Input**

> The catalog records that Ortiz began teaching in 1974 [1]. Two reviewers called her early work austere. The pilot survey covered only 18 visitors, so its results may differ from those of a museum-wide survey. Despite these challenges, her work sparked a broader conversation about education and identity. She won the Hart Prize in 1981 [2].

**Expected behavior**

- Keep who taught and when, the catalog citation, the two reviewers' judgment, the pilot's scope and uncertainty, and the named award with its date and citation.
- Flag the vague claim about a broader conversation. Keep it with its original degree of certainty pending the author's decision. Never name a debate or add evidence from memory.

## 6. Deliberate voice and quotations

**Request**

> Copyedit this personal newsletter. Keep my voice.

**Input**

> Hi, Mae!
>
> I waited for ages — long enough to make friends with the dog. The clerk said “come back in April” and handed me the April–June timetable. Perhaps I’ll get the first bus next time.

**Expected behavior**

- Keep the greeting, aside, date range, exact quotation, and uncertainty. The curly punctuation and dash can stay. A clean passage can come back unchanged.
- Report editing observations without guessing who wrote it.

## 7. The short edit summary

**Request**

> Turn this into a short wiki edit summary. The reader already knows why we had to change the timetable.

**Input**

> In response to reviewer feedback, I carefully updated the article in line with the relevant guidelines while preserving the remaining schedules, improving clarity and accuracy. The Sunday bus now departs at 8:30.

**Expected behavior**

- State the changed time and day. Drop the generic claims about compliance and the description of unchanged schedules.

## 8. A prose-only file edit

Save the following as `notice.md` in a temporary directory.

~~~~markdown
---
published: false
---

# Notice

Here's the thing: the venue opens at 9.

## Booking

The fee is £8. Book on the [venue website](https://example.org/old-booking).

## Staff

The staff can run `open-desk --dry-run`.

```sh
open-desk --dry-run
```
~~~~

**Request**

> Humanize the prose in notice.md. The booking link is obsolete. Flag it in your summary. I don't have a replacement yet.

**Expected behavior**

- Read the entire file and report that all three headings were reviewed.
- Remove the staged opener and keep 9 and £8.
- Keep the YAML, link target, inline code, and fenced command byte for byte. Report the obsolete link separately.

## 9. Leaked citation markup

**Request**

> Copyedit this text for a printed exhibition label. I need to know if any citation needs attention.

**Input**

> The east wing opened in 1974. contentReference[oaicite:4]

**Expected behavior**

- Keep 1974. Put the raw token in an editorial note so the author can trace it, and flag the missing source. Do not invent a source or leave the token in the public-facing label.

## 10. A descriptive title in a lead

**Request**

> Copyedit this draft wiki article. Keep its title and the supplied citation.

**Input**

> Title: Schools on Bell Island
>
> Schools on Bell Island refers to the schools found on Bell Island. The council opened the first school in 1932 [1].

**Expected behavior**

- Keep the title. Start the prose with the council opening the first school in 1932 and keep citation [1] with the date.

## Package checks

```sh
python3 scripts/validate-package.py
npx skills add . --list
claude plugin validate .
```

Use `python` on Windows if that is how Python is installed. Package checks cover metadata and discovery. The editorial cases check the behavior of the loaded prompt.
