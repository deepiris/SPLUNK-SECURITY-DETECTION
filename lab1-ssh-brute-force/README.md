Read this first (60 seconds)
In one line: people around the world kept guessing passwords on one server, and none of them got in.
What we checked	Result	What it means
Wrong-password attempts	8,154	Someone was guessing passwords, a lot
Different attacking computers	181	Many sources, so not one single hacker
Busiest attacker	87.194.216.51 (218 tries)	Even the worst was only 2.7% of the total
Successful logins	380	All from 3 company-internal computers
Attackers who got in	0	No break-in found

How we found out, in 3 steps:
1.	Loaded the log into Splunk and counted the failed and successful logins.
2.	Pulled the computer address (IP) out of every failed login to see who was attacking.
3.	Checked whether any attacking address ever logged in successfully. None did.
What to do: turn off direct root login over SSH, use keys instead of passwords, and limit who can reach the server (firewall, VPN or fail2ban).
Usernames guessed: common defaults such as root, administrator, operator and admin. No single name dominates (root is only 4.2% of attempts).
Where to look in the rest: section 4 has the results, section 5 lists the mistakes we fixed, section 7 has the full recommendations, and Appendix A has searches you can copy and paste.
1. Executive summary
•	The log holds 8,534 password events: 8,154 failed and 380 accepted (Figures 4 and 9).
•	181 distinct source IPs produced failed logins (Figure 7). The ten busiest sources account for 1,401 failures (17.2%), led by 87.194.216.51 with 218 attempts. The activity is spread across many addresses, which is typical of automated brute-forcing.
•	All 380 successful logins came from three internal 10.x addresses. Only those three IPs both failed and succeeded, and their failure rate (about 10%) looks like ordinary mistyped passwords (Figure 10).
