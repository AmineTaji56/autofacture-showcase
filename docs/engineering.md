# Engineering notes

## Application structure

AutoFacture has two projects: a Laravel application serving a React interface through Inertia.js, and a Python document-processing service exposed through FastAPI. The Laravel application owns authentication, invoice records, vendor templates, validation, and human review state. The processing service handles document extraction requests.

PostgreSQL is configured for application persistence. The screenshot environment is an isolated SQLite preview containing sample records.

## Review workflow

The interface distinguishes extracted information awaiting review, records needing attention, and documents explicitly marked reviewed. Users edit invoice fields and save corrections before completing a review. Review state describes a user action, not a guarantee about financial correctness.

## Vendor templates

The document editor lets users select regions associated with extraction fields. Templates are saved against a vendor so that later uploads can use a known document layout. Region-based templates depend on document consistency; they do not establish universal extraction accuracy.

## Interface choices

The dashboard uses cobalt actions, lime progress highlights, navy contrast, and tinted surfaces. Manrope is self-hosted. Lucide supplies icons. Forms include labels, validation messages, processing feedback and password visibility controls. Responsive layouts adapt navigation and document review for narrow screens.

## Validation and remaining work

Development checks included frontend production builds, 18 authentication tests, and browser checks for responsive layouts and key UI interactions. These checks are not an independent security audit or a guarantee of production readiness.

Remaining evaluation includes OCR accuracy on representative invoices, end-to-end service integration under realistic conditions, outbound email delivery, and deployment validation against PostgreSQL.

## Showcase scope

Only curated screenshots and documentation belong in this repository. It intentionally has no executable application, setup credentials, customer data, or hosted demo. Do not add private application files when publishing updates.
