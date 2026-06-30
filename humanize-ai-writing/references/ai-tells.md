# AI writing tells — full catalog

Detection reference. Source: [Wikipedia: Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing).
A single tell is weak evidence; clusters are strong. Scan for all of these.

## 1. Language & word choice

**AI vocabulary (high-frequency words).** Cluster together; one usually means
more nearby.
- 2023–mid-2024: additionally, delve, intricate/intricacies, garner, pivotal,
  testament, underscore, tapestry, vibrant, meticulous.
- mid-2024–mid-2025: align with, enhance, emphasizing, fostering, highlighting,
  showcasing.
- Grok-leaning: causal, empirical, correlate, underscore, "X rather than Y."

**Avoidance of plain copulas.** Replacing "is/are" with serves as, marks,
features, represents, functions as, stands as, offers, refers to.

**Elegant variation.** Swapping in synonyms to avoid repeating a word
("the author… the writer… the wordsmith"). Reads forced.

**Promotional buzzwords.** vibrant, rich, nestled, boasts, showcasing,
cutting-edge, world-class, state-of-the-art, seamless, robust, holistic.

## 2. Sentence structure

**Negative parallelism.** "Not only X but also Y," "it's not X, it's Y,"
"X rather than Y," "more than just." A top tell.

**Rule of three.** Auto-grouping into three adjectives or phrases to fake depth
("identity in flux, constituted through iterative difference").

**Present-participle padding.** Trailing "-ing" clauses claiming significance
without evidence: "…, enhancing its role as a dynamic hub,"
"…, contributing to the socio-economic development of the region."

## 3. Fake significance & analysis

**Undue emphasis on legacy.** "stands as," "marks a pivotal moment,"
"symbolizing its ongoing," "leaves an indelible mark," "enduring testament."

**Superficial depth.** Vague statements about "broader implications,"
"philosophical questions," "what it means to…" with no substance.

**"Challenges" formula.** "Despite its [positives], [subject] faces challenges
typical of… but continues to thrive," followed by future speculation.

**Future/potential speculation.** "future investments could," "potential
expansions might," "has shaped emerging policy discussions" — unfounded.

## 4. Tone & voice

**Promotional / press-release.** "commitment to," "dedication to," "ensuring,"
"passionate about," "we're excited to," "revolutionary."

**Cultural-heritage over-emphasis.** Repeatedly reminding the reader of "rich
history," "spiritual significance," "cultural heritage" — even where irrelevant.

**"Active social media presence."** Idiosyncratic post-2024 note: "maintains a
strong digital presence, particularly on Instagram."

## 5. Hedging & attribution

**Weasel attribution.** "experts say," "studies show," "observers have noted,"
"researchers treat X as," "it is widely believed," "many argue" — no named
source.

**Exaggerated source quantity.** Presenting one or two sources as "widely held"
or "such as X and Y" implying a longer list.

## 6. Formatting & structure

- Title Case In Headings (should be sentence case).
- Excessive boldface for mechanical emphasis.
- Inline-header vertical lists: "**Standard Saws**: used for…".
- **Em dashes** — overuse is a flagged tell. Treat as: avoid; rewrite with comma,
  period, colon, or parentheses.
- Curly/smart quotes instead of straight quotes.
- Emoji used as bullets/formatting (•, 🔹).
- Markdown leaking where it shouldn't (*asterisks*, #hashtags in wikitext).
- Skipped heading levels; horizontal rules before headings.

## 6b. Formula sections
- "Despite its [positives], it faces challenges…" openings.
- "Future Outlook", "Challenges and Legacy", "Challenges and Future Directions"
  headings that end an article with vague positive speculation.

## 7. Markup / technical artifacts (copy-paste leftovers)

contentReference, oaicite, oai_citation, :::writing, turn0search0, "+1",
attached_file, grok_card, links to search queries, utm_source= in citation URLs,
invalid DOI/ISBN, citations with no page numbers, named refs never used.

## 8. Hollow conclusions

"In conclusion," "Overall," "Ultimately," end paragraphs that restate the whole
piece, section summaries that recap what was just said.

## 9. Historical / fading tells

"As an AI, I…," "I cannot…," didactic disclaimers, abrupt mid-sentence cut-offs,
end-of-section recaps. Rare in current models but still appear.

## 8. Hollow conclusions — also section summaries
Add "In summary" to the banned openers, and the "Despite its… → Future Outlook"
formula in §6b.

## Not reliable on their own (per Wikipedia)
These are weak evidence in isolation — don't treat them as proof, and when
*rewriting*, don't mangle meaning to purge a single instance:
- A lone "AI vocabulary" word. One "vibrant" is not a verdict.
- Generic promotional tone by itself — humans write marketing too.
- **AI-detector tools** — high error rates; they flag human text constantly.

## Composite signal
Confidence rises sharply when several cluster: AI vocabulary + superficial
analysis + promo tone + excess bold + Title Case + inline-header lists. Human
judgment alone is near chance; pattern-matching the clustered list is what works.
When generating, the rule is simpler: avoid producing these patterns at all.
