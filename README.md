# okta-prestart-interval


## Before you get Started / Prerequisites
Before you get started, you will need:

Access to an Okta tenant with Okta Workflows enabled for your org

Workday as Master 

## Problem

"Preparation makes perfect" 

By default, Workday imports new hires on their start date. What if on that start date you have 20 engineers joining and you run out of SaaS licenses? What if there is a user with a mispelled name? What if the user doesn't have access to all of their day 1 apps?

The PreStart Interval is an optional field for early provisioning of Workday users. It allows you to onboard a user account into Okta prior to the official Worker/Employee Date (this is the employee’s actual start date). 

The interval represents the number of days prior to a Workday user’s stated Worker/Employee Date that Okta will evaluate a Workday user for early import. Okta evaluates the Workday PreHire Date; then if it falls within the set interval, Okta imports the user.

## Solution

Compliment the prestart interval by building a profile checker that activates imported staged users from Workday.


![PreStart Interval](https://user-images.githubusercontent.com/87619174/147149655-eb68bbf6-ee5c-4897-9dbd-03c928dc6f6f.png)


