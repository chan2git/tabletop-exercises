# About





# Scenario 1: Phishing

## Scenario Background
HR staff reports issues to IT Service Desk regarding an email requesting a password change for their O365 account.
When clicking on the URL link and submitting credentials, they are not able to properly log in.


The email appears to come from a trusted source (Bob Smith, HR Manager). Bob Smith is currently on annual leave.


The IT team is responsible for authorizing email password changes. They are suspicious of the situation and raised a ticket to the Security team.

## Preparation 
This exercise omits a Preparation phase. See the Lessons Learned phase to see how the company can improve from this incident and strengthen the Preparation Phase for the next attack.


## Identification
**Who or what identified a potential incident?**

- The IT team identified a potential incident after reviewing HR team’s issues regarding a non-working link asking for credentials, which originates from an managerial employee who is currently on leave.

**What is the next step in verifying if this identified potential incident is an actual incident?**
- An initial triage of the reported incident needs to be conducted by the appropriate staff.

**Quiz #1: With regards to this scenario, how would you verify that a security incident has occured? Select all that applies.**

:white_check_mark: Ask a senior manager to contact Bob to establish more information about details around sending the emails to his team

:white_check_mark: The IT service desk should speak to the HR team to discover more details regarding the email received

:x: Contact senior team as this is not IT’s responsibility

:white_check_mark: Review the email itself


**Facts gathered from initial triage**

- The email utilized language that made the email appear to be urgent.

- After speaking with Bob, he stated that he had a similar email and that he submitted his credentials. Bob noted that the URL did not appear to work.


Based on the initial triage results, it is determined that this reported incident requires the IR team to be mobilized. 
Based on the facts gathered, the incident is rated as a P3 (due to incident appearing to only affect one isolated department; business operating as usual). The IR team agrees that a digital investigation is needed to gauge the impact/risk to the organization.


**Information to find out**

- Who else experienced a similar incident?

- Who else submitted credentials?

- What happens to the credentials when it is submitted to the link?


**Quiz 2: During this digital investigation, what would you consider? Select all that applies.**

:x: Working on the original devices/emails

:white_check_mark: Chain of Custody

:white_check_mark: Setting and following the objectives of the investigation

:white_check_mark: Keeping notes


**The Investigation key fact results are**
- Origin
    - The initial email was sent to Bob 2 months ago.

    - The initial email was sent from a Gmail account.

    - The initial email contained the same URL as the one sent to HR.

- URL
    - Fake link that led to a counterfeit O365 login page.

    - No payload was downloaded when link is clicked or page visited.

- Other
    - All of HR received an email from Bob

    - Half of HR submitted their credentials to fake O365 login page

    - Incident appears isolated to HR department only


**Quiz 3: According to NIST, what should be the next stage? Select one.**

:x: Prepare

:white_check_mark: Containment and Eradication

:x: Post incident

:x: Recovery

:x: Detection and analysis
