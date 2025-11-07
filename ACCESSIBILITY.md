# Accessibility Audit Plan - WCAG 2.1 AA

This document outlines the accessibility audit process for Tobolkometrie to ensure WCAG 2.1 AA compliance before making any claims.

## Audit Scope

All public pages must be tested:
- index.html (Homepage)
- metodika.html (Methodology page)
- drzitele.html (Recipients database page)
- clanky.html (Articles page)
- admin/index.html (Admin interface)

## WCAG 2.1 AA Success Criteria

### 1. Perceivable

#### 1.1 Text Alternatives
- [ ] All images have meaningful alt text
- [ ] Decorative images use `alt=""` or `aria-hidden="true"`
- [ ] SVG icons have `aria-hidden="true"` for decorative use

#### 1.2 Time-based Media
- [ ] N/A - No audio or video content currently

#### 1.3 Adaptable
- [ ] Semantic HTML structure (headings, lists, landmarks)
- [ ] Logical heading hierarchy (h1 → h2 → h3)
- [ ] No information conveyed by color alone
- [ ] Responsive layouts work at 320px width

#### 1.4 Distinguishable
- [ ] **Color Contrast**: Minimum 4.5:1 for normal text, 3:1 for large text
  - Test NTK Red (#C41E3A) on white background
  - Test all text/background combinations
- [ ] Text resizing: Readable at 200% zoom
- [ ] No text as images (except logos)

### 2. Operable

#### 2.1 Keyboard Accessible
- [ ] All interactive elements accessible via keyboard
- [ ] Visible focus indicators
- [ ] No keyboard traps
- [ ] Logical tab order

#### 2.2 Enough Time
- [ ] N/A - No time limits on content

#### 2.3 Seizures
- [ ] No flashing content (>3 flashes per second)

#### 2.4 Navigable
- [ ] Skip to main content link (optional but recommended)
- [ ] Page titles are descriptive
- [ ] Link text is meaningful (avoid "click here")
- [ ] Multiple navigation methods available
- [ ] Focus order is logical
- [ ] Link purpose clear from context

#### 2.5 Input Modalities
- [ ] Touch targets at least 44x44px
- [ ] No path-based gestures required

### 3. Understandable

#### 3.1 Readable
- [ ] Page language declared (`<html lang="cs">`)
- [ ] Text readability appropriate for target audience

#### 3.2 Predictable
- [ ] Consistent navigation across pages
- [ ] No automatic context changes on focus
- [ ] No automatic context changes on input

#### 3.3 Input Assistance
- [ ] Form labels associated with inputs
- [ ] Error identification and suggestions
- [ ] Error prevention for critical actions

### 4. Robust

#### 4.1 Compatible
- [ ] Valid HTML (no parsing errors)
- [ ] ARIA used correctly where needed
- [ ] Name, role, value for all UI components

## Testing Tools

### Automated Testing

1. **axe DevTools** (Browser Extension)
   - Install for Chrome/Firefox
   - Run on each page
   - Document all issues found

2. **WAVE** (WebAIM)
   - https://wave.webaim.org/
   - Paste URL or use browser extension
   - Review contrast errors, structural issues

3. **Lighthouse** (Chrome DevTools)
   - Run accessibility audit
   - Aim for 100 score
   - Review specific recommendations

4. **HTML Validator**
   - https://validator.w3.org/
   - Validate all pages
   - Fix parsing errors

### Manual Testing

1. **Keyboard Navigation**
   - Disconnect mouse
   - Navigate using Tab, Shift+Tab, Enter, Space, Arrow keys
   - Verify all functionality accessible

2. **Screen Reader Testing**
   - **macOS**: VoiceOver (Cmd+F5)
   - **Windows**: NVDA (free) or JAWS
   - Navigate each page, verify content makes sense

3. **Zoom Testing**
   - Zoom to 200% (Cmd/Ctrl + +)
   - Verify no content cutoff
   - Check horizontal scrolling minimal

4. **Color Contrast**
   - Use contrast checker: https://webaim.org/resources/contrastchecker/
   - Test all color combinations:
     - Primary (#C41E3A) on white (#ffffff)
     - Foreground (#1a1a1a) on white
     - Muted text (#4a5568) on white
     - White text on primary

5. **Mobile Testing**
   - Test on real devices (iOS, Android)
   - Verify touch target sizes
   - Check responsive behavior

## Known Issues to Address

### Current Implementation Concerns

1. **Color Contrast** (Priority: High)
   - NTK Red (#C41E3A) contrast needs verification
   - Muted text color (#4a5568) may not meet 4.5:1 ratio

2. **Focus Indicators** (Priority: Medium)
   - Need to verify visible focus states on all interactive elements
   - May need to enhance default browser focus rings

3. **SVG Icons** (Priority: Low)
   - All decorative icons currently use `aria-hidden="true"` ✓
   - Verify no informative icons missing labels

4. **Form Labels** (Priority: High - when forms added)
   - Admin CMS forms need testing once Decap CMS loads
   - Future contact forms need proper labels

## Audit Process

### Phase 1: Automated Scan (Week 1)
1. Run axe DevTools on all pages
2. Run WAVE on all pages
3. Run Lighthouse audit
4. Validate HTML
5. Document all findings

### Phase 2: Manual Testing (Week 2)
1. Keyboard navigation test
2. Screen reader test (VoiceOver)
3. Zoom/resize test
4. Color contrast measurements
5. Mobile device testing

### Phase 3: Remediation (Week 3)
1. Fix critical issues (color contrast, keyboard access)
2. Fix important issues (focus indicators, ARIA)
3. Fix minor issues (semantic improvements)
4. Re-test all fixes

### Phase 4: Documentation (Week 4)
1. Create accessibility statement page
2. Document any known limitations
3. Provide alternative access methods if needed
4. Add accessibility page to site footer

## Accessibility Statement Template

Once audit is complete, create `/pristupnost.html` with:

```markdown
# Prohlášení o přístupnosti

Tobolkometrie se zavazuje zajistit přístupnost svého webu v souladu s WCAG 2.1 úrovně AA.

## Stav souladu
[Plně vyhovuje / Částečně vyhovuje / Nevyhovuje]

## Datum auditu
[Datum posledního testu]

## Nástroje použité pro testování
- axe DevTools
- WAVE
- Lighthouse
- VoiceOver
- Manuální testování klávesnice

## Známá omezení
[Dokumentovat případné nevyřešené problémy]

## Zpětná vazba
Pokud najdete nějaké překážky v přístupnosti, kontaktujte nás na:
[kontaktní email]
```

## Success Criteria

Only claim WCAG 2.1 AA compliance when:
- [ ] All automated tests pass
- [ ] All manual tests pass
- [ ] Zero critical accessibility issues remain
- [ ] Accessibility statement published
- [ ] Re-audit scheduled (annually)

## Resources

- [WCAG 2.1 Guidelines](https://www.w3.org/WAI/WCAG21/quickref/)
- [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/)
- [axe DevTools](https://www.deque.com/axe/devtools/)
- [WAVE Tool](https://wave.webaim.org/)
- [A11y Project Checklist](https://www.a11yproject.com/checklist/)

## Notes

This is a living document that should be updated as:
- New pages are added
- New features are implemented
- WCAG guidelines are updated
- Issues are discovered and resolved
