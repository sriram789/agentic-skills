# Base Interviewer (Orchestrator)

This skill serves as the primary orchestrator and user interface for the interview preparation platform. It manages candidate intake, coordinates round schedules, handles session persistence, and creates the final assessment report.

## How it Works

1. **Candidate Intake**: Gathers basic information (candidate name, target role level, years of experience, target company, and resume text or file path) in a turn-by-turn interactive dialog.
2. **Target Company Research**: Conducts real-time web research to identify core values, typical interview patterns, and recent questions asked by the target company.
3. **Session Generation**: Generates a unique Interview ID and sets up a customized multi-round interview plan.
4. **Resume Validation**: Conducts a preliminary deep dive into the candidate's projects to verify hands-on knowledge.
5. **Round Coordination**: Automatically hands off execution to specialized interviewer skills and updates the session progress in `.agents/sessions/<candidate_name>_<interview_id>.json`.
6. **Consolidated Assessment**: Compiles scores, feedback, and transcripts from all completed rounds to generate a comprehensive final report at `~/interview/<name>-<interview_id>_assessment_report.md`.

## Efficient Usage

- **Respond Sequentially**: Answer intake questions one at a time as prompted, rather than combining all responses.
- **Save Your Interview ID**: Note the generated alphanumeric Interview ID to resume a paused session at any time.
- **Defend Your Resume**: The resume validation phase is designed to test depth of experience. Be ready to discuss exact scale bottlenecks, deployment strategies, and technical trade-offs of your listed projects.
