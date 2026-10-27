# Synthetic example: AI-generated CSS

User: "Generated mobile UI doesn't match the design. Diagnose only."
Spec: CTA row must stack below 768 CSS px. Supplied complete style block:

```css
.cta { display: flex; flex-direction: row; }
@media (min-width: 768px) { .cta { flex-direction: column; } }
```

Expected handling:

- OBSERVED source-level breakpoint/direction mismatch with the explicit spec.
- INFERRED mobile horizontal arrangement if this CSS wins the cascade. Runtime
  computed style and other sheets were not inspected, so do not claim measured overflow.
- Propose column by default and row at min-width:768px; do not edit automatically.
- Verify computed styles/layout at 390, 767 and 768 CSS px plus a desktop viewport,
  checking labels, order and overrides. Report NOT RUN until executed.
- Do not assume framework utility names map to fixed pixels without configuration.
