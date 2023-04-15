###powershell script where we can check each line and split words with a seperator as *  in a paragraph of 5 lines and gives output only those words which are after * of that line
## Using regular Expression
```powershell
Get the path of the file
$file_path = "C:\Users\abina\OneDrive\Desktop\roughnote.txt"

Read the content of the file
$content = Get-Content $file_path

Split each line into words with *
foreach ($line in $content) {
    if ($line -match "\*(.+)$") {
        $words = $Matches[1]
        Write-Output $words
    }
}
```
## with out using regular Expression
```powershell
# Get the path of the file
$file_path = "C:\Users\abina\OneDrive\Desktop\roughnote.txt"

# Read the content of the file
$content = Get-Content $file_path

# Split each line into words with *
foreach ($line in $content) {
    $words = $line.Split('*')
    if ($words.Length -gt 1) {
        $output_words = $words[1..($words.Length-1)]
        Write-Output $output_words
    }
}
```