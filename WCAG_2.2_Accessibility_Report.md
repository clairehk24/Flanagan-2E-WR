# WCAG 2.2 Accessibility Evaluation Report

**Website:** Acute and Emergency Care in Sports Medicine, Second Edition Web Resource  
**Evaluation date:** October 8, 2026  
**Evaluation standard:** [Web Content Accessibility Guidelines WCAG 2.2](https://www.w3.org/TR/WCAG22/), Level A and Level AA  
**Primary file evaluated:** `index.html`

## Executive summary

The HTML interface has no known WCAG 2.2 Level A or Level AA failures within the criteria and interactions tested after remediation. Automated testing reported zero violations in the Home, Dislocation Reduction Videos, and Quick References views. Keyboard behavior, responsive reflow, focus management, status announcements, accessible names, color contrast, and the embedded video-player controls were also tested manually or programmatically.

The complete website package should not currently be represented as fully conforming to WCAG 2.2 Level AA if the two locally hosted PDF downloads are included in the conformance scope. Both PDFs are untagged, and the Sample AMA Form has no interactive form fields. The PDFs were inspected but were not edited.

## Scope

### Included

- Home view
- Dislocation Reduction Videos view
- Quick References view
- Hash-based navigation between views
- Keyboard navigation and focus behavior
- Abbreviation search and dynamic results
- Human Kinetics logo alternative text
- Embedded Brightcove video-player controls
- Caption metadata and caption content for all nine linked videos
- Responsive behavior at 320 CSS pixels
- The two locally hosted PDF downloads, inspected for document accessibility metadata

### Excluded

- Accessibility of externally hosted websites and documents linked from Quick References
- Screen-reader testing with NVDA, JAWS, VoiceOver, or TalkBack
- Mobile-device assistive-technology testing
- Legal compliance determinations under the ADA, Section 508, or jurisdiction-specific requirements

## Evaluation methods

- Source review of HTML, CSS, and JavaScript
- Axe-core 4.14 automated testing against WCAG 2 A, AA, 2.1 A, AA, and 2.2 AA rules
- Headless Microsoft Edge rendering at desktop and 320 CSS-pixel viewport widths
- Keyboard tab-order, skip-link, view-navigation, video open and close, and focus-restoration tests
- Browser accessibility-tree inspection
- Programmatic color-contrast calculations
- Text-spacing resilience testing
- Brightcove playback metadata and caption-file review
- PDF metadata inspection and visual rendering

Automated testing cannot establish complete WCAG conformance by itself. The findings below combine automated results with targeted manual and programmatic checks.

## Results by success criterion

| WCAG criterion | Level | Status | Evidence |
|---|---:|---|---|
| 1.1.1 Non-text Content | A | Pass | The Human Kinetics logo has an appropriate `alt` value. Decorative arrows and play symbols are hidden from assistive technology. |
| 1.2.2 Captions Prerecorded | A | Pass | All nine Brightcove videos expose substantive English caption files. The shared player provides a keyboard-accessible captions control. |
| 1.2.5 Audio Description Prerecorded | AA | Manual review recommended | Caption text includes detailed narration of positioning, hand placement, traction, and movement. A human review should confirm that the spoken narration communicates all essential visual information throughout every video. |
| 1.3.1 Info and Relationships | A | Pass for HTML; fail for PDFs | HTML headings, landmarks, labels, table headers, and relationships are programmatically available. Both local PDFs are untagged and therefore lack reliable structural semantics. |
| 1.3.2 Meaningful Sequence | A | Pass for HTML | DOM order, visible reading order, and keyboard order are logical in all three views. PDF reading order is not reliably defined because the files are untagged. |
| 1.4.3 Contrast Minimum | AA | Pass | Small resource numbers now have a 5.75:1 contrast ratio, exceeding the required 4.5:1. No remaining automated text-contrast violations were found. |
| 1.4.10 Reflow | AA | Pass | All three views render at 320 CSS pixels without page-level horizontal scrolling or loss of content. |
| 1.4.11 Non-text Contrast | AA | Pass | Focus indicators inside dark video areas now use gold at 11.81:1 against the dark background. Other controls and focus indicators meet the tested contrast requirements. |
| 1.4.12 Text Spacing | AA | Pass | Required text-spacing overrides produced no page-level overflow or loss of textual content. |
| 2.1.1 Keyboard | A | Pass | All locally controlled links, search controls, video choices, close controls, and embedded-player controls are keyboard operable. |
| 2.1.2 No Keyboard Trap | A | Pass | No keyboard trap was found in the site shell or tested Brightcove player. |
| 2.4.1 Bypass Blocks | A | Pass | The skip link works in all views. Interior skip links remain in their current view and place the next tab stop at the first main control. |
| 2.4.2 Page Titled | A | Pass | The document title changes appropriately for Home, Videos, and Quick References. |
| 2.4.3 Focus Order | A | Pass | Tab order follows the visible content order. Client-side view changes now move focus to the destination H1. Closing a video restores focus to the triggering video link. |
| 2.4.6 Headings and Labels | AA | Pass | Headings and control labels describe their topics and purposes. Heading levels do not skip within the visible view. |
| 2.4.7 Focus Visible | AA | Pass | Keyboard focus is visibly indicated. Dark-panel focus styling was strengthened during remediation. |
| 2.4.11 Focus Not Obscured Minimum | AA | Pass in tested interactions | Focused controls and destination headings remained visible during the tested navigation flows. |
| 2.5.3 Label in Name | A | Pass | Visible control text is included in accessible names. |
| 3.2.2 On Input | A | Pass | Typing in the abbreviation search filters results without an unexpected change of context. |
| 4.1.2 Name Role Value | A | Pass | Controls expose names and roles. Medical overbar symbols now appear in the accessibility tree as named images, such as “p with overbar.” |
| 4.1.3 Status Messages | AA | Pass | “No matching abbreviations found” is exposed as a polite status message without moving keyboard focus. |

## Automated and functional test summary

| Test | Result |
|---|---|
| Axe-core violations on Home | 0 |
| Axe-core violations on Videos | 0 |
| Axe-core violations on Quick References | 0 |
| Page-level overflow at 320 CSS pixels | None in all views |
| Visible main landmarks | One per active view |
| Duplicate IDs | None found |
| Unlabeled visible controls | None found |
| Images without `alt` attributes | None found |
| Broken ARIA ID references | None found |
| Browser console errors during local tests | None |
| Video caption tracks | Present for all nine videos |

Axe-core identified several gradient or inherited-background combinations for manual contrast review. The confirmed low-contrast resource numbers were corrected. No additional contrast failure was found during the targeted review.

## PDF findings

### Common Medical Abbreviations Used in Prehospital Care Reports

- Tagged PDF: No
- Document title: Present
- Language and structural reading order: Not reliably exposed through PDF tags
- Table relationships: Not programmatically identified as table structure
- Accessibility status: Does not meet accessible-PDF expectations in its current form

### Sample AMA Form

- Tagged PDF: No
- Document title: Present
- Interactive form fields: None
- Labels and field relationships: Not programmatically exposed
- Accessibility status: Does not meet accessible-PDF or accessible-form expectations in its current form

The PDFs were not modified. Their SHA-256 hashes at the completion of testing were:

- `common-medical-abbreviations.pdf`: `572265E5630C5857147991A374A54F596C472612831A37BDEBBC18C78054A57B`
- `sample-ama-form.pdf`: `CF2AED70FE86BAD7818480D55F4CD951ED68B5C11C74159C17774886607C2C4D`

## Conformance conclusion

The HTML application has no known failures among the WCAG 2.2 Level A and Level AA requirements evaluated in this audit. This result should be described as a tested accessibility status, not as an unconditional conformance certification, until representative assistive-technology testing is completed.

The complete resource package does not currently meet WCAG 2.2 Level AA when the locally hosted PDFs are included. A full-site conformance claim should not be made unless the PDFs are remediated, replaced with accessible equivalents, or explicitly excluded from a narrowly defined conformance scope.

## Recommended next steps

1. Conduct a short manual screen-reader test with NVDA and Edge or Chrome across all three views.
2. Review each video with audio alone to confirm that narration communicates every essential visual action.
3. Preserve the current keyboard, focus, status-message, and contrast tests as regression checks for future updates.
4. If full-package conformance is required later, remediate the two local PDFs or provide equivalent accessible HTML resources.
