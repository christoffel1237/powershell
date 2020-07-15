# powershell

#This is a test to put Powershell code on Github.

Add-Type -AssemblyName System.IO.Compression.FileSystem

$url = "https://github.com/linuxacademy/content-azure-labs/blob/master/zips/Azure-LearningActivity-CfgSecMon.zip?raw=true"
$zipfile = "C:\Users\azureuser\Desktop\Azure-LearningActivity-CfgSecMon.zip"
$folder = "C:\Users\azureuser\Desktop\images"

[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
Invoke-WebRequest -UseBasicParsing -OutFile $zipfile $url 

[System.IO.Compression.ZipFile]::ExtractToDirectory($zipfile, $folder)

Remove-Item -Path $zipfile 
