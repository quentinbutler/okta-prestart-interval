# okta-prestart-interval


## Before you get started / prerequisites
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

1. User gets imported x days before their start date
2. Profile checker runs every 60 minutes
    A. Searches "staged" users
    B. Checks if pre-hire status has changed to Employee
    C. If (Y) then Activate, If (N) then flow ends here. 
3. Same-Day Activation (This is for immediate activations outside of the 60 minute interval. A scenario for this flow is if there is a user in orientation perhaps and they don't have an acconut etc)
    A. Trigger: Workday assigned to user 
    B. Flow checks if start date matches the date of import.
    C. If (Y) then user will activate immediately, If (N) then flow will go to wait status until date.


![PreStart Interval](https://user-images.githubusercontent.com/87619174/147149655-eb68bbf6-ee5c-4897-9dbd-03c928dc6f6f.png)

Resources:

https://help.okta.com/en/prod/Content/Topics/Provisioning/Workday/workday-provisioning.htm
