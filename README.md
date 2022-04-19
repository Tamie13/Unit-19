# Unit-19



Unit 19 Homework: Protecting VSI from Future Attacks

Scenario
In the previous class,  you set up your SOC and monitored attacks from JobeCorp. Now, you will need to design mitigation strategies to protect VSI from future attacks.
You are tasked with using your findings from the Master of SOC activity to answer questions about mitigation strategies.

System Requirements
You will be using the Splunk app located in the Ubuntu VM.

Logs
Use the same log files you used during the Master of SOC activity:

Windows Logs
Windows Attack Logs
Apache Webserver Logs
Apache Webserver Attack Logs



Part 1: Windows Server Attack
Note: This is a public-facing windows server that VSI employees access.

**Question 1**

Several users were impacted during the attack on March 25th.
Based on the attack signatures, what mitigations would you recommend to protect each user account? Provide global mitigations that the whole company can use and individual mitigations that are specific to each user.

    -  Locking out accounts after a set number of failed login attempts is a mitigation strategy that would work globally as well as for individuals in the company.
    -  To slow down or prevent brute forcing by automation CAPTCHA can be used for mitigation.
    -  Use of cookies to prevent unrecognized servers or computers from accessing company server.
    
**Question 2**

VSI has insider information that JobeCorp attempted to target users by sending "Bad Logins" to lock out every user.
What sort of mitigation could you use to protect against this?

    -  Account lockout policies that set or have a threshold for the number of times login failure can happen per user accounts.  Zero threshold would stop attacks but a higher threshold number of 3 failed attempts before lockout occurs would be more feasible for mitigation in this instance. 
    -  To back this up, strong password policies are a must and should include minimum length of 12 as well as requied use of special characters and require that passwords must be changed every 90 days.

Part 2: Apache Webserver Attack:

Question 1

Based on the geographic map, recommend a firewall rule that the networking team should implement.
Provide a "plain english" description of the rule.

For example: "Block all incoming HTTP traffic where the source IP comes from the city of Los Angeles."


Provide a screen shot of the geographic map that justifies why you created this rule.


Question 2


VSI has insider information that JobeCorp will launch the same webserver attack but use a different IP each time in order to avoid being stopped by the rule you just created.


What other rules can you create to protect VSI from attacks against your webserver?

Conceive of two more rules in "plain english".
Hint: Look for other fields that indicate the attacker.




Guidelines for your Submission:
In a word document, provide the following:

Answers for all questions.
Screenshots where indicated

Submit your findings in BootCampSpot!

© 2020 Trilogy Education Services, a 2U, Inc. brand. All Rights Reserved.
