\# Wireframe — Profile \& Settings



\## Goal



Give users one simple place to manage their profile, learning preferences, and app settings.



This screen should stay lightweight and should not become a second dashboard.



\---



\## Navigation



Bottom navigation:



\- Learn

\- Progress

\- You



You is the active tab.



\---



\## Screen — Profile



\### Header



\- User avatar or simple initials

\- User name

\- Current streak

\- Total XP



Example:



> Devesh  

> 🔥 6 day streak  

> ⭐ 1,240 XP



Keep the profile identity simple in v1.0.



\---



\## Learning Preferences



\### Topics



Show saved learning topics.



Example:



\- Python — 72%

\- C — 41%

\- C++ — 18%



Primary action:



\*\*Manage topics\*\*



Users can:



\- add a topic

\- switch their current topic

\- pause a topic



Changing topics must never delete or reset progress.



\---



\## Daily Goal



Show the current daily goal.



Example:



> Daily goal  

> 10 minutes



Action:



\*\*Change goal\*\*



Options:



\- 5 minutes

\- 10 minutes

\- 15 minutes



The default remains 10 minutes.



\---



\## Notifications



Setting:



\*\*Daily learning reminder\*\*



Options:



\- On

\- Off



If enabled, the user can choose a preferred reminder time later.



Do not build advanced notification scheduling in v1.0.



\---



\## Appearance



Setting:



\*\*Theme\*\*



Options:



\- System default

\- Light

\- Dark



Dark mode is supported in v1.0.



\---



\## Account



For the pilot, keep account functionality minimal.



Possible options:



\- Sign in

\- Sign out

\- Account information



Do not add complex account management.



\---



\## About



Show:



\- CodeFlow version

\- About CodeFlow

\- Feedback

\- Privacy

\- Terms



Keep these as simple navigation items.



\---



\## Empty State



If no profile information is available:



> Your profile will appear here.



The user can continue learning normally.



\---



\## Loading State



Show lightweight placeholders for:



\- profile information

\- XP

\- streak

\- topic progress

\- daily goal



Avoid blocking unrelated settings.



\---



\## Error State



If profile/settings data cannot be loaded:



> We couldn't load your settings.



Action:



\*\*Retry\*\*



Previously saved preferences should not be reset because of a temporary error.



\---



\## Topic Switching



Topic switching from the profile must behave exactly like switching from Learn.



Example:



Current topic:



> Python



User selects:



> C



The learning feed changes to C.



Python progress remains unchanged.



When the user returns to Python, their previous:



\- mastery

\- attempts

\- review state

\- completed cards

\- learning history



remain available.



\---



\## Wireframe Notes



Keep the screen:



\- simple

\- organized

\- easy to scan

\- focused on preferences



Avoid:



\- social profiles

\- followers

\- leaderboards

\- achievements taking over the screen

\- complicated account settings

\- subscription screens

\- advertisements

\- unnecessary customization

