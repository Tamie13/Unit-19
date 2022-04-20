# Unit-19



Unit 19 Homework: Protecting VSI from Future Attacks

Scenario
In the previous class,  you set up your SOC and monitored attacks from JobeCorp. Now, you will need to design 
mitigation strategies to protect VSI from future attacks.  You are tasked with using your findings from the 
Master of SOC activity to answer questions about mitigation strategies.


### Part 1: Windows Server Attack
Note: This is a public-facing windows server that VSI employees access.

**Question 1**

Several users were impacted during the attack on March 25th.
Based on the attack signatures, what mitigations would you recommend to protect each user account? 
Provide global mitigations that the whole company can use and individual mitigations that are specific to each user.

    -  Locking out accounts after a set number of failed login attempts is a mitigation strategy that would work 
       globally as well as for individuals in the company.
    -  To slow down or prevent brute forcing by automation CAPTCHA can be used for mitigation.
    -  Use of cookies to prevent unrecognized servers or computers from accessing company server.
    -  User limitations / permission need to be reviewed and more stringent limitations placed on access
       priviledges for non-admin users such as USER_J.
    
**Question 2**

VSI has insider information that JobeCorp attempted to target users by sending "Bad Logins" to lock out every user.
What sort of mitigation could you use to protect against this?

    -  Account lockout policies that set or have a threshold for the number of times login failure can happen per user accounts.  
       Zero threshold would stop attacks but a higher threshold number of 3 failed attempts before lockout occurs would be 
       more feasible for mitigation in this instance. 
    -  To back this up, strong password policies are a must and should include minimum length of 12 as well as requied 
       use of special characters and require that passwords must be changed every 90 days.

### Part 2: Apache Webserver Attack:

*Mapping iplocation before and after the atack revealed that before the attack Paris, France was the 
primary source of traffic as can be seen below.*

*Before The Attack1*
![TODO](https://github.com/Tamie13/Unit-19/blob/main/Unit%2019%20Screenshots/Apache%20Logs%20iplocation%20before%20attack.png)

*Attack logs show a large spike in traffic from the Ukraine who had little to no presence before the 
attack which can be seen in the image below.*

*After The Attack*
![TODO](https://github.com/Tamie13/Unit-19/blob/main/Unit%2019%20Screenshots/Apache%20Attack%20Logs%20iplocation%20pie%20chart.png)


**Question 1**

Based on the geographic map, recommend a firewall rule that the networking team should implement.
Provide a "plain english" description of the rule.

    -  Answer: Firewall rule to block all incoming HTTP traffic where the source IP comes from the Kiev, Ukraine. 
       Recommend also blocking outgoing traffic to unrecognized or validated client ip addresses orginiating 
       from out of the country.


**Question 2**

VSI has insider information that JobeCorp will launch the same webserver attack but use a different IP each time in order 
to avoid being stopped by the rule you just created.

What other rules can you create to protect VSI from attacks against your webserver?

Conceive of two more rules in "plain english".

    -  1. Use ingress and egress packet filtering that will also help to establish an 
          Access Control List (ACL) of permitted source ip addresses.
          
    -  2. Use IP-Level encryption protocols that will protect traffic going to and 
          from the companies enterprise server.


© 2020 Trilogy Education Services, a 2U, Inc. brand. All Rights Reserved.
