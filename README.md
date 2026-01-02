****# Good Energy (Archived)

**Status:** Archived / abandonware / historical reference only
**Intended use:** **Posterity, research, and code archaeology** — **not** reuse or deployment
**License:** GNU Affero GPL v3 (AGPL-3.0) — see `COPYING`

Good Energy is a behavior-change and employee engagement web app built around well-known findings from social psychology (e.g., social norms, pledges, identity). Historically, it was deployed in production with the David Suzuki Foundation (environmental sustainability) and a Vancouver-area school (student self-improvement).

It was designed as a **white-label** product: each customer could brand the header, footer, and CSS to appear integrated into a company intranet or a public website. Questions (top center) and default pledges (bottom right) were configurable via the Django admin interface.

---

## 2026 Warning: Do Not Reuse / Do Not Deploy

This repository is **abandonware** and is preserved **for posterity only**.

**Do not deploy this system** (especially not on the public internet). It targets an obsolete stack (Python 2.x-era + Django 1.x-era) and depends on historical packages and operational assumptions that are not safe by modern standards.

If you are looking for a behavior-change or engagement tool in 2026, treat this repository as a **case study** and re-implement the idea on a maintained stack.

### Security & operational risks (non-exhaustive)

* **End-of-life dependencies:** Python 2.x and early Django versions are long out of support and have unpatched vulnerabilities.
* **Outdated installation assumptions:** older third-party libraries, abandoned upstream URLs, and obsolete tooling.
* **Insecure default patterns in old deployments:** legacy cache and session configurations, missing modern security headers, etc.
* **Potentially dangerous “copy/paste” setup:** any legacy instructions that use trivial passwords or excessive database privileges are **not appropriate for production**.

**If you run this at all**, do so only in an isolated environment (offline VM/container), with fake data, and only for educational purposes.

---

## Support / Maintenance

There is **no official support** and no maintenance commitment.
The original authors were:

* [https://github.com/grahamking](https://github.com/grahamking)
* [https://github.com/jeremydosborn](https://github.com/jeremydosborn)

Please do not treat this as a supported product.

---

## What this project was

Good Energy’s top-level concepts:

* **Organization**: each deploying customer/tenant
* **Campaign**: a set of questions (Indicators), status updates, and pledges
* **Indicator**: a multiple-choice question answered repeatedly over time (Likert preferred)
* **Status updates**: entries that can have comments
* **Pledges**: actions users commit to, with comments and barriers

Campaigns were commonly run as fixed-date programs. A 5-week campaign length was recommended historically as a practical compromise.

---

## Archived Installation Notes (for historical context only)

These notes are preserved to reflect how the software was originally run. **They are not recommendations.** The stack and ecosystem referenced below are obsolete.

### Original dependencies (historical)

* Python 2.6+
* Django 1.3+
* A Django-supported database (historically tested with MySQL and Postgres)
* Memcached + Python bindings (**required at the time**)

Python libs (historical):

* pytz
* PIL (Python Imaging Library)

Django apps (historical):

* `sorl.thumbnail`
* `django-compress`

Optional worker (historical):

* Gearman + Python bindings
* `oilcan`

### SECRET_KEY (historical)

A random `SECRET_KEY` was required in `settings.py`. (Modern Django uses similar concepts but the surrounding security model has evolved.)

### Database configuration (historical)

Old readmes often suggested simplistic database credentials and privileges. **Do not use trivial passwords or excessive DB privileges** in any environment that matters.

---

## License

Good Energy is free software, licensed under the **GNU Affero General Public License v3 (AGPL-3.0)**. See `COPYING`.

---

## About this archive

This repository is kept public as a snapshot of an older era of Django/Python application design and a record of an applied behavior-change product. It is **not** a maintained reference implementation and is **not** a modern security baseline.
********
