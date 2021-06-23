# Azure CLI 설치
<파워쉘>
Invoke-WebRequest -Uri https://aka.ms/installazurecliwindows -OutFile .\AzureCLI.msi; Start-Process msiexec.exe -Wait -ArgumentList '/I AzureCLI.msi /quiet'; rm .\AzureCLI.msi

# azure CLI 실행
az login

# 권장 구성 요소 설치
1. Visual Studio Code 설치
2. VS Code용 Python 확장 설치
3. VS Code용 Azure 확장 설치
4. git 설치(소스트리 설치로 대체함)