# AB testing best practices (technical)

This document is meant to help developers and QA engineers working with A/B experiments.

## General best practices

- Use plain Javascript, not the visual editors
- Make sure to minimize the flicker effect
- Make sure all elements involved in the experiment are loaded before the changes are triggered
- If possible, use existing elements and libraries already loaded on the page
- Make sure the experiment functions the same way on all targeted pages, devices, browsers, screen widths and no matter how you navigate to a targeted page

## Coding a test

### Step 1 - Planning

Start by reading through the test spec, see if you have all the necessary information and make sure the test is actually doable (i.e. doesn't require a back-end modification).

Divide your experiment (and code) into logical parts based on the type of changes you're making and/or the areas of the site you're modifying.

### Step 2 - Coding

There are various approaches one can take when building an A/B test but here's a common one.

1. In your favorite text editor, build a "skeleton" of the test
2. Start building the first change (in plain Javascript)
3. Test your code in your browser developer tools (copy-paste in the console)
4. Follow the process until all changes are implemented and everything looks OK

### Step 3 - Upload code in the testing tool

After writing the code in a text editor and testing it in the browser, it's time to move it into a testing tool. Most tools have a dedicated box for custom Javascript.

After uploading your code, generate a preview link and test it. Now it's time for configuring targeting and audience rules, goals and quality assurance.

## Naming conventions

Name of an A/B experiment should be short and descriptive. A good names containes the following information.

- Author (developer or team - only relevant if multiple teams are working under one account)
- Targeted page(s), page type or page group
- Changes (a short description of what changes are being tested)
- Target audience(s) (device group, traffic source, geolocation etc.)
- Version information
- Other relevant information

*Some examples:*

- CXL - HP - Benefits ATF - Mobile - V2 | (HP stands for Home Page and ATF stands for Above The Fold)
- CXL - GetApp - Promote Link to Reviews on SEM Landing Pages - Mobile
- CXL - GetApp - Priority 1 - Chicken Salad SEM Test - Mobile (Hotjar) (Relaunch)

## A/A tests

A/A test is a special type of A/B test where both variants are identical. The reasons why someone should run an A/A test are described below.

- To validate the installation/setup (before running any A/B tests)
- To check a new goal
- To validate the installation/setup after a major change

## Integrations

Depending on a testing tool that is being used, a manual integration with an analytics tool (i.e. Google Analytics) or a user behavior analysis platform (i.e. Hotjar) may be required.

## Developer checklist (pre-dev)

- Ensure that test spec contains all the necessary information for development.
- Read client/project/website wiki notes, check for site specific checklists or testing instructions
- Ensure that the test is functionally viable

## Developer checklist (pre-QA)

- All design changes are implemented correctly
- Check all core functions: Form submit, CTA, Login/Signup, Input fields etc.
- Test is working properly after page refresh
- URL targeting configured
- Device targeting configured
- Audience targeting configured
- Goals/Events added and firing properly
- Analytics integration activated & checked (if not automatic)
- Anything site/project/page specific?

## Quality assurance (QA)

The following items should be checked in the QA process

- Read client/project/website wiki notes, check for site specific checklists or testing instructions
- Confirm analytics integration
- Device Targeting
- URL Targeting
- Audience Targeting
- Goals/Events added and firing properly
- Custom Dimension added (if needed) 
- Check all relevant browsers (Chrome,Firefox,Safari,Internet Explorer,Edge)
- All design changes are implemented correctly
- Check all core functions: Form submit, CTA, Login/Signup, Input fields etc.
- Test is working properly after page refresh
- Make sure there are no conflicting tests
- Create a test audience/query parameter for live QA (if needed)
- Anything site/project/page specific?
