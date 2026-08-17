# WCAG : Robust (WR)

Source: https://info.standards.tech.gov.sg/control-catalog/dss/wr/
Page last updated: 5 March 2026

Content © Government Technology Agency of Singapore, snapshotted from the public portal for grounding; canonical source is the live portal.

## WR-1 — Name, Role, Value

### Statement

Ensure that essential information of custom components and controls can be identified and read by assistive technologies.

### Recommendations

Essential information including name, roles, properties, values, states, and state changes are provided using techniques like ARIA labels.

Standard HTML controls should already meet this criterion when used according to specification. (example: text input field)

### Rationale

Enables end users of assistive technology to properly understand and interact with custom components.

## WR-2 — Status Messages

### Statement

Ensure that assistive technology can identify and announce system status changes that don't receive focus.

### Recommendations

Use ARIA roles and properties to inform users of status changes, such as when an incorrect text in an input is entered and a status message appears above.

### Rationale

Allows screen readers to identify and announce changes to content that may otherwise be missed by users of assistive technologies. This benefits users with visual impairments who unlike sighted users may not notice changes outside of their area of focus.
