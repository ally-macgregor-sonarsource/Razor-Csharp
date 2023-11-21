node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def scannerHome = tool 'SonarScanner for MSBuild'
    withSonarQubeEnv() {
      bat "dotnet ${scannerHome}\\SonarScanner.MSBuild.dll begin /k:\"ally-macgregor-sonarsource_Razor-Csharp_AYvzfYXfO8HlseoPVxAl\""
      bat "dotnet build"
      bat "dotnet ${scannerHome}\\SonarScanner.MSBuild.dll end"
    }
  }
}

