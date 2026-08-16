# CS499 Computer Science Capstone
Cj Carlos &middot; Southern New Hampshire University &middot; Summer 2026

![page builder](https://img.shields.io/badge/page%20builder-GitHub%20Pages-orange)
![language](https://img.shields.io/badge/language-HTML%20%7C%20CSS-blue)
![collaboration tool](https://img.shields.io/badge/collaboration%20tool-Git%20%26%20GitHub-lightgrey)
![editor](https://img.shields.io/badge/editor-VS%20Code-informational)
![license](https://img.shields.io/badge/license-MIT-green)

---

## Overview

This repository documents my process for developing my ePortfolio as the final project for
CS-499, the Computer Science Capstone. Creating a professional portfolio that showcases my
unique abilities is one of the best visual communication tools I have to demonstrate my value
to potential employers. The content of the ePortfolio is meant to give a clear, honest picture
of my skills across the key areas of computer science.

The artifact at the center of this ePortfolio is **Travlr Getaways**, a MEAN stack (MongoDB,
Express, Angular, Node) travel booking application I originally built in CS-465, Full Stack
Development. Rather than building three unrelated pieces, I went back through this single
application and enhanced it across all three required categories: software design and
engineering, algorithms and data structures, and databases. Coming from a background in quality
assurance and inspection work, that approach felt natural: go back through existing work the way
you'd go back through a flagged part, find what's actually wrong, fix it, and document the
reasoning clearly enough that someone else can trust it.

[![HOME](https://img.shields.io/badge/-HOME-2F6F6B?style=for-the-badge)](index.html)
[![EPORTFOLIO](https://img.shields.io/badge/-EPORTFOLIO-0E2038?style=for-the-badge)](https://wandererbush.github.io/cs499.github.io/)

---

## Self-Reflections

### [Journal: Emerging Technology & Capstone Update](<CS499 6-1 journal.docx>)
This paper looks at two technologies I consider genuine game changers, generative AI and
cloud computing, and reflects on how they're likely to shape computer science and my own
career. It also reports my progress against all five course outcomes and gives a status
checkpoint on all three enhancement categories heading into the final stretch of the capstone.

---

## Code Review

- [Software Design and Engineering Artifact](code-review.html)
- [Algorithms and Data Structure Artifact](code-review.html)
- [Databases Artifact](code-review.html)

I perform a code review of Travlr Getaways before making any enhancements, analyzing the
existing code for weaknesses, limitations, and vulnerabilities and explaining my plan for each
enhancement. The review walks through:

- **Existing functionality:** a walkthrough of how a request moves through the MEAN stack, from
  the Angular front end, through the Express API routes, to the MongoDB data layer.
- **Code analysis:** target areas for improvement in structure, efficiency, and data integrity,
  including two real bugs found while reading through the code, a stale-data bug in the trip
  update endpoint and an undefined error variable in the error handling.
- **Enhancements:** a walkthrough of the planned fix for each issue, mapped to the course outcome
  it was intended to demonstrate.

---

## Software Design and Engineering Enhancement

### [Narrative](<cs499 3-2 milestone (1).docx>)

This paper is the narrative that accompanies the software design and engineering artifact. It
explains why Travlr Getaways' authentication layer was selected for this category and reflects
on the process of building it. The original API had no authentication at all on the trip
create/update routes, so I added a `User` model with salted and hashed passwords, JWT
authentication via Passport, and role-based access control enforced through a reusable
`requireRole` middleware factory, plus matching route guards and an HTTP interceptor on the
Angular side.

---

## Algorithms and Data Structure Enhancement

### [Narrative](<cs499 4-2 milestone (1).docx>)

This paper is the narrative that accompanies the algorithms and data structure artifact. It
explains why the trip search and lookup logic was selected for this category and reflects on the
process of building it. The original code ran a fresh MongoDB query on every trip lookup with no
filtering endpoint at all. The enhancement introduces `TripIndex`, an in-memory hash map with a
code map for O(1) average lookups and a resort map that works as an inverted index for
multi-criteria search, kept in sync through an incremental `upsert` rather than a full rebuild on
every write.

---

## Databases Enhancement

### [Narrative](<cs499 5-2 milestone (1).docx>)
### [Live Enhancement Page](enhancement-databases.html)

This paper is the narrative that accompanies the databases artifact. It explains why the Trip
schema and trips controller were selected for this category and reflects on the process of
building it. The original schema only checked that fields were present, not whether the values
made sense, and a review of the controller turned up an undefined error variable that would have
crashed the server on any failed save. The enhancement adds real schema-level validation rules, a
`formatDbError` helper for clean client-facing error messages, and `runValidators` on the update
path, since Mongoose skips schema validation on updates by default.

---

## Professional Self-Assessment

### [Read the self-assessment](<CS499_Professional_Self_Assessment(1).docx>)

The self-assessment introduces me, reflects on how completing this program shaped my
professional goals coming from a QA and inspection background, and maps my work on Travlr
Getaways to all five program outcomes: collaborative environments, professional communication,
algorithmic trade-offs, well-founded tools and techniques, and a security mindset.

---

## Acknowledgments

Thank you to Professor Jeff Phillips for guidance throughout CS-499, and to the Southern New
Hampshire University Computer Science faculty for the four years of coursework this ePortfolio
represents.
