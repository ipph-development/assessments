# Assessment 

The React assignment should take you less than 2 hours to complete. If you go over, please stop. 

Send a link to paulzakin@bsd.uchicago.edu with a link to the private repo with your solution once complete. Be sure to share your repo with **paulzakin** (Paul's username) so we can access it.

## Overview

Build a React + TypeScript application utilizing the GitHub API to show data related to a given user. 

## Requirements

**Use Create React App or Next.js to avoid wasting time on configuration.** 

The app only has one page /. Hence, no routing required. 

The app fetches the results from this API call (https://api.github.com/users/[your-github-username]) with **any** GitHub username. 

> Example: https://api.github.com/users/paulzakin

The user enters the username in a search bar to fetch the result.

- The match should be an exact, lowercase match
- If no match is found, run window.alert("No match found!")

After the successful match has been fetched, present the following on the page: 

- Name 
- Bio 
- Username 
- Email
- Avatar (Through Avatar URL). 

The app should look reasonably nice and be mobile responsive. Don't use a CSS framework.
