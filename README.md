# PowerShell_Scripts
# Get the path of the file
$file_path = "C:\Users\abina\OneDrive\Desktop\roughnote.txt"

# Read the content of the file
$content = Get-Content $file_path

# Split each line into words with *
foreach ($line in $content) {
    if ($line -match "\*(.+)$") {
        $words = $Matches[1]
        Write-Output $words
    }
}
