# About
Watch and participate along at: https://www.youtube.com/watch?v=k7MKERqbJWc


# Table of Content
- [Scenario Background](https://github.com/chan2git/tabletop-exercises/tree/main/it-governance-ltd_scenario-1#scenario-background)
- [Preparation](https://github.com/chan2git/tabletop-exercises/tree/main/it-governance-ltd_scenario-1#preparation)
- [Identification](https://github.com/chan2git/tabletop-exercises/tree/main/it-governance-ltd_scenario-1#identification)
- [Containment and Eradacation](https://github.com/chan2git/tabletop-exercises/tree/main/it-governance-ltd_scenario-1#identification)
- [Recovery](https://github.com/chan2git/tabletop-exercises/tree/main/it-governance-ltd_scenario-1#identification)
- [Lessons Learned](https://github.com/chan2git/tabletop-exercises/tree/main/it-governance-ltd_scenario-1#lessons-learned)

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


**Quiz 4: Out of the following, what would you *NOT* do to contain/eradicate this incident? Select all that applies.**

:x: Reset all passwords for accounts associated with the incident

:x: Implement a rule to restrict access to the malicious URL

:x: Refine email filtering rules

:x: Distribute a bulletin to all staff members to raise awareness about the phishing email

## Containment + Eradication

**Containment and eradication actions taken:**

- All HR user passwords are reset.

- Proxy changed and firewall rules updated.

- Applied email filters to proactively block similar phishing attempts.

- Restricting access from known malicious IP address.

- Communication was sent to all company staff to raise awareness of phishing campaign.


## Recovery

**Recovery actions advised**
- Proactively monitor IT environment for any suspicious/unusual activities

- Confirm with IT team they are good with affected devices/items to be reconnected back into the environment



## Lessons Learned
There are several things that come to mind when it comes to Lessons Learned. They can be broken up into categories: Prevention and Detection/Response. It is noted that it appears the threat actor maintained persistent for 2 months before someone on the HR team reached out to the IT team who then raised a security ticket. In those 2 months, several employees fell for phishing emails which were sent from Bob's email.

Further, there appeared to be many oppurtunities to reduce the MTTD. Ideally, a company should not rely solely on ticket submission before beginning to triage a potential incident. Imagine if the HR staff simply ignored that the fake login page didn't work and never reported to IT - the threat actors would continue to maintain persistence.

**Prevention**

Does the company provide mandatory anti-phishing trainings and refreshers to it's employees? Does the company facilitate a routine internal phishing tests conducted by the IT/Security team against employees from all departments? Does the company build a culture where it rewards its staff for being proactive, vigilent, and aware? When all else fails, are there any last step measures?

- Not everyone is security-savy. A good anti-phishing training can go a long way in introducing staff to security concepts, indicators of phishing, and how to timely report and respond should they suspect they have been a recipient or interacted with an unusual email.

- Learning is good, but to test is even better. The popular saying "You are your weakest link" is especially true, and they also say humans are easiest things to hack in a company. After implementing training to the general staff, the IT/security team should also run routine phishing tests against staff and measure how many people were able to report and how many people fell victim. Without measurements, one cannot continue to improve and build a robust campaign. Deploying a diverse set of phishing tests (**including from internal email domains to present a scenario where internal emails are comrpomised**) will assist in bolstering staff confidence in identifying and reporting phishing activity. The company should be mindful to celebrate and incentivize participation and not punish staff members who fail the tests. A strong security posture is a culture that involves everyone playing together as a team.

- Does the company have a policy of mandatory password rotations? Is it feasible? By routinely rotating passwords, you may be able to cut off a threat actor's persistence while being unaware of their presence, unless they've managed to gain persistence in other ways that transcends beyond simply having credentials.


Does the company have a threat intelligence team or utilize theat intelligence services? Were there any IOCs associated with the URL/email/threat group that could have been used by threat intelligence for preemptive (or at least a quicker) identification? If yes, then why weren't these IOCs incorporated into detection rules/firewalls beforehand?
- Threat intelligence provides a lot of value in being able to forecast/predict an imminent attack or to gather IOCs found in the wild that could be used to turn into a detection rule in advance.

- Threat intelligence could also be used to study trends and patterns amongst incidents. For example, if we know that our industry peers are being hit by the same APT who consistently use a specific script/tool and capatilizing on a specific vulnerability, then perhaps we should proactively assume that an imminent attack is on the way with similar TTPs.

- If the company isn't ready to build a threat intelligence team, then is it time to at least consider if it's a good business decision to subscribe to a vendor that can provide actionable intelligence?


Does the company utilize MFA? How fast can MFA be soundly implemented after this incident?
- MFA should be implemented to bolster Preparation and serve as an addition method of prevention and detection. It's possible that the threat actor could have been denied entry from failing MFA.
- MFA also serves as a potential detection rule which would greatly reduce MTTD if too many failed attempts are recorded.
- MFA tools such as YubiKeys serve as a great way to implement MFA as you need the physical key itself.


**Detection/Response**
     
What detections could be created so that when a similar event occurs, the company is not relying on non-Security staff to identify and report a possible incident? What additional changes could be implemented to provide more log resources for better detections? How can the MTTD be reduced from 2 months to something more acceptable?

- Detect email interactions with external/unusual/malicious domains
- Detect employee account activity when they are on leave/vacation/out of office/unusual hours
- Detect employee login from a non-typical/non-historical location/ISP/IP Address/device
- Detect when an employee account or device is using unusual browsers
- Detect when MFA fails repeatedly, or if MFA involves an unusual device/contact number
- Detect when a common identifier (device, IP address, etc.) is found to be logging into multiple employee accounts
- Determine what is an acceptable MTTD
- Detect when a malicious link or payload is embedded in the body message or attachment
- Detect when an employee accesses an unusual or malicious domain


Does the company implement SOAR tools and technology? How could measures be automated to cut off threat actor before triaging even starts?
- Similar to the potential detection rules listed above, SOAR could be implemented to automatically restrict the compromised account should specified conditions are met.
- It may be beneficial to determine the delicate balance between security and usability. How many MFA failed attempts before locking the account? Etc.