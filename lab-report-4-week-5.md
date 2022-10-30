# Find Command Options
* Note: All commands are done within the technical folder (as working directory)

## Command Line Option: -newer

* This command shows all files that we're changed or created after the file listed
* When is this useful?: If you made edits to files because of the addition or modification of a certain file, by using this command, you can see all the files you changed in relation to that original file.

### Example #1
Input ~
```
technical % find 911report -newer */chapter-6.txt
```

Output ~
```
911report
911report/chapter-7.txt
911report/chapter-9.txt
911report/chapter-8.txt
911report/preface.txt
```

* We are showing files in the 911report directory which are newer than the chapter-6.txt file from 911report

### Example #2 
Input~
```
technical % find government -newer */Media/Workers_aid_center.txt 
```

Output~
```
government
government/Post_Rate_Comm
government/Post_Rate_Comm/Gleiman_EMASpeech.txt
government/Post_Rate_Comm/Mitchell_spyros-first-class.txt
government/Post_Rate_Comm/Cohenetal_CreamSkimming.txt
government/Post_Rate_Comm/Cohenetal_DeliveryCost.txt
government/Post_Rate_Comm/Mitchell_RMVancouver.txt
government/Post_Rate_Comm/Gleiman_gca2000.txt
government/Post_Rate_Comm/Cohenetal_Cost_Function.txt
government/Post_Rate_Comm/Redacted_Study.txt
government/Post_Rate_Comm/Mitchell_6-17-Mit.txt
government/Post_Rate_Comm/Cohenetal_comparison.txt
government/Post_Rate_Comm/Cohenetal_Scale.txt
government/Post_Rate_Comm/Cohenetal_RuralDelivery.txt
government/Post_Rate_Comm/ReportToCongress2002WEB.txt
government/Post_Rate_Comm/WolakSpeech_usps.txt
government/Media
government/Media/water_fees.txt
government/Media/balance_scales_of_justice.txt
government/Media/highlight_Senior_Day.txt
government/Media/agency_expands.txt
government/Media/not_accessible_to_disabled.txt
government/Media/predatory_loans.txt
government/Media/Working_for_Free.txt
government/Media/help_rent-to-own_tenants.txt
```

* We are showing files in the government directory which are newer than the Workers_aid_center.txt file in the government/Media directory

### Example #3
Input~
```
technical % find government/Post_Rate_Comm -newer */Media/Workers_aid_center.txt
```

Output~
```
government/Post_Rate_Comm
government/Post_Rate_Comm/Gleiman_EMASpeech.txt
government/Post_Rate_Comm/Mitchell_spyros-first-class.txt
government/Post_Rate_Comm/Cohenetal_CreamSkimming.txt
government/Post_Rate_Comm/Cohenetal_DeliveryCost.txt
government/Post_Rate_Comm/Mitchell_RMVancouver.txt
government/Post_Rate_Comm/Gleiman_gca2000.txt
government/Post_Rate_Comm/Cohenetal_Cost_Function.txt
government/Post_Rate_Comm/Redacted_Study.txt
government/Post_Rate_Comm/Mitchell_6-17-Mit.txt
government/Post_Rate_Comm/Cohenetal_comparison.txt
government/Post_Rate_Comm/Cohenetal_Scale.txt
government/Post_Rate_Comm/Cohenetal_RuralDelivery.txt
government/Post_Rate_Comm/ReportToCongress2002WEB.txt
government/Post_Rate_Comm/WolakSpeech_usps.txt
```

* We are showing files in the government/Post_Rate_Comm directory which are newer than the Workers_aid_center.txt file in the government/Media directory
---
## Command Line Option: -mtime

* This command shows files based on when they were created, in terms of days
* When is this useful?: If you want to see the most recently added files to a project, or you want to access a recently created file but don't remember its name.

### Example #1
Input~
```
technical % find 911report -mtime -8
```

Output~

(There is no output for this input)

* We are showing files in the 911report directory which were created LESS THAN (-) 8 days ago, none in this case

### Example #2
Input~
```
technical % find 911report -mtime +8
```

Output~
```
911report
911report/chapter-13.4.txt
911report/chapter-13.5.txt
911report/chapter-13.1.txt
911report/chapter-13.2.txt
911report/chapter-13.3.txt
911report/chapter-3.txt
911report/chapter-2.txt
911report/chapter-1.txt
911report/chapter-5.txt
911report/chapter-6.txt
911report/chapter-7.txt
911report/chapter-9.txt
911report/chapter-8.txt
911report/preface.txt
911report/chapter-12.txt
911report/chapter-10.txt
911report/chapter-11.txt
```

* We are showing files in the 911report directory which were created MORE THAN (+) 8 days ago

### Example #3
Input~
```
technical % find 911report -mtime 9
```

Output~
```
911report
911report/chapter-13.4.txt
911report/chapter-13.5.txt
911report/chapter-13.1.txt
911report/chapter-13.2.txt
911report/chapter-13.3.txt
911report/chapter-3.txt
911report/chapter-2.txt
911report/chapter-1.txt
911report/chapter-5.txt
911report/chapter-6.txt
911report/chapter-7.txt
911report/chapter-9.txt
911report/chapter-8.txt
911report/preface.txt
911report/chapter-12.txt
911report/chapter-10.txt
911report/chapter-11.txt
```

* We are showing files in the 911report directory which were created EXACTLY 9 days ago
---
## Command Line Option: -size

* This command shows files based on how much space they use, in terms of whatever the user specifies (can be kibibytes, mebibytes, gibibytes, etc.)
* When is this useful?: Can be used to see if there are any files taking up a ton of space that you want to remove/modify.

### Example #1
Input~
```
technical % find 911report -size +1k
```

Output~
```
911report/chapter-13.4.txt
911report/chapter-13.5.txt
911report/chapter-13.1.txt
911report/chapter-13.2.txt
911report/chapter-13.3.txt
911report/chapter-3.txt
911report/chapter-2.txt
911report/chapter-1.txt
911report/chapter-5.txt
911report/chapter-6.txt
911report/chapter-7.txt
911report/chapter-9.txt
911report/chapter-8.txt
911report/preface.txt
911report/chapter-12.txt
911report/chapter-10.txt
911report/chapter-11.txt
```

* We are showing files in the 911report directory which are MORE THAN (+) 1 kibibyte

### Example #2
Input~
```
technical % find 911report -size +200k
```

Output~
```
911report/chapter-13.4.txt
911report/chapter-13.5.txt
911report/chapter-3.txt
```
* We are showing files in the 911report directory which are MORE THAN (+) 200 kibibytes

### Example #3
Input~
```
technical % find 911report -size -50k
```

Output~
```
911report
911report/preface.txt
911report/chapter-10.txt
```

* We are showing files in the 911report directory which are LESS THAN (-) 50 kibibytes
