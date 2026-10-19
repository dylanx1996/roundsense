# RoundSense Privacy Policy

Effective date: 19 October 2026

This Policy explains what information RoundSense (the "Software") processes on your device and when it goes online, why, who receives it, how long it is kept and how you can exercise your rights.

## 1. Who is responsible and how to reach us

Controller (personal information processor): Dylan Su, the developer of RoundSense (an individual developer).

Contact: https://github.com/dylanx1996/roundsense/issues

GitHub Issues are public; please do not post anything there that you do not want to be public.

## 2. Overview

RoundSense is a CS2 demo review tool that runs on your computer:

- Parsing, analysis and match history are done and stored on your computer and are not uploaded to the Developer's servers.
- The Software goes online only in the cases listed in section 4. The user experience improvement programme and AI analysis are off unless you turn them on.

## 3. Information processed on your computer

| Information | Purpose | Where it is kept |
|---|---|---|
| Demo files you import or that appear in watched folders, and the match data parsed from them: players' SteamIDs, in-game names, positions, kills, economy, voice | Review, analysis, replay | Demo files are not copied; analysis results and replay caches are kept in `%APPDATA%\RoundSense` |
| The list of accounts that signed in to Steam on this computer (SteamID and display name from `loginusers.vdf`; account names and passwords are not read), and the SteamID-named folders in the Perfect World demo folder | Working out which player is you | Read at run time only; the account you pick is saved in the Software's settings |
| Voice extracted from demos | Playback in the replay | The cache folder in `%APPDATA%\RoundSense` |
| Your settings, training goals, findings you marked as "this is wrong", lineup screenshots and videos you import | Software features | `%APPDATA%\RoundSense` |
| The AI service key you enter | Calling the AI service you chose | `%APPDATA%\RoundSense`, encrypted with the Windows Data Protection API (DPAPI) |
| The random install number of the user experience improvement programme, and your choice | See section 4.1 | The Software's settings |

This information is kept until you delete the match or item in the Software, or delete the `%APPDATA%\RoundSense` folder. **Uninstalling the Software does not delete that folder**; to remove all local data, delete it after uninstalling. Apart from the AI key, this local data is not encrypted, and anyone who can sign in to your Windows account can read it.

## 4. Information processed online

### 4.1 User experience improvement programme (optional, off by default)

**Nothing is sent unless you have explicitly agreed.** You can opt in with the checkbox in the installer, on first start or on the About page. Not joining has no effect on any feature.

- **What is sent**:
  - a random install number, generated on your computer when first needed and unrelated to your SteamID, in-game name or hardware;
  - the Software version;
  - the interface language.

  The server records the date it receives them.
- **Please note**: the number stays the same, so the records sent from one computer on different days can be linked together. The statistics are pseudonymised, not completely anonymous.
- **What is never sent**: demo files, match data, SteamIDs, in-game names, file or folder paths, your Windows account name, hardware details or AI keys.
- **Purpose**: to count how many devices use the Software and which versions and languages are in use, to improve compatibility and stability and to decide what to work on. Legal basis: your consent.
- **How often**: at most once a day. If sending fails (for example when you are offline) it is simply skipped — it is not retried and does not affect the Software.
- **Recipients and international transfer**:
  - The statistics service runs on Workers and the D1 database provided by Cloudflare, Inc. (United States), so your data is transferred outside your country (including outside mainland China).
  - Network connections need your IP address: Cloudflare, as the network and computing provider, sees it while carrying the request.
  - The statistics program written by the Developer does not read or store IP addresses or any other request headers, and request logging for the service is turned off.
  - Processing that Cloudflare carries out for its own security and operations is governed by its privacy policy (https://www.cloudflare.com/privacypolicy/) and is outside the Developer's control.

  By opting in you separately consent to this transfer.
- **Retention**: each record is deleted automatically within about 400 days of being received.
- **Withdrawing**:
  - You can untick the box on the About page at any time, and the Software stops sending at once.
  - On withdrawal the Software sends the number to the statistics service once, asking it to delete all records under that number, and deletes the number from your computer. If you are offline at the time, it tries again the next time it starts online.
  - If you join again later, a new number is generated.

### 4.2 Checking for and downloading updates

- When you click "Check for updates", or if you have turned on the daily check, the Software contacts GitHub (GitHub, Inc., United States) to:
  - read the latest version number;
  - read the supporters list (`supporters.json`).
- When you click "Update now", the Software downloads the new installer from GitHub.
- These requests contain no personal data, but GitHub, as the service provider, sees your IP address; its privacy statement applies (https://docs.github.com/site-policy/privacy-policies/github-general-privacy-statement).

### 4.3 AI analysis (optional, off by default)

Only after you choose a provider and enter your own key in Settings, and only when you ask for an AI summary, does the Software send the structured data that one analysis needs to the provider you chose — Anthropic, an OpenAI-compatible service (such as DeepSeek) or another endpoint you enter.

- **What is sent**: map, score, rounds, positions, weapons, statistics, and the problems found by the rules with their descriptions; the descriptions may contain the in-game names of players in that match.
- **What is not sent**: demo files, file paths or your Steam account details.
- **Your key**: it is sent to the provider you chose only to authenticate, and is never included in usage statistics or written to log files.
- **The provider's processing**: how the provider processes and retains this data, and whether it uses it for training, is governed by the provider's own terms and is outside the Developer's control. The provider may be outside your country. Please read its terms before turning this on.
- **Kept locally**: the summary the AI returns is saved on your computer so it can be shown again.

### 4.4 Other actions you start

- **Report a problem**: the Software opens a pre-filled GitHub issue in your browser, which can include diagnostics (Software version, Windows version, whether CS2 was found, the number of matches in your library). You can review and edit it, or leave out the diagnostics, before deciding whether to submit it; submitted issues are public.
- **Opening external links**: the site opens in your browser and its own policies apply.
- **Opening a replay in CS2**: starts the game on your computer; no data is sent over the network.

## 5. What we do not do

- We do not upload your demo files.
- We do not read your Steam account name or password, or game memory.
- We do not sell personal information, use it for advertising or combine it with other data to build profiles.

## 6. Your rights

Depending on the law that applies to you, you have rights to be informed, to decide, to access, to obtain a copy, to correct and to delete your personal information, to withdraw consent, to object and to ask for an explanation.

- **Local data** is all on your own computer: you can view, export or delete it directly.
- **User experience improvement programme records**:
  - withdrawing deletes them, as described in section 4.1;
  - you can also send a request using the contact in section 1, quoting the random number shown on the About page. Without that number the Developer cannot find your records.
- **Complaints**: if you believe your rights have been infringed, you can contact the Developer or complain to the data protection authority where you live.

## 7. Security and its limits

- **What is in place**:
  - all network requests use HTTPS;
  - the AI key is stored encrypted with DPAPI;
  - the statistics service accepts only fields in a fixed format and discards everything else;
  - reading the statistics requires the Developer's key.
- **Limits**:
  - local analysis data is not encrypted;
  - the security of third-party providers (Cloudflare, GitHub, AI providers) is outside the Developer's control;
  - no security measure is absolute.

## 8. Children

The Software has no features aimed at children. If you are under 14 (or under the age of digital consent where you live), please join the user experience improvement programme or use AI analysis only with your parent's or guardian's consent.

## 9. Changes to this Policy

Revised versions will be published on the releases page and in the Software. If the purposes, the kinds of personal information or the recipients change, the Software will tell you the next time you open it and will stop sending usage statistics until you agree again.

## 10. Language

This Policy is available in Chinese and English. If the two versions differ in interpretation, the Chinese version prevails, without affecting any mandatory protection applicable law gives you.
