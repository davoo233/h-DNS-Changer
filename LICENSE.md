
        ═══════════════════════════════════════════════════════════════
        CODE SIGNING INSTRUCTIONS
        ═══════════════════════════════════════════════════════════════
        
        Step 1: Obtain a Code Signing Certificate
        - Purchase from: DigiCert, Sectigo, GlobalSign
        - Cost: $200-400/year
        - Type: Code Signing Certificate (not SSL)
        
        Step 2: Install Windows SDK
        - Download from: https://developer.microsoft.com/windows/downloads/windows-sdk/
        - SignTool.exe is required
        
        Step 3: Sign the Executable
        signtool sign /f "path\to\certificate.pfx" ^
            /p YOUR_PASSWORD ^
            /tr http://timestamp.digicert.com ^
            /td sha256 ^
            /fd sha256 ^
            "h/DNS.exe"
        
        Step 4: Verify the Signature
        signtool verify /pa /all "h/DNS.exe"
        
        ═══════════════════════════════════════════════════════════════
