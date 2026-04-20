# AI Course — Contributor Guide

This repo hosts an **interactive, project-driven AI course** covering Computer Vision and GenAI (LLMs). The course is built project by project; each project is a self-contained, runnable app plus a short written lesson.

This file is the contract for anyone (human or Claude) working in the repo. Read it before starting work in any subfolder.

---

## Python environment policy

The canonical Python environment tool for this course is **[virtualenvwrapper](https://virtualenvwrapper.readthedocs.io/)** running on top of the system `python3`.

Do **not** use `venv`, `conda`, `poetry`, `uv`, `pipenv`, or `pyenv` in this repo. One tool, consistent muscle memory, works the same on every learner's machine.

### One-time shell setup (learner runs this themselves)

```bash
pip install --user virtualenvwrapper
```

Then add to `~/.zshrc` (or `~/.bashrc`):

```bash
export WORKON_HOME=$HOME/.virtualenvs
export VIRTUALENVWRAPPER_PYTHON=$(which python3)
source $(which virtualenvwrapper.sh)
```

Reload the shell once and virtualenvwrapper is ready.

### Per-project workflow

| Command | What it does |
|---|---|
| `mkvirtualenv <name>` | Create a new virtualenv named `<name>` |
| `workon <name>` | Activate that virtualenv |
| `setvirtualenvproject` | Bind the current folder to the active virtualenv so `workon <name>` later `cd`s here automatically |
| `deactivate` | Leave the virtualenv |
| `rmvirtualenv <name>` | Delete it |

**Naming convention**: the virtualenv name mirrors the project folder. For example, the project in `computer-vision/01-cv-playground/` uses the virtualenv `cv-playground`.

**Running any project** in this repo:

```bash
workon <project-name>
pip install -r requirements.txt
python app.py
```

Claude should **never** auto-activate, deactivate, or delete virtualenvs on the learner's behalf. Printing the command for the learner to run is fine; executing it is not.

---

## Repo layout

```
ai-course/
├── CLAUDE.md                   # this file
├── README.md                   # course intro for learners
├── computer-vision/            # CV track (classical CV first, then DL)
│   └── 01-cv-playground/
├── genai/                      # LLM / GenAI track (future)
└── shared/                     # reusable utilities shared across projects (future)
```

Every project folder is self-contained and ships with:

- `README.md` — what the project is, how to run it, exercises
- `LESSON.md` — the theory the project teaches, in plain language
- `requirements.txt` — pinned dependencies
- `app.py` or equivalent runnable entry point

---

## Teaching conventions

The course is **interactive and project-based**. Every project must satisfy three rules:

1. **Runnable demo.** The learner should get a working app within five minutes of `workon` + `pip install`.
2. **Plain-language lesson.** `LESSON.md` explains the theory without assuming prior CV / ML background beyond the course's stated audience (intermediate Python developers).
3. **Exercises.** Each project ends with 2–3 open-ended exercises that extend the code the learner just ran.

Lessons explain the *why* and the *intuition*. Code comments do not duplicate the lesson.

---

## Coding conventions

- Python 3, system-provided (whatever `python3` points to on the learner's machine).
- Formatter: `black`. Linter: `ruff`. Keep both clean before committing.
- Type hints on public function signatures. Internal helpers are free to skip them.
- Comments only where the *why* is non-obvious. Never narrate what the code does — identifiers already do that.
- Prefer editing existing files over adding new ones.
- Never commit sample media files larger than 2 MB. Link to them or generate them on first run.

---

## Course scope (living document)

The course grows project by project. The canonical ordering at the time of writing:

**Computer Vision track**
1. `01-cv-playground` — classical CV: interactive detection + segmentation workbench.
2. *(planned)* Deep-learning object detection.
3. *(planned)* DL-based semantic / instance segmentation.
4. *(planned)* Video and tracking.

**GenAI track** — begins once the CV track has two published projects.

Keep this list in sync as projects land.
