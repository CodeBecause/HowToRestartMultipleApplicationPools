# HowToRestartMultipleApplicationPools

Define the List of Application Pool Names:

$appPoolNames = @("AppPool1", "AppPool2", "AppPool3")
This line defines an array $appPoolNames containing the names of the application pools you want to restart.
Replace "AppPool1", "AppPool2", and "AppPool3" with the actual names of your application pools.
Import the WebAdministration Module:

Import-Module WebAdministration
This imports the WebAdministration module, which provides the necessary cmdlets for managing IIS.
Iterate Over Each Application Pool Name:

foreach ($appPoolName in $appPoolNames) {
    # Logic to stop and start the application pool
}
The foreach loop iterates over each application pool name in the $appPoolNames array.
Inside the loop, the script stops and then starts each application pool.
Stop and Start the Application Pool:

Stop-WebAppPool -Name $appPoolName
Write-Output "Application pool '$appPoolName' stopped."

Start-WebAppPool -Name $appPoolName
Write-Output "Application pool '$appPoolName' started."
Stop-WebAppPool stops the current application pool.
Start-WebAppPool starts the current application pool.
Write-Output provides feedback on the status of each application pool.
Error Handling:

catch {
    Write-Output "Failed to restart application pool '$appPoolName': $_"
}
If an error occurs while stopping or starting an application pool, the catch block captures the error and outputs a message indicating the failure.
Final Output:

Write-Output "All specified application pools have been restarted."
After the loop completes, the script outputs a message indicating that all specified application pools have been restarted.
Steps to Save and Run the Script:
Save the Script:

Save the script as RestartMultipleAppPools.ps1.
Run the Script:

Open PowerShell with administrative privileges.
Navigate to the directory where the script is saved.
Execute the script by typing .\RestartMultipleAppPools.ps1.
This script will sequentially stop and start each application pool listed in $appPoolNames. It will also provide output messages to inform you of the status of each operation.
