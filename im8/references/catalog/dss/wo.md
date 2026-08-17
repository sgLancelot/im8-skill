# WCAG : Operable (WO)

Source: https://info.standards.tech.gov.sg/control-catalog/dss/wo/
Page last updated: 5 March 2026

Content © Government Technology Agency of Singapore, snapshotted from the public portal for grounding; canonical source is the live portal.

## WO-1 — Keyboard equivalent

### Statement

Ensure any action done using a pointer device can also be done using a keyboard.

### Recommendations

Provide keyboard operation for all the functionality of the page unless the function requires path-dependent input such as handwriting.

Avoid requiring specific timings for individual keystrokes such as requirements to repeat or execute multiple keystrokes within a short period of time.

### Rationale

Ensures that there is no loss of functionality for users who rely on keyboards such as those with motor impairments.

## WO-2 — No Keyboard Trap

### Statement

Ensure that keyboard users can move keyboard focus away or out from a component or section of the digital service.

### Recommendations

Test forms, widgets, and custom elements with keyboard-only navigation to confirm end users can exit all components using standard keys (like Tab and Shift+Tab).

If the key functionality of the component restricts the focus to a subsection of the content, communicate clearly to users how to leave that state and "untrap" the focus.

### Rationale

A keyboard trap happens when keyboard focus is moved to a component or subsection of the digital service without a way of the end user navigating back out using a keyboard interface. End users who who rely on exclusive keyboard interface usage such as people with vision and physical disabilities get stuck and are unable to proceed to other parts of the service or complete a critical transaction.

## WO-3 — Character Key Shortcuts

### Statement

Provide a mechanism to disable or remap shortcuts that are activated using only one character key press.

### Recommendations

If character key shortcuts are used, provide end users with the ability to disable or remap them. Implement keyboard settings within the interface for customisation, ensuring shortcuts do not interfere with common keyboard interactions.

### Rationale

Reduces the risk of accidental activation of keyboard shortcuts for keyboard users and speech input users, whose dictation is interpreted as strings of letters.

## WO-4 — Adjustable Timings

### Statement

Allow time limits to be turned off, adjusted, or extended.

### Recommendations

Avoid time-dependent functions unless absolutely necessary. Ensure timers are non-disruptive and adjustable or extendable.

Not required when the time limit is:

a) Mandatory from a legal point of view

b) Required as part of a real-time event where extensions would invalidate the activity

c) Longer than 20 hours

### Rationale

Persons with disabilities may need more time to complete complex tasks such as filling out lengthy grant forms. Designing functions that are not time-dependent or allow for adjustable timings will help everyone, especially people with disabilities, succeed at completing these tasks.

## WO-5 — Pause, Stop, Hide

### Statement

Provide a function to pause, stop, hide or control the frequency of moving, blinking, scrolling or auto-updating content that occur in parallel with other content.

### Recommendations

Content changes refer to, but are not exclusive to, auto-updating information, animations containing essential information or similar components.

Allow users to pause, stop, or hide content that automatically moves, blinks, scrolls or auto-updates for more than 5 seconds.

### Rationale

Content that moves or auto-updates can be a barrier to anyone who has trouble reading stationary text quickly, tracking moving objects or noticing page changes easily. It can also cause problems for screen readers.

## WO-6 — Reduce Flash Triggers

### Statement

Avoid content that flashes more than three times per second or provide a warning and the option to skip such content.

### Recommendations

Provide a clearly displayed warning message such as "This video may potentially trigger seizures for people with photosensitive epilepsy. Viewer discretion is advised."

Excludes flashes contained in a small area, are low contrast or include a small amount of the colour red.

### Rationale

Flashing content can trigger seizures in end users with photosensitive epilepsy leading to serious health risks for these users.

## WO-7 — Bypass Repeating Content

### Statement

Provide a means of skipping repetitive blocks of content that appear across multiple pages.

### Recommendations

Implement visible and keyboard accessible link(s) for end users to skip repeated content blocks and/or group blocks of repeated material in a way that can be skipped through the use of ARIA landmarks or heading markup.

### Rationale

End users who navigate sequentially with keyboards or screen readers often encounter repeated content such as headers and navigation links across multiple pages. Providing a mechanism to bypass these repetitive sections enables users to access the main content more efficiently.

## WO-8 — Page Title And Purpose

### Statement

Provide a page title describing the purpose of every web page or distinct Single-Page Application view served from the same Uniform Resource Identifier (URI).

### Recommendations

Provide a clear and succinct page title that describes the purpose of the page. For example, "Budget 2024 Support Schemes Calculator" is a clear title stating the page contains a calculator for Support Schemes from Budget 2024.

### Rationale

Clear, descriptive titles provide quick context, enabling all end users (including users of assistive technologies) to quickly understand where they are without having to scan page content. They also facilitate efficient navigation in site maps and search results, allowing rapid identification of relevant information.

## WO-9 — Sequential Focus Order

### Statement

Ensure focusable components receive focus in an order that preserves meaning and operability when the navigation sequences affect meaning or operation.

### Recommendations

When a user triggers a focusable element like a modal dialog via an element (button or link), the keyboard focus should be set to within the modal and limited to the elements of modal until dismissed.

When the modal is dismissed, the keyboard focus should logically return to the original trigger element to minimise confusion for the user.

### Rationale

Allows keyboard users to navigate in a sequence that reflects the content's logical structure, preventing disorientation from unexpected tabbing focus. This approach accommodates various valid navigation patterns while preserving content coherence. Implementing this improves accessibility, often results in cleaner markup, and can enhance SEO, benefiting all users.

## WO-10 — Link Text And Purpose

### Statement

Ensure that link text identifies the purpose of the link and can be interpreted easily on its own.

### Recommendations

Avoid using vague link text such as "click here" or "read more".

### Rationale

Descriptive and meaningful link text helps users understand the content and purpose of each link without needing to read the surrounding text. This is especially important for screen reader users who often navigate web pages by jumping from one link to another. It also improves the SEO value of a page and helps all users find the information they need more efficiently.

## WO-11 — Multiple Ways

### Statement

Provide at least two ways to reach the same content.

### Recommendations

Focus on information architecture and implement multiple ways to reach content such as clear and logical navigation structures, search function and shortcuts.

### Rationale

Providing multiple ways to access content allows end users to locate content in ways that best meet their needs. Users may find one navigation path easier or more comprehensible than another, improving both the user experience of the service and the discoverability of content.

## WO-12 — Headings and Labels

### Statement

Provide descriptive headers and labels that identify the context of surrounding text and the component's purpose.

### Recommendations

Do not disable platform or user-agent default visual focus indicators. If default focus indicators are not available or do not meet other accessible guidelines like colour contrast, modify the background colour or border of the element with focus.

Ensure that 'floating' components like widgets and sticky headers do not cover elements receiving focus.

### Rationale

Allows end users to quickly identify which element or control has keyboard focus. This is especially important for users relying exclusively on keyboards to navigate.

## WO-13 — Focus Visible and Not Obscured

### Statement

Ensure components receiving focus have distinguishable indicators and are not obscured by other elements.

### Recommendations

Do not disable platform or user-agent default visual focus indicators. If default focus indicators are not available or do not meet other accessible guidelines like colour contrast, modify the background colour or border of the element with focus.

Ensure that 'floating' components like widgets and sticky headers do not cover elements receiving focus.

### Rationale

Allows end users to quickly identify which element or control has keyboard focus. This is especially important for users relying exclusively on keyboards to navigate.

## WO-14 — Simple Pointer Alternatives

### Statement

Provide single-point alternatives to multipoint or path-based interactions or gestures.

### Recommendations

If multipoint or path-based gestures such as sliders and drag-and-drop functions are used, provide alternative options to perform the same interaction through simple single-point alternatives.

### Rationale

Interactions that involve complicated gestures or precise movements such as dragging or pinching can be challenging or impossible for end users with mobility disabilities, elderly users, or those using adaptive input devices.

## WO-15 — Pointer Cancellation

### Statement

Provide a predictable and consistent way to cancel or undo pointer interactions.

### Recommendations

Implement clear and accessible methods to cancel critical actions such as an "undo" function. Confirmation dialogs can be used as a secondary confirmation for critical actions.

Unless absolutely necessary, only execute a function when the click or touch is released (up-event) instead of when the click or touch is made (down-event). This gives end users the opportunity to cancel the activation after by moving their pointer or finger away from the target before releasing.

### Rationale

People with various disabilities can accidentally initiate touch or mouse events. Allowing such end users to easily recover from such unintended pointer actions minimises unintended consequences such as accidental submissions.

## WO-16 — Label In Name

### Statement

Ensure that visible text labels of user interface components match or are contained within their programmatic or accessible names.

### Recommendations

Ensure that accessibility labels meaningfully describe the equivalent visual UI element by containing both the visible text label and other contextual descriptors that help assistive technology users fully understand the purpose and interaction.

### Rationale

Matching visible text labels with the programmatic component supports the use of assistive technologies such as allowing speech-input users to navigate by speaking the visible text labels of components.

## WO-17 — Motion Actuation

### Statement

Provide an option to disable motion control for motion-operated features, and provide alternative means to operate such features.

### Recommendations

When implementing motion-operated features, provide a way to disable motion actuation and offer alternative means to operate these features through user interface components.

Not required when motion is essential to the function, such as in pedometers that require device motion to count steps.

### Rationale

End users with motor impairments may have difficulty holding or moving a device steadily, which can prevent them from using motion-operated features and may cause accidental triggering of functions.

## WO-18 — Minimum Pointer Target Size

### Statement

Ensure that interactive areas for pointer input are at least 24 by 24 CSS pixels.

### Recommendations

Use min-height and min-width to ensure sufficient target spacing.

If targets have to be smaller than 24-pixels, they must be spaced so that a 24-pixel area around each target does not overlap adjacent targets.

Follow platform guidelines and consider larger target sizes for mobile applications and mobile web browsing where touch is the input mechanism.

Not required if the size of the interactive area is constrained by the line-height of non-interactive text such as text links within a body of text.

### Rationale

End users with physical and fine motor disabilities require more effort to accurately activate small targets or targets that are close to each other. Ensuring pointer inputs are large enough with sufficient spacing between targets reduces the likelihood of errors from accidentally activating the wrong control.
