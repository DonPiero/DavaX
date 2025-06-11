Timesheet RDBMS Project

This repository contains two implementations of the same Timesheet relational database:
- One in Oracle SQL Developer
- One in Microsoft SQL Server

Each version contains the same logic:
- 6 normalized tables ('employee', 'project' for every worked entry having the project field in our platform, 'task' same as project's situation, 'time_type' for either regular, overtime or any type of absences/ vacations, 'timecard' being a unique one for every worked week, 'entry' for every entry in a timecard)
- 5 views with different select statements('vw_all_timecards' for displaying all entries in a timecard with their corresponding employee, 'vw_employee_worked_hours' for displaying the total number of worked hours (regular and overtime) of an employee in a timecard, 'vw_hours_by_country' for displaying the total number of hours worked (regular and overtime) in a country, 'vw_entry_json' for displaying entries that have been submitted (field in JSON), 'vw_ranked_employees' by displaying a ranking of the hardest workers)
- 1 materialized view/ indexed view ('mv_project_hours' for displaying the total number of hours worked per project)
- 1 extra index ('idx_entry_date' on the entry_date field of the entry table)
- 1 trigger ('trg_no_timetravel_entry' for preventing entries with a date not in it's timecard start and end range)
- 1 procedure ('easy_draft_timecard_create' creates a new draft timecard with default values for a certain employee)
- sample data
