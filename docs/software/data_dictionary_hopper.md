---
layout: default
title: Hopper sync
parent: Data dictionaries
grand_parent: Software
nav_order: 2
---

# Hopper sync

This document contains the column names and descriptions for data synced from VoteAmerica+ to 
[Hopper by Community Tech Alliance](https://communitytechalliance.org/hopper). 

The Hopper team can work with you to transform this data into a format that suits your destination tool. 
[Learn more here about the Hopper sync](/integrations/hopper/). 

Data for all VoteAmerica+ tools are pushed to Hopper as part of a unified schema. 
Because different tools collect different information, 
some columns will have NULL values for tools where they do not apply.
The table below includes a column to indicate which VoteAmerica+ tools collect the data.

| Column title                 | Description                                                                                                                                                                                                                                                                                                                                 | Tools collecting this data                                                 |
|------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------|
| tool                         | The VoteAmerica+ tool that collected the data. Options: `absentee`, `futurevoter`, `locate`, `pledge`, `register`, `remind`, `upcoming`, `verify`                                                                                                                                                                                           | All                                                                        |
| subscriber_slug              | An identifier for the subscriber / customer                                                                                                                                                                                                                                                                                                 | All                                                                        |
| uuid                         | The ID we store internally for the action                                                                                                                                                                                                                                                                                                   | All                                                                        |
| subscriber_name              | The name of the subscriber (i.e. your customer name)                                                                                                                                                                                                                                                                                        | All                                                                        |
| subscriber_id                | VoteAmerica's internal identifier for the subscriber / customer                                                                                                                                                                                                                                                                             | All                                                                        |
| created_at                   | The date and time when data for this action was first submitted, in UTC                                                                                                                                                                                                                                                                     | All                                                                        |
| updated_at                   | The date and time when this action's data was last updated, in UTC                                                                                                                                                                                                                                                                          | All                                                                        |
| first_name                   | The user's first name                                                                                                                                                                                                                                                                                                                       | `absentee`, `futurevoter`, `pledge`, `register`, `remind`, `verify`        |
| last_name                    | The user's last name                                                                                                                                                                                                                                                                                                                        | `absentee`, `pledge`, `register`, `remind`, `verify`                       |
| date_of_birth                | The user's date of birth                                                                                                                                                                                                                                                                                                                    | `absentee`, `futurevoter`, `pledge`, `register`, `remind`, `verify`        |
| email                        | The user's email address                                                                                                                                                                                                                                                                                                                    | `absentee`, `locate`, `pledge`, `register`, `remind`, `upcoming`, `verify` |
| phone                        | The user's phone number                                                                                                                                                                                                                                                                                                                     | `absentee`, `locate`, `pledge`, `register`, `remind`, `upcoming`, `verify` |
| address1                     | The user's address1                                                                                                                                                                                                                                                                                                                         | `absentee`, `locate`, `pledge`, `register`, `remind`, `upcoming`, `verify` |
| address2                     | The user's address2                                                                                                                                                                                                                                                                                                                         | `absentee`, `locate`, `pledge`, `register`, `remind`, `upcoming`, `verify` |
| city                         | The user's city                                                                                                                                                                                                                                                                                                                             | `absentee`, `locate`, `pledge`, `register`, `remind`, `upcoming`, `verify` |
| zipcode                      | The user's zipcode                                                                                                                                                                                                                                                                                                                          | All                                                                        |
| state_id                     | The 2-letter code for the user's state                                                                                                                                                                                                                                                                                                      | All                                                                        |
| sms_opt_in_subscriber        | True/False if the user opted into the subscriber's SMS list                                                                                                                                                                                                                                                                                 | `absentee`, `locate`, `pledge`, `register`, `remind`, `upcoming`, `verify` |
| source                       | The ?source= query param                                                                                                                                                                                                                                                                                                                    | All                                                                        |
| utm_source                   | The ?utm_source= query param                                                                                                                                                                                                                                                                                                                | All                                                                        |
| utm_medium                   | The ?utm_medium= query param                                                                                                                                                                                                                                                                                                                | All                                                                        |
| utm_campaign                 | The ?utm_campaign= query param                                                                                                                                                                                                                                                                                                              | All                                                                        |
| utm_content                  | The ?utm_content= query param                                                                                                                                                                                                                                                                                                               | All                                                                        |
| utm_term                     | The ?utm_term= query param                                                                                                                                                                                                                                                                                                                  | All                                                                        |
| embed_url                    | The URL of the page where the tool was embedded                                                                                                                                                                                                                                                                                             | All                                                                        |
| session_id                   | The ID of a user's session. For tracking users across multiple tools or visits.                                                                                                                                                                                                                                                             | All                                                                        |
| status                       | (DEPRECATED) Indicator of an action's status for multi-step flows                                                                                                                                                                                                                                                                           | All                                                                        |
| finished                     | For tools that involve submitting data to an election office, this indicates the user has (1) clicked a link to visit a state site where they can complete the task, (2) emailed themselves a paper form to complete the task and downloaded it at least once, or (3) (DEPRECATED) had their PDF submitted to their Local Election Official | `absentee`, `register`, `futurevoter`                                      |
| self_print                   | If the user has emailed themselves a printable customized ballot request form (for `absentee` tool) or registration form (for `futurevoter` or `register` tool)                                                                                                                                                                             | `absentee`, `register`, `futurevoter`                                      |
| finished_external_service    | If the user clicked a link to visit their state's ballot request portal (for `absentee` tool) or online voter registration portal (for `futurevoter` or `register` tool)                                                                                                                                                                    | `absentee`, `register`, `futurevoter`                                      |
| leo_message_sent             | (DEPRECATED) If VoteAmerica's toolset directly submitted the ballot request (for `absentee` tool) or registration form (for `register` tool) to the user's Local Election Official                                                                                                                                                          | `absentee`, `register`, `futurevoter`                                      |
| total_downloads              | For users who have emailed themselves a ballot request or registration form, the number of times they clicked "download" in their email                                                                                                                                                                                                     | `absentee`, `register`, `futurevoter`                                      |
| referring_tool               | For users who were linked to this tool by another tool, the name of that referring tool                                                                                                                                                                                                                                                     | `absentee`, `register`, `futurevoter`                                      |
| registered                   | For `verify` actions, whether VoteAmerica's data provider indicated that the user has an active registration                                                                                                                                                                                                                                | `verify`                                                                   |
| unstructured_address         | The full, unstructured address provided by the user                                                                                                                                                                                                                                                                                         | `locate`                                                                   |
| register_confirmed           | If a `futurevoter` user has confirmed that they are registered to vote after receiving a reminder that they are now old enough to do so                                                                                                                                                                                                     | `futurevoter`                                                              |
| last_preregistration_message | The date and time when a `futurevoter` user last received an SMS message indicating they are now old enough to pre-register to vote                                                                                                                                                                                                         | `futurevoter`                                                              |
| last_drip_message            | The date and time when a `futurevoter` user last received an SMS message reminding them to check their registration now that they have turned 18                                                                                                                                                                                            | `futurevoter`                                                              |