# Family Feud — Tournament Edition
## Cowork Project Context

---

## What This Is

A browser-based **Family Feud party game** built as a single HTML file (`family-feud-tournament.html`). It was custom-built for a party with friends in Copenhagen. The game is tournament-style with 4 families, real show mechanics, and a dual-view design: one screen for the audience and a hidden Quiz Master (QM) control panel for the host.

---

## Game Rules (as implemented)

### Tournament Structure
- **4 families** enter names at setup
- **Semi-Final 1**: Family 1 vs Family 2
- **Semi-Final 2**: Family 3 vs Family 4
- **Final**: SF1 winner vs SF2 winner
- Visual bracket updates after each match with final scores
- Champion screen at the end

### Each Match = 2 Rounds

Each round uses **one question** with **top 3 answers only** (trimmed from the real show's longer answer sets).

**Round flow:**

1. **QM selects a question** from the 50-question bank (played questions are greyed out)
2. **Buzzer** — QM selects who buzzed first and what they answered:
   - If they got **#1**, they control the board
   - If not, the other team gets one attempt
   - Whoever had the **higher-ranked answer** wins control
   - If both wrong, the first buzzer wins control
3. **Play or Pass** — The controlling team chooses:
   - **Play**: they try to name all remaining answers
   - **Pass**: the other team plays instead
4. **Playing** — QM reveals correct answers; marks strikes for wrong ones
   - **Max 2 strikes** (not 3 like the real show — our custom rule)
   - After 2 strikes → **Steal phase**
5. **Steal** — The non-playing team gets **one guess only**:
   - Correct → steal team wins ALL points on the board
   - Wrong → playing team keeps ALL points
6. **Award** — QM confirms, points added to match total
7. After Round 1: brief pause, then Round 2 begins with a new question
8. After Round 2: match ends, higher score advances

### Point System
- Each question's 3 answers have real survey point values (out of 100)
- Example: Q1 answer #1 = 44pts, #2 = 42pts, #3 = 7pts
- Revealed points accumulate on the board; all go to whoever wins the round

---

## Dual-Screen Design

### Audience Board (`s-match` screen)
- Shows the question, tile slots (hidden until revealed), and strike dots
- Shows both team names and running match scores
- Status bar narrates each phase (e.g. "FAMILY 1 IS PLAYING!")
- Tile reveal has animation; strikes flash red

### Quiz Master Panel (QM Panel)
- Hidden behind a **◀ QM** toggle button (top-right corner)
- Intended for a **second device** (e.g. tablet or second laptop) — though it's on the same page
- Always shows all 3 answers + point values (the audience can't see this)
- Context-aware: shows only the relevant controls for the current phase
- Controls: select question → buzzer → play/pass → reveal/strike → steal → award
- Shows running round points and match score at all times

---

## Question Bank Summary

50 questions total. Each has exactly 3 answers with point values.

Topics covered:
- Relationships / marriage / dating
- Work / office life
- Body / health / embarrassing moments
- Animals and nature
- Social situations / parties
- Sleep habits / everyday life
- Children / family
- Procrastination and habits
- Food / restaurants

Questions are sourced from real Family Feud show seasons (S16, S20) plus originals written in the same style. All are deliberately non-American-specific so they work with an international crowd.

### Full Question Bank (50 questions)

| # | Question | A1 (pts) | A2 (pts) | A3 (pts) |
|---|----------|----------|----------|----------|
| 1 | Name something you might do at work to convince your boss you're too sick to be there. | Cough violently (44) | Vomit / fake throwing up (42) | Sneeze maniacally (7) |
| 2 | Name something you'd hate to find out was living in the walls of your house. | Termites / bugs (45) | Rats / mice (42) | Snakes (5) |
| 3 | Name a musical instrument perfect for someone full of hot air. | Tuba (56) | Trumpet (17) | Trombone (8) |
| 4 | Name a gesture a mother would be shocked to see her baby making in an ultrasound. | Flipping the bird (63) | Waving hello (10) | Peace sign (9) |
| 5 | Name a gripe about your computer you could also have about a partner. | Too slow (68) | Doesn't work / always crashing (20) | Won't follow commands (4) |
| 6 | Name a place where it's perfectly fine to sing — even if you're terrible. | In the shower / bath (61) | At church / a religious service (26) | At a karaoke bar (7) |
| 7 | Without a tongue, you couldn't lick what? | Ice cream / popsicle (62) | A lollipop (23) | Yourself / your nose (6) |
| 8 | Name something a man takes along when shopping with his wife. | Cash / wallet / credit cards (56) | His phone / earphones (24) | Something to read (13) |
| 9 | Name something cats do when fighting that rival humans might also do. | Scratch / claw (69) | Screech / hiss (13) | Bite (11) |
| 10 | Name something an elderly person might love that's wrinkled. | Their partner / spouse (66) | Prunes / dried fruit (22) | Old comfy clothes (5) |
| 11 | In a crime thriller, name something the villain urgently needs to get rid of. | The weapon (58) | The body (27) | Blood / other evidence (6) |
| 12 | Name a reason a much younger man might marry a much older woman. | She has a lot of money (87) | He genuinely loves her (4) | She's experienced / exciting (4) |
| 13 | Name something a baby does that would be completely unacceptable in a flatmate. | Cry / wail at 3 a.m. (39) | Soil / wet themselves (28) | Vomit on you (9) |
| 14 | Name something you love doing when you're completely alone. | Reading (27) | Watching TV / films (26) | Taking a long bath (18) |
| 15 | Name something a housefly dies from that you'd hate as your own cause of death. | A flyswatter (74) | Bug spray / insecticide (6) | Starvation (5) |
| 16 | Name something you have to squeeze really hard before anything comes out. | A lemon / citrus fruit (25) | Ketchup / mustard bottle (25) | Toothpaste (19) |
| 17 | Name something a man wears trying to impress women that actually repels them. | Way too much cologne (66) | A Speedo (9) | A toupee / terrible wig (6) |
| 18 | Name something that could ruin a romantic horse-drawn carriage ride. | Horse relieves itself near you (37) | Horse has terrible gas (25) | Rain or a storm starts (10) |
| 19 | Name information you don't want but expect your best friend to tell you. | Your partner is cheating (38) | You've put on weight / look bad (33) | You have food stuck in your teeth (8) |
| 20 | Name an occupation where the more attractive you are, the more money you make. | Exotic dancer / stripper (38) | Model (25) | Actor / entertainer (11) |
| 21 | Name someone a cool teenager would be mortified to see show up at their party. | Their parents (58) | An embarrassing celebrity / person (11) | The school nerd / geek (9) |
| 22 | If a man isn't attractive, he'd better have a beautiful ___. | Personality (31) | Smile (17) | Heart / soul (17) |
| 23 | Name something you'd hate to smell when climbing into your date's car. | Rubbish / old food (29) | Cigarette / cigar smoke (19) | Fresh flatulence (14) |
| 24 | Name something a woman brings to bed after a tough breakup. | Food / ice cream / chocolate (38) | Her pet (15) | A stuffed animal / teddy bear (11) |
| 25 | Name something surprising grandparents might still do if they were former hippies. | Smoke cannabis (74) | Dance wildly to old music (7) | Kiss passionately in public (4) |
| 26 | Name a sign your partner might secretly be turning into a cat. | Meowing or purring (37) | Clawing and scratching everything (21) | Growing whiskers (18) |
| 27 | Name something a married man gets in trouble for telling others about his wife. | Her weight / measurements (40) | That she snores (18) | Her real age (14) |
| 28 | Name what most men would do if a first date started describing her dream wedding in detail. | Run for the exit / bail (86) | Listen politely (5) | Smile awkwardly and say nothing (2) |
| 29 | Name something people always seem to lose. | Their keys (45) | Their phone (28) | Their glasses / sunglasses (12) |
| 30 | Name a real reason someone calls in sick when they're perfectly healthy. | A hangover (35) | Just needed a day off / laziness (30) | Personal plans / a date (15) |
| 31 | Name something people do in a lift / elevator when completely alone. | Check their phone (40) | Stare at themselves in the mirror (22) | Press buttons for no reason (15) |
| 32 | Name something you'd definitely find on the floor of a teenager's bedroom. | Clothes everywhere (40) | Dirty dishes / snack wrappers (25) | Charging cables and tech stuff (15) |
| 33 | Name a reason someone might be late to their own wedding. | Cold feet / last-minute nerves (45) | Traffic / transport problems (20) | Hair, makeup or getting ready (15) |
| 34 | Name something people do when they feel extremely nervous. | Sweat profusely (35) | Bite their nails (25) | Talk too much / ramble (18) |
| 35 | Name something you start cleaning when procrastinating on something important. | The kitchen / dishes (32) | The bathroom (28) | Your desk or workspace (15) |
| 36 | Name something a dog does when it's overjoyed to see you come home. | Wags its tail furiously (50) | Jumps all over you (25) | Barks or howls excitedly (12) |
| 37 | Name something wedding guests love to complain about. | The food (not enough or bad) (35) | The music / DJ (28) | The seating arrangement (15) |
| 38 | Name a type of weather people complain about most. | Rain (38) | Extreme heat / humidity (28) | Freezing cold (20) |
| 39 | Name something people do at a party they deeply regret the next morning. | Drink way too much (50) | Dance embarrassingly (20) | Say something stupid to someone (12) |
| 40 | Name something people do when they're bored. | Scroll through their phone (40) | Watch TV / stream something (25) | Eat snacks (15) |
| 41 | Name a reason you'd feel embarrassed in a doctor's waiting room. | Running into someone you know (38) | Your name / condition called out loud (30) | Your phone going off loudly (15) |
| 42 | Name something you do before sleeping that you also do when you wake up. | Check your phone (40) | Brush your teeth (30) | Go to the bathroom (15) |
| 43 | Name something you take to the beach that you never actually end up using. | A book (35) | Sunscreen (stays in the bag) (28) | Sports / exercise equipment (15) |
| 44 | Name something married couples argue about most often. | Money / finances (40) | Household chores (28) | The in-laws (12) |
| 45 | Name something a diner does that makes everyone around them cringe. | Talks loudly on their phone (35) | Sends food back repeatedly (25) | Lets children run wild (18) |
| 46 | Name something people famously do in their sleep. | Snore (55) | Talk in their sleep (22) | Sleepwalk (12) |
| 47 | Name a time of day when everyone seems to be in a terrible mood. | Monday morning (45) | Rush hour / commute time (28) | Early morning before coffee (15) |
| 48 | Name something people do when they think nobody is watching. | Pick their nose (45) | Dance or sing to themselves (25) | Talk to themselves (12) |
| 49 | Name something you'd see on a table at a birthday party. | A birthday cake (60) | Balloons / decorations (20) | Presents / gifts (12) |
| 50 | Name a reason someone might quit a job they just started. | The boss / management is awful (42) | The pay is terrible (35) | The work environment / colleagues (15) |

---

## Code Structure (HTML file)

The entire game is a **single self-contained HTML file** — no server, no dependencies, no npm. Open it in any browser.

### Key sections:

```
<style>               — All CSS (CSS variables, screens, tiles, QM panel, animations)
#s-setup              — Team name entry screen (4 families)
#s-bracket            — Visual tournament bracket
#s-match              — Live game board (audience view)
#s-champ              — Champion celebration screen
#qm-btn               — Toggle button for QM panel
#qm-panel             — Sliding Quiz Master control panel
#flash                — Full-screen red flash overlay for strikes

<script>
  Q_BANK[]            — 50 questions with answers and point values
  G{}                 — Global game state object
  startTournament()   — Initialises bracket, teams
  startMatch(id)      — Loads a match (sf1/sf2/final)
  selectQuestion(i)   — QM picks question, enters buzzer phase
  buzzWho(ab)         — QM sets who buzzed first
  buzzAnswer(i,isSecond) — QM records the buzzer answer(s)
  choosePlayOrPass()  — Winning team elects to play or pass
  revealAnswer(i)     — QM reveals a correct answer tile
  addStrike()         — QM records a wrong answer
  stealGuess(i)       — QM records the steal guess
  doAward()           — Confirms points, advances round/match
  startRound2()       — Resets for round 2
  endMatch()          — Records result, updates bracket
  render()            — Master render (calls renderBoard + renderQM)
  renderBoard()       — Updates audience screen
  renderQM()          — Updates QM panel with phase-correct controls
  toggleQM()          — Slides QM panel in/out
```

### State object `G` (key fields):
- `G.teams[]` — 4 team name strings
- `G.bracket` — sf1, sf2, final objects with teamA/B indices, scores, winner
- `G.currentMatch` — 'sf1'|'sf2'|'final'
- `G.round` — 1 or 2
- `G.q` — current question object
- `G.revealed[]` — [false,false,false] for each of the 3 answers
- `G.strikes` — 0, 1, or 2
- `G.playingTeam` — 'a' or 'b'
- `G.stealTeam` — 'a' or 'b' (always opposite of playingTeam)
- `G.phase` — current game phase (drives all QM controls)
- `G.usedQ` — Set of used question indices
- `G.bFirst/bControl/bStep` — buzzer sub-state

### Phase flow:
```
select_q → buzzer (bStep: who→first_ans→second_ans→done) → playing → steal → award_playing/award_steal → between_rounds → select_q → playing → ... → match_end
```

---

## Known Limitations / Possible Improvements

1. **No second device separation** — QM panel is on the same page as the audience board. For a real party, you'd want the QM panel on a separate URL/window. Could be solved by extracting QM to a separate HTML file that communicates via localStorage events.

2. **No timer** — Real show has a countdown. Could add a 30-second timer for the playing phase.

3. **No sound effects** — Buzzer sound, wrong answer buzz, correct answer ding would improve the experience greatly. Web Audio API or pre-loaded audio clips.

4. **Mobile-unfriendly QM panel** — The QM panel works on tablet but is cramped on phones. Could be improved with a dedicated mobile layout.

5. **No "Fast Money" round** — The real show ends with a bonus round. Could be added as an optional 3rd round.

6. **Question randomisation** — Could shuffle or filter questions by difficulty / theme.

7. **Score persistence** — If the browser refreshes, all state is lost. Could use localStorage to checkpoint state.

8. **Printable scoreboard** — A summary view at match end showing round-by-round breakdown.

---

## How to Use This in Cowork

1. Save both files (`family-feud-tournament.html` and `FAMILY_FEUD_CONTEXT.md`) into a folder, e.g. `~/Desktop/FamilyFeud/`
2. Open Claude Desktop → switch to **Cowork** tab
3. Grant Cowork access to that folder
4. Use the prompt below to kick off your task

### Suggested Cowork Prompt

```
I have a Family Feud tournament game in this folder. The full context, rules, and code structure are in FAMILY_FEUD_CONTEXT.md. The game itself is in family-feud-tournament.html.

Please read the context file first, then help me with:
[describe what you want — see ideas below]
```

### Example tasks for Cowork:
- "Add a 30-second countdown timer to the playing phase"
- "Split the QM panel into a separate HTML file that syncs with the main board via localStorage"
- "Add sound effects: a buzzer sound on strike, a ding on reveal, applause on award"
- "Add 20 more questions to the question bank, keeping the same format and international style"
- "Create a printable PDF scoreboard showing all match results and round scores"
- "Add a Fast Money bonus round after Round 2"
- "Make the game work better on a phone screen for the QM panel"
```
