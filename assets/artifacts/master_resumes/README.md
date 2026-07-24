# Master resumes

These are the two canonical one-page resumes:

- `Vaghesan_Sundaram_Software_Resume.tex` / `.pdf` for general software engineering roles.
- `Vaghesan_Sundaram_Security_Resume.tex` / `.pdf` for secure software and cybersecurity roles.

Both sources import `resume_common.tex` so the contact information, education,
experience facts, project links, and typography stay consistent. The legacy
`../Vaghesan_Sundaram_Resume.tex` wrapper compiles the security master for old
links that still expect `Vaghesan_Sundaram_Resume.pdf`.

These two masters and the canonical wrapper are the only resumes maintained by
default. Files under `../tailored_resumes/` are an archive and should not be
rebuilt or synchronized unless tailored resumes are explicitly reactivated.

## Build

Run from `assets/artifacts` with XeLaTeX available:

```powershell
xelatex -interaction=nonstopmode -halt-on-error -output-directory=master_resumes master_resumes\Vaghesan_Sundaram_Software_Resume.tex
xelatex -interaction=nonstopmode -halt-on-error -output-directory=master_resumes master_resumes\Vaghesan_Sundaram_Software_Resume.tex
xelatex -interaction=nonstopmode -halt-on-error -output-directory=master_resumes master_resumes\Vaghesan_Sundaram_Security_Resume.tex
xelatex -interaction=nonstopmode -halt-on-error -output-directory=master_resumes master_resumes\Vaghesan_Sundaram_Security_Resume.tex
```

The shared template uses Times New Roman through `fontspec`, so the build host
must have that font or the font declaration must be changed deliberately.

## Validation gate

For both PDFs:

1. Confirm one US Letter page (612 x 792 points).
2. Extract text and confirm the name, phone, email, `Expected Fall 2027`, and
   section order are intact.
3. Confirm all header and project links are PDF link annotations.
4. Render the page and inspect it for clipping, crowding, and broken glyphs.
5. Search source and extracted text for stale dates, obsolete project links,
   unsupported skills, and future certification language.
