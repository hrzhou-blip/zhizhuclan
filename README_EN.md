# ZhiZhu Clan Management System

**The only offline genealogy software built for Chinese kinship.**

> *"Know where you came from, light the way forward."*  
> *(知所从来，烛照其往)*

Website: [www.zhizhuclan.com](https://www.zhizhuclan.com)

---

## Why ZhiZhu?

Most genealogy tools were built for Western family structures. They handle biological parents and nuclear families well, but they break down when faced with the complexity of Chinese clan systems.

**Adoption with dual-line succession (过继)** — where a child simultaneously belongs to both the biological and adoptive lines.  
**Dual heirship (兼祧)** — where one son inherits two ancestral lines, with separate spouses and descendants for each house.  
**Uxorilocal marriage (招婿入赘)** — where the husband joins the wife's clan, and children carry the maternal surname.  
**Full female lineage records** — daughters with complete names, married destinations, and children; daughters-in-law with natal family addresses and parental information.

These are not edge cases in Chinese genealogy. They are core features. Yet Western software treats them as footnotes.

ZhiZhu was built from the ground up to handle these relationships as first-class data structures — not custom fields, not text notes, but formal relational records that the system can compute, visualize, and validate.

**Born in Shantou, China** — a city with deep historical ties to overseas Chinese communities across Southeast Asia and beyond. ZhiZhu is both a genealogy tool and a bridge.

---

## Core Features

### Pure Local Storage

All data stays on your computer. No cloud. No account. No registration. No internet required.

- Single SQLite database file per clan project
- Supports 1,000,000+ records per database
- Manage multiple clans independently via the project launcher
- Your clan data is your family's private asset — not a platform's product

### Built for Chinese Genealogy

Native support for complex Chinese kinship structures that Western software cannot model:

| Relationship | Western Software | ZhiZhu |
|:---|:---|:---|
| Adoption (过继) | Single parent pair, adoption as event note | Dual-line succession, simultaneous biological + adoptive lineage |
| Dual heirship (兼祧) | Not supported | One person inherits two houses, separate spouses and descendants per house |
| Uxorilocal marriage (招婿入赘) | Husband marked as spouse, no clan transfer | Husband joins wife's clan, children carry maternal lineage |
| Female records | "Wife of X" or surname only | Full name, married destination, natal family, children — independent node |
| Five degrees of mourning (五服) | Not supported | Automated calculation with adoption/dual-heirship path support |

### Universal Data Import

Coming from Ancestry.com, Family Tree Maker, Gramps, or another tool?

- **GEDCOM import** — bring your existing data directly into ZhiZhu
- **Excel/CSV import** — auto-recognizes column names in Chinese and English variants (Father/Dad/爹/father, Surname/Given Name, etc.)
- **Smart column mapping** — manual mapping for unmatched columns, preview before write
- **Horizontal-to-vertical auto-transpose** — handles spreadsheets where fields are row headers
- **Six-dimensional deduplication** — Generation × Gender × Spouse × Father × Mother × Grandfather cross-validation prevents duplicate entries
- **Multi-spouse support** — automatically splits multiple spouses in a single cell or across columns

We welcome you with a genealogy tool that actually understands Chinese kinship.

### 3D Galaxy Map

Traditional tree charts choke on large datasets — DOM/SVG rendering hits a CPU serial bottleneck at a few thousand nodes.

ZhiZhu replaces the tree with a **WebGL particle system**:
- Three.js r157 + TypedArray GPU buffer binding
- Custom recursive gravitational clustering + perturbation + repulsion algorithms
- Ring-shaped generational layout with constellation-like branch grouping
- **100,000 nodes stress-tested** — CPU ~2.5%, memory ~800MB–1.2GB, smooth interaction
- Special visual markers for adoption, dual heirship, and uxorilocal marriage
- Click any node to trace three generations of lineage

This is not a gimmick. It is a structural solution to a structural problem — and a reimagining of what a clan chart can look like on a digital screen.

### Smart Zibei Management (字辈)

Multi-generation naming tables with automatic character assignment. Set an anchor (which generation gets which character) and the system scans all members to assign generational names automatically.

### Data Quality Engine

13 automated validation rules covering generation, chronology, relationships, duplicates, and isolation. One-click repair with rollback support and whitelist exceptions.

### Traditional ↔ Simplified Chinese

Full UI language switching. Overseas Chinese from Hong Kong, Taiwan, and Southeast Asia can use the interface in Traditional Chinese; mainland users can switch to Simplified.

### Genealogy Typesetting Engine

Built-in automated typesetting engine. Enter your data, export a finished book.

**Four Layout Styles**
- **Biographical (行传)**: One person per card, most detailed
- **European Lineage Chart (欧式世系图)**: One name per cell, horizontal layout, lineage at a glance
- **Vertical-Bead Linked (垂珠连线版)**: Father-son connecting lines, modern visual style
- **Su-style Traditional (苏式垂珠古法)**: Traditional vertical-bead format, full father-son connections, classical genealogy aesthetics

**Typesetting Features**
- Six paper sizes: A4 / A5 / Standard 16K / Large 16K / Standard 32K / Large 32K
- Font size auto-scales with paper size; recommended persons per page auto-calculated
- Kinship relations auto-translated: adoption, dual heirship, uxorilocal marriage, and fosterage automatically identified and marked
- Dual-heirship members show separate spouses and children for each house; children grouped by mother
- Left-opening or right-opening binding, per regional custom
- Traditional ↔ Simplified Chinese output, one-click switch
- Surname protection: prevents incorrect conversion (e.g., 余 not converted to 餘)
- Auto-generated volume splits, name index, and cross-volume master index

**Print-Ready Output**
- Bleed lines, CMYK color mode, binding margins, crop marks
- Traditional double-line page frames
- Exported PDF can be sent directly to a print shop

**One-Click Book Assembly**
Cover (built-in template / custom image / none), preface, postscript, volume splits, name index, cross-volume index — the full skeleton from cover to index, assembled automatically.

The typesetting engine shares ZhiZhu's core design principle: **you only manage the data; the engine handles the book.** No parameter tuning, no layout learning curve.

### Hardware-Bound Encryption

AES-256 full-file encryption with device-specific key binding via Windows DPAPI. The development team holds no keys and cannot access your data.

⚠️ **Important**: Before switching devices or reinstalling your system, use the built-in **Export Backup** function. The exported file is your only credential for migration.

This is not a design flaw. It is a deliberate choice: your genealogy is your family's private property. We choose inconvenience over compromise.

---

## Data Sovereignty

- **No data collection** — We do not collect, upload, or share any user data
- **No servers** — We have no servers; we store nothing about you
- **No lock-in** — Export your complete data to Excel, CSV, JSON, or GEDCOM at any time, for free, without permission. Compiled for a year and want to switch software? Export everything today. We do not build data cages.
- **You are using software, not a platform**

### Distributed Compilation, Unified Import

Compiling a large clan genealogy is inherently a multi-person effort — each branch collects information, fills in forms, and submits them for consolidation. But genealogy is not Wikipedia. It involves strict rules of generation, seniority, and succession.

ZhiZhu's workflow:

1. **Chief compiler exports a blank template** — standardized Excel or CSV with all required fields
2. **Distribute to each branch** — branches fill in using Excel, no software installation, no new learning curve
3. **Collect and consolidate** — the chief compiler imports all returns in one go
4. **Automated processing** — column mapping, data transposition, person classification, relationship construction, six-dimensional deduplication, 13 validation rules, error repair — all automatic
5. **One-click commit** — confirm and write to database

The entire clan participates, but the data entry point is unified and controlled. One person operates the software, but the whole clan collaborates behind it.

---

## Root-Seeking Relay Station

### A single line in your genealogy may be the answer someone has searched for across generations

While compiling your clan records, you may have casually noted a piece of information that seemed trivial at the time — a daughter who married into a certain village, a son-in-law's family name, a daughter-in-law's natal address and parents' names.

What you may not know is that decades later, this very line could become the critical key to another family's search for their roots. Especially for descendants of those who left their homeland a century ago and crossed the oceans — they may hold only a vague place name, a surname passed down by word of mouth, yet they have searched for generations.

**This is what ZhiZhu wants to be: not a data pool for everyone, but a relay station for root-seekers.**

We do not hold anyone's data — it stays on the genealogist's own computer. What we do is help you ask, search, and match when you need it. One person searching alone is looking for a needle in the ocean. A group searching together changes the odds.

### To overseas Chinese: if you are looking for the road home

We know that in many overseas Chinese families, the last words an elder left behind were a place name.

"We came from Taishan. There was a big banyan tree at the village entrance."  
"Our ancestral home was in Chaoshan, next to the pond by the ancestral hall."  
"Your great-grandfather left Fujian by boat when he was sixteen."

Just that. No complete address. No contact. Sometimes not even the correct pronunciation — just an approximation passed down orally. Yet these few sentences have sustained the longing of generation after generation.

If you hold such a clue — even if it is only an approximate village name, an ancestor's name, an old photograph, or an oral migration story — reach out to us. We know many genealogists who may hold the very piece of information you need. We will help you ask, search, and match.

### To domestic genealogists: every name you record is a lantern

If you are compiling a clan genealogy, every piece of information you record — a daughter's married destination, a daughter-in-law's natal address, a clan member's relocation record — may become the lantern that guides an overseas compatriot home.

Those who were forced to leave during turbulent times — their names may still remain in some old genealogy book. You recorded them, and their descendants have a path to follow.

If you are willing to share part of your information to help root-seekers, contact us. We will help you connect with those who may be searching for this very clue.

### Why ZhiZhu can do this

- **Traditional & Simplified Chinese switching** — Overseas Chinese can use the software and read genealogies in the script they are comfortable with
- **Full female records** — Married daughters' destinations and daughters-in-law's natal information, often overlooked in traditional genealogies, are precisely the most important clues for root-seeking
- **Universal import** — No matter what format your family information is in, it can be imported and integrated
- **Pure local storage** — Your data stays on your own device; whether to share is entirely your decision

### What clues you can provide

The more specific, the better. Even a fragment may be the breakthrough:

- **Place names** — Ancestral hometown, migration origin, even an approximate pronunciation passed down orally. E.g., "Taishan," "Chaoshan," "Quanzhou," "Hakka," "Hainan"
- **Surnames & zibei** — Family surname, hall name (堂号), a line from the generational name poem
- **People** — An ancestor's name, nickname, birth/death years, or an out-married daughter's name and destination
- **Objects** — Old genealogy photographs, handwritten copies, ancestral hall inscriptions, ancestral tablet photos, old letters
- **Oral history** — Elders' oral migration stories, even if only a vague place name and a hazy memory

### Contact

- **WeChat**: zhizhuclan
- **Email**: zhizhuManager@163.com
- **Xiaohongshu (小红书)**: Search "知烛先生"

Every genealogist preserves family clues in their own way. When these clues are carefully recorded, they become keys to finding roots. And those names scattered across the world deserve to be found, deserve to be remembered, deserve to find their way home in the digital age.

**Know where you came from, light the way forward.**

---

## Free vs Paid

- **Free tier**: Up to 200 persons, 1 project. All features included.
- **Full version**: Annual subscription. Unlimited persons, unlimited projects.

---

## Tech Stack

Python · PySide6 · SQLite3 · Three.js · ngraph · D3.js · Inno Setup

---

## License & Contact

This is closed-source software with compiled code protection.

For inquiries, feedback, or root-seeking assistance, reach out via the channels above.

---

*[中文版完整介绍请见 README.md]*
