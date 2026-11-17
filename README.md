# Focus Nudge

**Inactivity-triggered notifications to support sustained attention while studying.**

Focus Nudge is a web application and HCI research study that tests whether a gentle prompt, fired when a student goes inactive during a study session, helps them focus and learn more, and how much it annoys them in the process.

> **Status:** In development. Study planned for November 2026.

---

## Research Question

> Do inactivity-triggered notifications (sound vs. visual, subtle vs. assertive) improve sustained attention and study efficiency compared to no intervention, and at what cost in annoyance or interruption?

## Hypotheses

| # | Hypothesis |
|---|------------|
| **H1** | Participants who receive inactivity-triggered notifications will score higher on the post-session comprehension quiz than participants who receive no notifications. |
| **H2** | Subtle notifications will produce quiz scores equal to or higher than assertive notifications. Assertive notifications may refocus the reader, but they may also interrupt comprehension. |
| **H3** | Participants will rate assertive notifications as more annoying and interruptive than subtle ones. |

## How It Works

1. A participant starts a study session in the web app and reads the provided study material on screen.
2. The app watches for input activity (scrolling, mouse movement, keypresses).
3. If the participant is inactive for a set period, the app fires a notification according to their assigned condition.
4. Every interaction, notification, and response (for example, time to resume activity or whether the notification was dismissed) is logged with a timestamp.
5. After the session, the participant takes a short comprehension quiz and fills out a brief questionnaire about their experience with the notifications.

### Experimental Conditions

| Condition | Description |
|-----------|-------------|
| **Control** | No notifications |
| **Auditory** | Sound-based notification on inactivity |
| **Visual** | Pop-up notification on inactivity |

Each notification type can be delivered at a **subtle** or **assertive** intensity. *(Final condition matrix to be confirmed by the team.)*

## Study Design

| | |
|---|---|
| **Participants** | 20-45 college students, ages 18-25, recruited through professors, clubs, and campus organizations |
| **Setting** | College computer lab, Windows 11 desktops with mouse and keyboard |
| **Duration** | About 15 minutes of studying plus a 5-minute assessment |
| **Incentive** | $5 cash per participant |
| **Timing** | An afternoon in November 2026 |

**Variables**

- **Independent:** notification presence, notification type (sound vs. visual), and assertiveness (subtle vs. assertive)
- **Dependent:** comprehension quiz score, attention and study efficiency, and perceived annoyance and interruption
- **Controlled:** study time, study material, quiz difficulty, and testing environment

## Data Collection

- **Automated interaction logs:** timestamped scrolling, mouse movement, keypresses, inactivity periods, notification events, and participant responses
- **Comprehension quiz:** same difficulty for every group; completed on paper to discourage LLM use
- **Post-session questionnaire:** 1-5 Likert items on how annoying, interruptive, and helpful the notifications were, plus an optional comment box
- **Video capture:** used after sessions to verify the logs and identify false alarms (the system flags inactivity, but the participant was actually reading or thinking). Participants give written consent beforehand.

### Privacy and Anonymity

- Participants are assigned a random ID (for example, `P01`). All logs, scores, and survey responses are stored under that ID only.
- No names or email addresses appear in data files.
- Consent forms are stored separately from the data.
- Results are reported only in aggregate (for example, average quiz score per condition).

## Tech Stack

- **JavaScript**, **HTML**, **CSS** for the web app, notifications, and activity detection
- Browser audio and DOM events for sound and visual notifications
- Session logs exported per participant as CSV/JSON, with no backend required
- Built primarily from scratch, using open-source techniques and LLM assistance as guidance

## Getting Started

> The app is not built yet. This section will be updated as development progresses.

```bash
git clone https://github.com/<org>/focus-nudge.git
cd focus-nudge
# Open index.html in a browser, or run a local server:
npx serve .
```

## Repository Structure *(planned)*

```
focus-nudge/
├── index.html        # Study session page
├── src/
│   ├── activity.js   # Inactivity detection (scroll, mouse, keys)
│   ├── notify.js     # Sound and visual notifications
│   ├── logger.js     # Timestamped event logging and export
│   └── conditions.js # Condition assignment (control / sound / visual)
├── assets/           # Notification sounds, styles, study material
├── study/            # Consent form, quiz, questionnaire, protocol
├── data/             # Anonymized session logs (P01, P02, ...)
└── docs/             # Study design, report, slides
```

## Limitations

- **False alarms:** inactivity may mean thinking or reading rather than distraction. The system cannot tell the difference, so we review recordings to identify and account for these cases.
- **Small sample:** 20-45 participants limits statistical power.
- **Single session in a lab:** results may not generalize to real-world studying.

## Related Work

- Hutt, S., Krasich, K., Brockmole, J. R., & D'Mello, S. K. (2021). *Breaking out of the lab: Mitigating mind wandering with gaze-based attention-aware technology in classrooms.* CHI 2021. https://doi.org/10.1145/3411764.3445269
- Mumcu, B. B., & Çebi, A. (2025). *You have a notification: The role of push notifications in shaping students' engagement, self-regulation and academic procrastination.* International Journal of Educational Technology in Higher Education. https://link.springer.com/article/10.1186/s41239-025-00537-x

### What this study adds

Prior work used gaze tracking to detect mind wandering or delivered notifications through a learning management system. Focus Nudge differs in three ways:

1. **Input-based detection** that needs no special hardware
2. **Comparison of notification styles** (sound vs. visual, subtle vs. assertive) rather than a single intervention
3. **Direct measurement of annoyance cost** alongside learning outcomes

## Team

- Oliver Liljeblad
- [Name]
- [Name]
- [Name]

*HCI course project, Albright College, Fall 2026.*

## License

[Choose a license, e.g. MIT]
