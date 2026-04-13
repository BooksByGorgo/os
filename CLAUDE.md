# project description

most of this content is meant to supplement the `Operating Systems in Three Easy Pieces` --- referred to as `OSTEP` --- book.

## chapters

- DO NOT MODIFY THE AUTHOR INTRO section
- each numbered element in `content` represents a chapter
- each chapter starts with a conversation between a student and professor with a very high level conversation to subtly
- after the conversation start a new page with an introduction to the topics covered, motivation for the topics highlighting things that are hard to do without knowledge of the topics, and a brief overview of the section
- each chapter ends with a brief highlight of key points
- each chapter has some exercises to test reader's comprehension of the topics covered. there should be a mix of the following types of questions:
    - though provoking questions to make them think a little deeper about what they have read
    - what does this do type questions, where they get a snippet of code and predict what it will do
    - calculation questions to quickly and objectively test comprehension, like `what is the sizeof ilist for int ilist[4] on a system where int is 32-bit?`
    - where is the bug type questions, where you show some code and ask what the problem is
    - propose a short test program they should write to test their knowledge
- an answer key should be generated as a separate document from the main chapter content, containing each exercise question and its answer

## format and style

- use pandoc markdown
- do not use emdash or endash, use --- or -- instead
- use correct grammar and capitalizations
- use tip callouts (`::: {.tip}` divs) to highlight idioms, best practices, or warn of bad practices
    - `Tip` for highlight idioms, best practices
    - `Trap` for common mistakes
    - `Wut` unexpected or counterintuitive rules
- callouts are rendered as full-width `tcolorbox` boxes via `callout.lua` --- do not use `wrapfigure`
- keep the tone professional but light
- preserve emojis and text emojis (e.g., `:'(`) in the text --- do not remove them
- refer to the reader as `you`
- do not wrap sentences in the markdown. every sentence gets its own line
- since we are supplementing `OSTEP` follow the conversational and practical style of that book
- when figures and diagrams are needed use `mermaid.js` to do them 

## diagrams
- when asked to create diagrams or visualizations, use mermaid.js syntax in .mmd files
- render to png using `mmdc` when a visual output is requested

## extra content

- the related repo `cpp` has books on C/C++
- the `OSTEP` book and chapter are found at https://pages.cs.wisc.edu/~remzi/OSTEP/

## implementing github issues

when committing a change based on an issue (or set of issues)

- chose the contributor that contributed the most to the text to be the author of the change
- list everyone else who contributed to the issues and text development as coauthors

## validating chapters

- fix any grammar or spelling errors
- check for awkward phrasing
- check any code examples for errors
- check that everything is explained accurately
- are there any missing concepts that should be covered?
- does the chapter have all the required elements
- does each chapter have exercises with a mix of:
    - thought provoking questions
    - what does this do type questions with code snippets
    - calculation questions
    - where is the bug type questions with code snippets
    - propose a short test program they should write

# making changes

- whenever you finish making changes automatically commit to git
- if there are changes that haven't been pushed, amend the commit to the latest local only commit
