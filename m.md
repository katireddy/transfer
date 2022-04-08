Configure Environment Using PowerShell
Instead of updating the PATH variable using the Settings app, you can also configure it using PowerShell. Here is a short script showing how to do so. You’ll need to change the value of $installPath to match where you extracted the Terraform executable back in Step 2. In the example below, the path is C:\terraform# Set $installPath to location of Terraform executable
$installPath = "C:\terraform"
 
# Save current value of PATH
$currentPath = (Get-Item -path "HKCU:\Environment" ).GetValue('Path', '', 'DoNotExpandEnvironmentNames')
 
# Add $installPath to $currentPath, saved as $newPath
$newPath = $currentPath + ";$installPath"
 
# Set PATH environment variable to $newPath value
setx PATH ($newPath)
