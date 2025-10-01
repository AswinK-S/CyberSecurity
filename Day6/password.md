1. **passwords**
  
  Hello_it'sMe@95_Here
  IamA_Hero@17ForSure
  Super_Idea@ForWeek
  This_isNot@15Funny
  JokEoFTheDay@88
  HeadAcheFor444#$
  Pas_swordForMe@12
  Qwerty@1
  ACbdf@1

2. **Test each password on password strength checker** 
     ` [ https://bitwarden.com/password-strength/ ] `

     Hello_it'sMe@95_Here - strong - estimated time to crack = centuries
     IamA_Hero@17ForSure - strong - estimated time to crack = centuries
     Super_Idea@ForWeek - strong - estimated time to crack = centuries

     `[ https://www.passwordmonster.com/ ] `

       This_isNot@15Funny  -very strong - Time to crack your password:48 centuries
       JokEoFTheDay@88 -very strong -  Time to crack your password:69 thousand years
       HeadAcheFor444#$  -very strong -  Time to crack your password:5 thousand years
       Pas_swordForMe@12 -very strong - Time to crack your password:49 centuries
       Qwerty@1  -   very wear- Time to crack your password:0.02 seconds
       ACbdf@1  -     weak  -  Time to crack your password:27.36 minutes

**.Identify best practices for creating strong passwords.**

  To create strong passwords, make them long (at least 12-16 characters), random (mix uppercase and lowercase letters, numbers, and symbols), and unique (different for every account). Avoid using personal information, common words, or easily guessable patterns. You can use a password manager to generate and securely store complex passwords, or create a memorable passphrases using a unique phrase, like a song lyric or book quote, and then add numbers and symbols.

  **.Write down tips learned from the evaluation**

  ✅ Best Practices

Length Matters → Use at least 12–16 characters (the longer, the stronger).

Mix It Up → Combine uppercase, lowercase, numbers, and special characters (! @ # $ % ^ & *).

Avoid Common Words → Don’t use names, birthdays, “123456,” “password,” or keyboard patterns (qwerty, abcd).

Passphrases Work Well → Create a phrase from random words, e.g. "Sun!Train99_PurpleSky". Easy to remember, hard to guess.

Unique Per Account → Never reuse the same password across multiple accounts.

Don’t Share Passwords → Keep them private and avoid writing them down in plain text.

Use a Password Manager → Tools like Bitwarden, 1Password, or LastPass can generate and store strong passwords securely.

Enable 2FA (Two-Factor Authentication) → Adds an extra layer of security, even if your password is leaked.

❌ What to Avoid

Pet names, family names, or favorite sports teams.

Repeating characters ("aaaa1111").

Short passwords (under 8 characters).

Password reuse across sites.


***common password attacks***

1) Brute-force attack

What: Attacker tries every possible password until one works (often automated). 


Signs: Many failed login attempts from same IP or account; account lockout alerts.
Defenses: strong long passwords, rate limiting, account lockouts/throttling, MFA.

2) Dictionary attack

What: Tries words from a dictionary (common words, permutations) instead of every possible string. Often faster than pure brute force. 


Signs: Rapid attempts using real-word passwords.
Defenses: block common passwords, use password complexity/length, use breached-password checks.

3) Credential stuffing

What: Use lists of breached username/password pairs against many sites — relies on password reuse. Very high-volume and automated. 


Signs: Successful logins from unfamiliar locations/IPs soon after a large breach; account takeover reports.
Defenses: unique passwords per site, password managers, MFA, monitoring for reused/breached credentials, bot-detection and IP reputation checks.

4) Password spraying

What: Attacker tries a small set of common passwords (e.g., Password1!) across many accounts to avoid lockouts. Effective against organizations with weak/default passwords. 


Signs: Many different accounts show single failed attempt from same IP range; low-and-slow login attempts.
Defenses: enforce strong passwords, detect abnormal authentication patterns, enable MFA, logon anomaly detection.

5) Phishing (and spear-phishing)

What: Trick users into revealing credentials (fake login pages, malicious links). Spear-phishing targets specific people. 


Signs: Unexpected emails asking to “confirm” credentials, login pages with odd URLs, sudden credential usage from new devices.
Defenses: user training, email filtering, link preview tools, MFA, browser/site-certificate checks.

6) Keyloggers / credential-stealer malware

What: Malware (or browser stealers) captures keystrokes, clipboard contents, or stored passwords. Recent reports show stealer malware and M-as-a-Service are increasingly common. 


Signs: Unusual processes on device, new accounts/transactions, credentials observed on dark web.
Defenses: endpoint protection/EDR, keep systems patched, avoid running untrusted binaries, use hardware MFA keys where possible.

7) Rainbow-table / precomputed hash attacks

What: Attacker uses precomputed tables to reverse common password hashes quickly (works when salts are absent or weak).
Signs: Offline compromise of hashed password database.
Defenses: salt + strong hashing (bcrypt/argon2/scrypt), slow hash settings, rotate/expire credentials after breaches.

8) Man-in-the-Middle (MitM)

What: Attacker intercepts traffic and steals credentials (e.g., on unsecured Wi-Fi) or via an intermediary server. 


Signs: Unexpected certificate errors, logins from odd IPs, user reports of strange network behavior.
Defenses: use HTTPS, HSTS, VPNs on untrusted networks, certificate pinning, MFA.

9) Shoulder-surfing / social engineering

What: Direct observation, phone scams, or impersonation to get credentials.
Signs: Someone asking for passwords/OTP, people looking over shoulders in public places.
Defenses: never disclose passwords/OTPs, privacy screens in public, security awareness training.

10) Hybrid attacks

What: Combine techniques (e.g., start with dictionary, then brute force on likely variants).
Defenses: multi-layered controls above + monitoring and incident response.

***summary***
Longer passwords → exponentially increase the number of possible combinations, making brute-force attacks far slower.

Mix of characters (upper, lower, numbers, symbols) → expands the character set, so attackers need to try many more possibilities.

Avoiding dictionary words & patterns → reduces the risk of dictionary or common-password attacks.

Unique per account → prevents credential stuffing when one password is leaked.

👉 In short: the more complex and unique a password is, the harder it becomes for attackers to break it using automated methods.