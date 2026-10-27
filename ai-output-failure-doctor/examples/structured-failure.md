# Synthetic example: post-generation type regression

Expected schema requires integer `count` and `additionalProperties: false`.
Model output: `{"count":3}`.
Delivered output: `{"count":"3"}`.
Transformer: `result.count = String(input.count)`.

Expected handling:

- Both outputs are valid JSON; only the delivered output violates the declared type.
- Earliest evidenced divergence is transformation, not model generation.
- The supplied transformer directly explains this field conversion. If its actual
  execution on this run is unproven, distinguish mechanism evidence from run provenance.
- No need for another paid model call: replay the transformer in an authorized safe
  test, and validate both stage outputs against the schema.
- Proposed fix: preserve the integer and validate at the transformation boundary.
- Verify exact type, required field and no-extra-field behavior, including zero and
  missing values. Do not claim the whole pipeline is fixed from one passing case.
