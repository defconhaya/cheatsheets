### PowerShell Basics:

1. **Running Scripts:**
   ```
   ./script.ps1
   ```

2. **Commenting:**
   ```powershell
   # This is a comment
   ```

3. **Variables:**
   ```powershell
   $variableName = "Hello, World!"
   ```

### Archive Manipulation:

4. **Compress Files/Folders to ZIP:**
   ```powershell
   Compress-Archive -Path C:\Path\To\Files -DestinationPath archive.zip
   ```

5. **Extract ZIP Archive:**
   ```powershell
   Expand-Archive -Path archive.zip -DestinationPath C:\Extracted\Directory
   ```

6. **Create TAR Archive:**
   ```powershell
   tar -cvf archive.tar C:\Path\To\Files
   ```

7. **Extract TAR Archive:**
   ```powershell
   tar -xvf archive.tar -C C:\Extracted\Directory
   ```

### File and Folder Operations:

8. **List Files and Folders:**
   ```powershell
   Get-ChildItem -Path C:\Path\To\Directory
   ```

9. **Copy Files or Folders:**
   ```powershell
   Copy-Item -Path source.txt -Destination destination.txt
   ```

10. **Move or Rename Files/Folders:**
    ```powershell
    Move-Item -Path source.txt -Destination destination.txt
    ```

11. **Delete Files/Folders:**
    ```powershell
    Remove-Item -Path file.txt
    ```

12. **Execute an External Program with Parameters:**
    ```powershell
    Start-Process -FilePath "program.exe" -ArgumentList "-param1 value1 -param2 value2"
    ```

13. **Capture Output of External Program:**
    ```powershell
    $output = Invoke-Expression -Command "program.exe -param1 value1 -param2 value2"
    ```

14. **Parse Text Output:**
    ```powershell
    $parsedOutput = $output | Where-Object { $_ -match "pattern" }
    ```

15. **Display Text Output:**
    ```powershell
    Write-Host "Output: $parsedOutput"
    ```
