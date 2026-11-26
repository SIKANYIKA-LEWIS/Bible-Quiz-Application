# Scripture Sage — Bible Quiz

A JavaFX desktop quiz with 15 randomly selected Bible questions, a 30-second timer for each question, answer feedback, a final score, and a play-again option. It opens maximized and currently draws from a pool of 330 questions.

Game extras include a one-use 50:50 lifeline, fast-answer and streak bonuses, a warning when the timer is nearly out, Bible references after answering newer questions, and a locally saved personal-best score.

## Requirements

- Windows, macOS, or Linux with a desktop environment (JavaFX needs a graphical display).
- JDK 21. The Maven wrapper downloads Maven and project dependencies automatically; an internet connection is needed the first time.
- No database or other external service is required. Questions and images are bundled in the project.

## Run on Windows

Open PowerShell in the project folder (the folder containing `pom.xml`), then run:

```powershell
.\mvnw.cmd javafx:run
```

The first run can take a little longer while Maven downloads dependencies. To compile, run automated tests, and package the app:

```powershell
.\mvnw.cmd clean test package
```

On macOS/Linux, use `./mvnw javafx:run` and `./mvnw clean test package` instead.

Check which JDK Maven is using with `.\mvnw.cmd -version` (Windows) or `./mvnw -version` (macOS/Linux). It should report Java 21. If it reports another version, install JDK 21 and set `JAVA_HOME` to that JDK before launching Maven.

## Manual application test

1. Start the app with the command above. The welcome screen should open maximized and explain the quiz rules.
2. Select **START QUIZ**. A question, four answer choices, question count, progress bar, and countdown timer should appear.
3. Optional: use **50:50** once and confirm two wrong options disappear; the lifeline should then show as used.
4. Select an answer and press **LOCK IN ANSWER**. The correct answer should turn green; a wrong selected answer should turn red. A source reference should appear for referenced questions, and a correct answer should add points to your streak. The next question appears after a short pause.
5. Complete all 15 questions. The results screen should show your score, best streak, star graphic, and personal best. Earn more points by answering quickly and maintaining a streak.
6. Select **Play Again** and confirm a new quiz starts.
7. Optional: let the timer reach zero and confirm the quiz ends and shows the results screen.

Automated tests validate that the bundled question bank loads and that each question has the expected answer choices. They do not automate the JavaFX screens; use the manual steps above to test the UI.


