#
#
#	The script is used to set TimeZone to EST and Schedule system restart On Sunday at 3AM
#
#

# Delete Task, if already scheduled.  
Unregister-ScheduledTask -TaskName "Auto Restart @ 3AM EST -- Logan" -Confirm:$false

#	----------------------------------------------------------------------------------------------------------------------------------
# Set TimeZone to Eastern
# 
Start-Service w32time

Set-TimeZone -Id "Eastern Standard Time"

Write-Host -BackgroundColor Black -ForegroundColor Green "---------------------------------------------------------------"
Write-Host -BackgroundColor Black -ForegroundColor Green "---------------------Time Zone set to EST---------------------"
Write-Host -BackgroundColor Black -ForegroundColor Green "---------------------------------------------------------------"

W32tm /resync /force
Restart-Service w32time

#	----------------------------------------------------------------------------------------------------------------------------------
#	A scheduled task action represents a command that a task executes when Task Scheduler runs the task. 
#	You can use a task action definition to register a new scheduled task or update an existing task registration.
#	A task can have a single action or a maximum of 32 actions. 
#	When you specify multiple actions, Task Scheduler executes the actions sequentially. 
#	The Task Scheduler service controls tasks activation, and it hosts the tasks that it starts.
#
#	https://docs.microsoft.com/en-us/powershell/module/scheduledtasks/new-scheduledtaskaction?view=win10-ps

$action = New-ScheduledTaskAction -Execute 'Powershell.exe' -Argument '-NoProfile -WindowStyle Hidden -command "& {Restart-Computer -Force}"'

#	----------------------------------------------------------------------------------------------------------------------------------
#	 You can use a time-based trigger or an event-based trigger to start a task. 
#	Time-based triggers include starting a task at a specific time or starting a task multiple times on a daily or weekly schedule. 
#
#	https://docs.microsoft.com/en-us/powershell/module/scheduledtasks/new-scheduledtasktrigger?view=win10-ps

$trigger = New-ScheduledTaskTrigger -Weekly -DaysOfWeek Sunday -At 3am

#	----------------------------------------------------------------------------------------------------------------------------------
#	Use a scheduled task principal to run a task under the security context of a specified account.
#	When you use a scheduled task principal, Task Scheduler can run the task regardless of whether that account is logged on.
#
#	https://docs.microsoft.com/en-us/powershell/module/scheduledtasks/new-scheduledtaskprincipal?view=win10-ps

$principal = New-ScheduledTaskPrincipal -UserID "NT AUTHORITY\SYSTEM" -LogonType ServiceAccount -RunLevel Highest

#	----------------------------------------------------------------------------------------------------------------------------------
#	The New-ScheduledTaskSettingsSet cmdlet creates an object that contains scheduled task settings. 
#	Each scheduled task has one set of task settings.
#		Use this cmdlet to configure options to manage the behavior of the task upon completion, 
#			to manage the behavior of the task if a problem occurs, 
#				or to manage the behavior of the task if an instance of the task is already running.
#
#	https://docs.microsoft.com/en-us/powershell/module/scheduledtasks/new-scheduledtasksettingsset?view=win10-ps

$settings = New-ScheduledTaskSettingsSet -MultipleInstances Parallel

#	----------------------------------------------------------------------------------------------------------------------------------
#	Registers a scheduled task definition on a local computer.
#
#	https://docs.microsoft.com/en-us/powershell/module/scheduledtasks/register-scheduledtask?view=win10-ps

Register-ScheduledTask -TaskName "Auto Restart @ 3AM EST -- Logan" -Action $action -Trigger $trigger -Settings $settings -Principal $principal -TaskPath "\Logan"
