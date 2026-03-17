# Suraksha-saathi
A WhatsApp-native system to prevent sexual violence in India — full blueprint for developers
# 🛡️ Suraksha Saathi — Safe Friend

> *"Yatra naryastu pujyante, ramante tatra Devata."*
> — Where women are honored, the divine resides. (Manusmriti 3.56)

**A WhatsApp-native, AI-powered, culturally-rooted system to prevent and respond to sexual violence in India.**

Conceived and designed by **Siddharth Nayak** — student, not a developer.
This is a complete blueprint. I need developers to build it.

---

## Why This Exists

A rape is reported every **16 minutes** in India.
That is 90 cases every single day — just the reported ones.
The real number is estimated to be **10 to 20 times higher.**

On August 9, 2024, a 31-year-old doctor went to a seminar hall in her hospital to sleep between shifts. She was raped and murdered there. Her name is not mentioned here, as per law and dignity. The police took 14 hours to file the FIR. The nation protested for weeks. Then moved on.

This happens every day. To doctors, to children, to grandmothers, to Dalit women in fields, to girls in temples.

**Over 90% of perpetrators are known to the victim.**
**The national conviction rate is 27%.**
**10 Dalit women are raped every single day.**

Laws exist. Strong laws. BNS 2023, POCSO, fast-track courts.
The problem is not missing laws.

> The problem is culture. Awareness. Trust. And the fact that the factory producing perpetrators is the home — and nobody is going into that home.

No existing platform speaks to **new mothers of boys.**
No existing platform speaks to **fathers** in a language they trust.
No existing platform uses **scripture** — the most trusted moral framework for hundreds of millions of Indians — to teach dignity and accountability.

That is what Suraksha Saathi does.

---

## What This Is

Suraksha Saathi ("Safe Friend") is not a single app. It is **four layers working simultaneously:**

```
┌─────────────────────────────────────────────────────────┐
│  LAYER 1 — PRIYA (WhatsApp Bot)                         │
│  Digital spine. 24/7. Warm, human, Hindi.               │
│  Emergency triage → helplines → human handoff           │
├─────────────────────────────────────────────────────────┤
│  LAYER 2 — SAHELI NETWORK (Human Women)                 │
│  Trained ASHA workers, anganwadi, SHG members           │
│  First human contact for survivors in villages          │
├─────────────────────────────────────────────────────────┤
│  LAYER 3 — BADLAV MITRS & SURAKSHA MITRS (Men)          │
│  Respected village men + trained male college students  │
│  Peer-to-peer healthy masculinity. On the ground.       │
├─────────────────────────────────────────────────────────┤
│  LAYER 4 — SCHOOL CURRICULUM KIT                        │
│  Five 20-min modules using Ramayana & Mahabharata       │
│  No teacher training required. Reaches children first.  │
└─────────────────────────────────────────────────────────┘
```

---

## The Bot — Six Tracks, Three Pillars

The WhatsApp bot ("Priya") runs **six content tracks** simultaneously:

| Track | Keyword | For | Purpose |
|---|---|---|---|
| Aawaaz | `madad` | Survivors | Emergency triage, rights, helplines |
| Saathi Bano | `saathi bano` | Bystanders | 5-step first responder protocol |
| Nai Amma | `nai amma` | Mothers of boys 0–8 | Raising empathetic sons. Dharmic framing. |
| Ghar Ka Mard | `ghar ka mard` | Fathers, village elders | Voice-note first. Peer voices. Healthy masculinity. |
| Asli Mard | `asli mard` | Boys and men 14–25 | Rejection dignity, Bollywood deconstruction, consent |
| Guru Ji Ke Liye | `teacher hoon` | Teachers | Downloadable 20-min lesson modules |

Every message across every track carries **three pillars:**

1. **Dharma Kya Kehta Hai** — What does our own scripture say? Ramayana, Mahabharata, Shakti worship. Framed as god-fear, not ideology.
2. **Filmon Ka Jhooth** — Deconstructing the Bollywood scripts that normalise stalking, coercion, and entitlement.
3. **Na Sunna Seekho** — Rejection dignity. "Kisi ka aapko pasand na karna unka haq hai, aapki beizzati nahi."

---

## The Emergency Flow

When anyone sends `madad`, `help`, `bachao`, `rape`, `danger` or any distress keyword:

```
User sends trigger word
        ↓
Priya responds in < 2 seconds (no delay)
"Main yahan hoon. Aap akeli nahi hain.
 Abhi aap safe jagah par hain? [Haan / Nahi]"
        ↓                    ↓
    NOT SAFE               SAFE
        ↓                    ↓
  🔴 112 tap-to-call     Empathetic response
  📍 Location share      + human handoff to
  Nearest OSC            nearest Saheli Network
                         volunteer (< 3 min)
                               ↓
                    "Kya aap police ko involve
                     karna chahti hain?
                     Yeh aapki marzi hai."
                     (NEVER auto-route to police)
```

**Verified helplines hardcoded in the bot:**

| Helpline | Number | Available |
|---|---|---|
| Police / All emergencies | `112` | 24/7, WhatsApp-enabled |
| Women's Helpline | `1091` | 24/7, toll-free |
| NCW Helpline | `14490` | 24/7 |
| NCW Alternate | `7827170170` | 24/7 |
| One Stop Centre | `181` | 24/7 |
| Childline (POCSO) | `1098` | 24/7, toll-free |
| Vandrevala Foundation | `+91 9999 666 555` | 24/7, also WhatsApp |
| iCall TISS | `022-25521111` | Mon–Sat, 8am–10pm |
| Free Legal Aid (NALSA) | `15100` | Business hours |

---

## Design Principles — Read These Before Writing A Single Line Of Code

**The bot must never feel like a government helpline or an NGO tool.**

- ✅ Name: **Priya**. Display name: "Priya — Suraksha Saathi". Illustrated female avatar.
- ✅ Language: Conversational Hindustani. "Haan bolo, main sun rahi hoon." Never "Please select option 1."
- ✅ **2–4 second typing delay** on all non-emergency responses. Real people don't reply in 0.3 seconds.
- ✅ Session memory. Priya never asks users to repeat themselves.
- ✅ Human handoff is **celebrated, not apologised for.**
- ✅ Every message ends with: *"Yatra naryastu pujyante, ramante tatra Devata."*
- ❌ Never numbered option menus.
- ❌ Never auto-route to police without survivor's explicit consent.
- ❌ Never store survivor identity without consent.

---

## Tech Stack

| Component | Tool | Cost |
|---|---|---|
| WhatsApp API | [Glific](https://glific.org) — open-source, NGO-focused | Free |
| Backend | Node.js on [Railway.app](https://railway.app) | Free tier |
| Database | PostgreSQL on Railway | Free tier |
| Content CMS | Google Sheets | Free |
| AI layer | Claude API (`claude-sonnet-4-6`) | ~$0.003/msg |
| Voice transcription | OpenAI Whisper API | Pay per use |
| Scheduler | Railway Cron | Free |
| **Total at launch** | **All free tiers** | **₹0** |

---

## What Needs To Be Built — Pick Something And Own It

This is where you come in. The full specification document is in this repo. Here are the specific modules that need builders:

### 🔴 Priority 1 — Core Bot (Start Here)
- [ ] Glific setup and WhatsApp Business API integration
- [ ] Keyword detection engine (Hindi + English + misspellings)
- [ ] Emergency flow — triage tree with 2-second response
- [ ] Tier 1 helpline display with tap-to-call buttons

### 🟠 Priority 2 — Content Engine
- [ ] Google Sheets CMS integration for weekly message scheduling
- [ ] Subscriber opt-in flow with track selection
- [ ] Message scheduler (cron job reading Sheets, dispatching via Glific)
- [ ] Voice note transcription (Whisper API) for rural low-literacy users

### 🟡 Priority 3 — AI Layer
- [ ] Claude API integration for open-ended conversation fallback
- [ ] Language auto-detection and regional language switching
- [ ] Session memory — context retention within conversation
- [ ] "What Would You Do?" interactive story response handler

### 🟢 Priority 4 — Human Network
- [ ] Saheli Network volunteer registration module
- [ ] District + PIN code based volunteer matching
- [ ] Three-way WhatsApp connection initiation on handoff
- [ ] Badlav Mitr registration and weekly script delivery

### 🔵 Priority 5 — School Kit
- [ ] PDF generation pipeline for teacher curriculum modules
- [ ] WhatsApp-optimised delivery (under 5MB per module)
- [ ] Teacher opt-in flow and download tracking

---

## The Full Specification Document

The complete vision, strategy, all six tracks, all content samples in Hindi, bystander protocol, police integration strategy, scripture framework, narrative design guidelines, BNS 2023 legal reference, and the master build prompt — all in one document.

📄 **[Download: Suraksha_Saathi_Complete_Document.docx](./Suraksha_Saathi_Complete_Document.docx)**

Read this before you write code. Seriously.

---

## How To Contribute

1. **Read the spec document.** The entire system is designed. You are not starting from scratch — you are executing a blueprint.
2. **Pick one module** from the list above that matches your skills.
3. **Open an issue** titled with the module name so others know it's being worked on.
4. **Fork the repo**, build the module, open a pull request.
5. **Join the conversation** — open an issue if you have questions, improvements, or disagreements with the design. This is a collaborative document.

No contribution is too small. Even writing the Hindi message content, testing the emergency flow, or building the Google Sheets CMS template is valuable.

---

## What Already Exists — And What Doesn't

| What you'd expect to exist | Reality |
|---|---|
| A WhatsApp bot with emergency flow in Hindi | ❌ Does not exist |
| Content tracks specifically for fathers | ❌ Does not exist |
| New mothers of boys track | ❌ Does not exist |
| Scripture-based behaviour change content | ❌ Only in academic papers. Not deployed. |
| Rejection violence / acid attack prevention series | ❌ Does not exist |
| Respected village men as change agents | ❌ Does not exist |
| Bell Bajao (2008) | ✅ TV campaign, reached 130M, peaked and faded. **No digital successor exists.** |
| Government helplines 112, 1091, 181 | ✅ Exist — Suraksha Saathi routes to them |
| One Stop Centres (Sakhi) | ✅ Exist — Suraksha Saathi sends survivors there |

---

## Why This Approach Is Different

Most platforms try to help **after** the assault. Suraksha Saathi intervenes **before** — in homes, in schools, in WhatsApp groups — with the people who shape the next generation's values.

Most campaigns target **women**. Suraksha Saathi targets **men** — fathers, boys, village elders — because that is where behaviour changes.

Most awareness content uses **statistics and policy**. Suraksha Saathi uses **stories and scripture** — because that is what Indian culture has always used to transmit values, and it works.

---

## Roadmap

```
Month 1–2   Emergency flow live. Bot named Priya is responding to "madad".
Month 3–4   Track 1 (Aawaaz) + Track 4 (Ghar Ka Mard) live.
Month 5–6   AI layer + voice transcription. Rural users can send voice notes.
Month 6–8   Saheli Network volunteer module. Human handoff working.
Month 9–12  All six tracks live. School curriculum kit distributed.
Year 2      NCW partnership. Badlav Mitr network in 3 states.
```

---

## Contact

**Siddharth Nayak**
📧 siddharthnayak530@gmail.com

I am a student. I designed this system because I read about another rape and felt I had to do something more than feel helpless. I cannot build this alone. If you can write code, design systems, create Hindi content, record voice notes, or connect this to NGOs and institutions — reach out.

*If you are a developer who has ever wanted to build something that actually matters — this is it.*

---

## License

This project is open source under the **MIT License.**
Build it. Fork it. Improve it. Deploy it in your state. Just build it.

---

> *"Yatra naryastu pujyante, ramante tatra Devata."*
> Where women are honored, the divine resides.
>
> — Manusmriti 3.56
