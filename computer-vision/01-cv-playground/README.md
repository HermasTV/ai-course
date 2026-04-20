# Project 01 — CV Playground

> An interactive, slider-driven lab for exploring classical Computer Vision algorithms — side-by-side input, pipeline illustration, and output, all in one window.

## What this project is

The **CV Playground** is the first hands-on project of the course. It is a single desktop app that lets you:

- Load an image.
- Pick a classical CV algorithm from a menu — a mix of **detection** and **segmentation** techniques.
- Tune each algorithm's parameters with live sliders and watch the output update in real time.
- See an **illustration panel** that shows the intermediate stages the algorithm went through, so you are not just looking at a final answer — you are watching the pipeline work.
- Save any result you like, together with the exact parameters that produced it.

The goal is not to memorize one algorithm. The goal is to build intuition: *when does Canny work better than Sobel? Why does HSV segmentation fail on shadows? What does K-means actually do to colors?* A playground is the fastest way to learn that.

## Who it is for

Intermediate Python developers who are new to Computer Vision. No prior CV or ML background is assumed — only comfort with Python.

## What you will learn

By the end of this project you will have:

- A working mental model of the two big families of classical CV: **detection** (finding things in an image) and **segmentation** (grouping pixels that belong together).
- Hands-on feel for roughly a dozen of the most-used OpenCV algorithms.
- A reusable workbench you can throw new images at whenever you want to test an idea later in the course.
- A plug-in pattern for adding your own algorithm to the playground as one of the exercises.

## Running it

Once the project is implemented, the flow will be:

```bash
workon cv-playground
pip install -r requirements.txt
python app.py samples/<some-image>
```

See the root [CLAUDE.md](../../CLAUDE.md) for how to set up `virtualenvwrapper` if you have not already.

## What comes with the project

- A small pack of sample images (shapes, coins, a document, faces, colored objects) — enough variety to make every algorithm interesting.
- A written lesson (`LESSON.md`) explaining the theory in plain language, one short section per algorithm.
- A set of exercises at the end that build on the code you just ran.

## Status

Scaffolding in progress. The implementation, lesson content, and sample pack are tracked in the repo's plan file and will land incrementally.

## Where this fits in the course

This is project **1 of the Computer Vision track**. It intentionally covers only **classical CV** — no deep learning yet. Deep-learning detection and segmentation come in later projects, and by then you will already know what problems they are solving and why.
