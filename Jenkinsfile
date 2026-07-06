pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                // GitHub에서 코드를 가져옴
                checkout scm
            }
        }
        stage('Deploy') {
            steps {
                echo '웹 파일을 Tomcat 서버로 복사합니다...'
                // 1. 기존 폴더 삭제 (필요 시)
                // 2. 소스 파일을 Tomcat의 webapps 경로로 복사
                bat '''
                    if exist "D:\\Tomcat\\webapps\\my-web" (
                        rmdir /s /q "D:\\Tomcat\\webapps\\my-web"
                    )
                    xcopy /s /y /e /i "%WORKSPACE%" "D:\\Tomcat\\webapps\\my-web"
                '''
            }
        }
    }
}
