node {
  stage('SCM') {
    git 'https://github.com/Kabi16/It-Works.git'
  }
  stage('Build + SonarQube analysis') {
    def sqScannerMsBuildHome = tool 'Scanner for MSBuild 4.6'
    withSonarQubeEnv('My SonarQube Server') {
      bat "${C:\Users\C605978\.dotnet\tools}\\SonarQube.Scanner.MSBuild.exe begin /k:myKey"
      bat 'MSBuild.exe /t:Rebuild'
      bat "${C:\Users\C605978\.dotnet\tools}\\SonarQube.Scanner.MSBuild.exe end"
    }
  }
}
