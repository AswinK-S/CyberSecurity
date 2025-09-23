# Phishing Email Analysis — Day 2 (Aswin KS)

**Source sample:** Screenshot provided `sample1_screenshot.png` (saved in phish_samples folder).

---

## 1) Obtained sample
- Sample type: **Screenshot / copied text** of suspected phishing email.
- File used: `/mnt/data/Screenshot 2025-09-23 140737.png`
- Saved copy for the repo: `phish_samples/sample1_screenshot.png` (recommend copying into your project folder before pushing).

---

## 2) Examine sender's email address for spoofing
- Visible sender: **Bank <info@bank-urgent.ca>**
- Red flags:
  - Domain uses a hyphen: `bank-urgent.ca` — unusual for a real bank (many banks use brand domain like `bankname.com`).
  - Generic display name "Bank" — attackers often use generic names to appear legitimate.
  - Multiple recipients listed in To: (john.doe@gmail.com, mich63277@hotmail.com, robert.smith@cablecorp.net) — bulk targeting is common in phishing.
  - **Action:** Hover over the address in the email client to confirm the exact address. If possible, view raw headers next.

**Conclusion:** The From address is suspicious and likely spoofed or at least not from an official bank domain.

---

## 3) Check email headers for discrepancies (how-to & what to look for)
*(You must extract raw headers from your mail client — do NOT paste any personally-identifying headers publicly.)*
- Steps to get headers:
  - Gmail: Open message → More (⋮) → **Show original**.
  - Outlook Desktop: Open message → File → **Properties** → Internet headers.
  - Thunderbird: Open message → **View → Message Source** (Ctrl+U).
- Inspect these header fields:
  - `From:`, `Reply-To:`, `Return-Path:` — mismatch indicates spoofing.
  - `Received:` chain — bottom-most received line usually shows origin IP. If origin IP is not from legitimate mail servers, suspicious.
  - `Authentication-Results:` — check `spf=`, `dkim=`, `dmarc=` results.
- If `spf=fail` and `dkim=none` or `dmarc=fail`, treat the mail as spoofed.
- **Recommend:** Paste only `Authentication-Results`, `From`, `Return-Path`, and bottom-most `Received:` lines (redact personal info) and I will analyze them for you.

---

## 4) Identify suspicious links or attachments
- Visible link text in email: `https://update.bank-urgent.ca`
- Footer (status bar) shows: `http://notice.bank-urgent.ca`
- **Red flag:** Link text and URL in the status/footer do **not** match — an obvious mismatch.
- **No attachments shown in screenshot**, but attachments would be suspicious by default unless you requested them.
- **Action:** Do **not** click links. Copy the URL text and check on VirusTotal or URLScan for reputation, or paste the URL into a text file for offline inspection.

---

## 5) Look for urgent or threatening language in the email body
- Phrases present:
  - "Security breach – Immediate action required"
  - "we are asking all our clients to immediately update their information"
  - "if the information ... is not updated within 48 hours ... complaints will be considered incidents unrelated ..."
- **Red flag:** Deadline (48 hours) and urgent tone are classic phishing tactics to push quick action.

---

## 6) Note any mismatched URLs (hover to see real link)
- As noted in (4), link label: `https://update.bank-urgent.ca` but status bar shows `http://notice.bank-urgent.ca`.
- This mismatch indicates the displayed link text is not the real destination. Attackers do this to trick users.
- **Actionable check:** Right-click → Copy link address (do not open) and paste into an online URL scanner (VirusTotal or urlscan.io) OR inspect it offline in a text editor.

---

## 7) Verify presence of spelling or grammar errors
- Examples found in email body:
  - "Rest assure" → should be **"Rest assured"**.
  - "This is an autmated message." → typo: **"automated"**.
  - Some sentences are awkward and missing articles or punctuation.
- **Red flag:** Legitimate corporate emails (banks) rarely have these errors.

---

## 8) Summary of phishing traits found (quick list)
- Suspicious sender domain: `bank-urgent.ca` (hyphenated, non-brand domain).  
- Generic display name "Bank" and multiple recipients.  
- Mismatched link label vs actual URL (update.bank-urgent.ca vs notice.bank-urgent.ca).  
- Urgent/Threatening language with a 48-hour deadline.  
- Spelling/grammar errors ("Rest assure", "autmated").  
- No proper authentication evidence (headers not yet checked; likely to fail SPF/DKIM/DMARC).

**Overall Verdict:** Very likely a phishing email. Do not click links or provide any credentials. Report to your organization's security team if applicable.

---



## Notes & Safety
- Do **not** click links in the email. Use VirusTotal or URLScan to analyze links safely.  
- When sharing headers or images, **redact** any real personal data or email addresses that are not required for analysis.

