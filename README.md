# Humanizer Plus

Humanizer Plus edits formulaic prose while preserving what the author means and how they sound. It uses patterns to guide edits. Authorship questions need evidence beyond the text's style.

## Install

```sh
npx skills add frankischilling/humanizer-plus
```

Use `/humanizer` with a passage or a file path. For a closer voice match, include a sample of your writing. See the [installation guide](docs/installation.md) for Claude Code, Codex, Cursor, pi, and other agents.

## Example

**Before**

> Here's the thing: the workshop isn't just for beginners, it's also open to returning members. If you already have a kit, bring it. We have six spares.

**After**

> Beginners and returning members are welcome. Bring your kit if you have one. We have six spares.

## The 29 patterns

The [skill prompt](SKILL.md) has the editing rules and examples. See [editing by context](docs/editing-by-context.md) for cases where the same wording or formatting calls for a different edit.

### A. Staging instead of stating

| # | Pattern |
|---|---------|
| 1 | **Not X but Y** [§1](SKILL.md#1-not-x-but-y) |
| 2 | **One-line closers and dramatic fragments** [§2](SKILL.md#2-one-line-closers-and-dramatic-fragments) |
| 3 | **Sayings that sound deep** [§3](SKILL.md#3-sayings-that-sound-deep) |
| 4 | **Staged run-up before the point** [§4](SKILL.md#4-staged-run-up-before-the-point) |
| 5 | **Arguing with no one** [§5](SKILL.md#5-arguing-with-no-one) |

### B. Rhythm by rule

| # | Pattern |
|---|---------|
| 6 | **Forced triads** [§6](SKILL.md#6-forced-triads) |
| 7 | **Repeated sentence openings** [§7](SKILL.md#7-repeated-sentence-openings) |
| 8 | **Dashes as the universal connector** [§8](SKILL.md#8-dashes-as-the-universal-connector) |
| 9 | **Stacked qualifiers** [§9](SKILL.md#9-stacked-qualifiers) |
| 10 | **Hyphenated pairs everywhere** [§10](SKILL.md#10-hyphenated-pairs-everywhere) |
| 11 | **Passive voice and missing subjects** [§11](SKILL.md#11-passive-voice-and-missing-subjects) |

### C. Inflation and borrowed authority

| # | Pattern |
|---|---------|
| 12 | **Overused AI words** [§12](SKILL.md#12-overused-ai-words) |
| 13 | **Inflated significance** [§13](SKILL.md#13-inflated-significance) |
| 14 | **Vague connection or association** [§14](SKILL.md#14-vague-connection-or-association) |
| 15 | **Shallow -ing phrases** [§15](SKILL.md#15-shallow--ing-phrases) |
| 16 | **Sales language** [§16](SKILL.md#16-sales-language) |
| 17 | **Borrowed authority** [§17](SKILL.md#17-borrowed-authority) |
| 18 | **Avoiding is, are, and has** [§18](SKILL.md#18-avoiding-is-are-and-has) |

### D. Formatting by rule

| # | Pattern |
|---|---------|
| 19 | **Bold as decoration** [§19](SKILL.md#19-bold-as-decoration) |
| 20 | **Decorative headings** [§20](SKILL.md#20-decorative-headings) |
| 21 | **Curly quotation marks** [§21](SKILL.md#21-curly-quotation-marks) |

### E. Leftovers from the chat and the draft

| # | Pattern |
|---|---------|
| 22 | **Chatbot residue** [§22](SKILL.md#22-chatbot-residue) |
| 23 | **Knowledge-limit disclaimers and guesses** [§23](SKILL.md#23-knowledge-limit-disclaimers-and-guesses) |
| 24 | **A heading repeated in the first sentence** [§24](SKILL.md#24-a-heading-repeated-in-the-first-sentence) |
| 25 | **Writing about the document instead of its subject** [§25](SKILL.md#25-writing-about-the-document-instead-of-its-subject) |
| 26 | **Unfilled placeholders** [§26](SKILL.md#26-unfilled-placeholders) |
| 27 | **Markup that leaked into prose** [§27](SKILL.md#27-markup-that-leaked-into-prose) |
| 28 | **Citations that need checking** [§28](SKILL.md#28-citations-that-need-checking) |

### F. Writing for the wrong reader

| # | Pattern |
|---|---------|
| 29 | **Re-explaining what the reader knows** [§29](SKILL.md#29-re-explaining-what-the-reader-knows) |

## Sources and license

Forked from [blader/humanizer](https://github.com/blader/humanizer) by Siqi Chen under the [MIT License](LICENSE). The [Wikipedia audit and credits](docs/wikipedia-audit.md) document the guide revisions, coverage, and attribution. See the [changelog](CHANGELOG.md) for release notes.

Use the [editorial regression tests](docs/regression-tests.md) to check changes to the prompt.
