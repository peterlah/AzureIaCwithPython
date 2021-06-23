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

# 구성 요소 확인
1. Python --version
2. az --version
3. code . (현재경로에서 vscode 실행)

# 개발을 위한 서비스 주체 및 환경 변수 만들기
az ad sp create-for-rbac --name localtest-sp-rbac --skip-assignment

{
  "appId": "f8c1b62e-a421-408a-9bc9-e5e4fa0f2eed",
  "displayName": "localtest-sp-rbac",
  "name": "http://localtest-sp-rbac",
  "password": "JadqNEiPyXG~feNpiVWJIyY13mqrYitg.q",
  "tenant": "7b79809c-09b9-4baa-ab98-ef8d94c6923f"
}


az account show

{
  "environmentName": "AzureCloud",
  "homeTenantId": "7b79809c-09b9-4baa-ab98-ef8d94c6923f",
  "id": "b136b1b1-2168-4277-b9a1-0bb43e2161d9",
  "isDefault": true,
  "managedByTenants": [
    {
      "tenantId": "2f4a9838-26b7-47ee-be60-ccc1fdec5953"
    }
  ],
  "name": "MPN-SW",
  "state": "Enabled",
  "tenantId": "7b79809c-09b9-4baa-ab98-ef8d94c6923f",
  "user": {
    "name": "peterlah@comasnewbiz.onmicrosoft.com",
    "type": "user"
  }
}

set AZURE_SUBSCRIPTION_ID="b136b1b1-2168-4277-b9a1-0bb43e2161d9"
set AZURE_TENANT_ID=7b79809c-09b9-4baa-ab98-ef8d94c6923f
set AZURE_CLIENT_ID=1f735860-55b9-435c-891b-4ee2abe1ce45
set AZURE_CLIENT_SECRET=4r_ZnV3YYLa1~-Kyb~_7j-zmFt6hwjL.YD

참고 > https://docs.microsoft.com/ko-kr/azure/active-directory/develop/howto-create-service-principal-portal

