# FinalDevTools

[การออกแบบและวางแผนการทำงาน](https://github.com/Yannawut62070051/FinalDevTools62070051/wiki/%E0%B8%81%E0%B8%B2%E0%B8%A3%E0%B8%AD%E0%B8%AD%E0%B8%81%E0%B9%81%E0%B8%9A%E0%B8%9A%E0%B9%81%E0%B8%A5%E0%B8%B0%E0%B8%A7%E0%B8%B2%E0%B8%87%E0%B9%81%E0%B8%9C%E0%B8%99%E0%B8%81%E0%B8%B2%E0%B8%A3%E0%B8%97%E0%B8%B3%E0%B8%87%E0%B8%B2%E0%B8%99)

ทดสอบการใช้งาน API ด้วย postman
methods ``GET``
```http://localhost:3013/class/all```

เขียน Dockerfile + Dockercompose มาแล้วแต่ไม่ผ่านครับ


Jenkins pipeline 

## Frontend

### Pull Code
```
pipeline {
    agent any

    stages {
        stage('Pull Code') {
            steps {
                git branch: 'main', url: 'https://github.com/konlawatit/SWDEV-BBP-PLUS'
            }
        }
```
 * Stage 1 ทำการดึง Code มาจาก Branch `main` ของโปรเจค

### Download dependency
```
     stage('Download dependency') {
            steps {
                sh 'cd frontend && npm install'
            }
        }
```
 * Stage 2 ทำการดาวน์โหลดและติดตั้ง Dependency ต่าง ๆ ของตัวโปรเจค โดยใช้คำสั่ง `cd frontend && npm install`

### Build
```
     stage('Build') {
            steps {
                sh 'cd frontend && npm run build'
            }
        }
```
 * Stage 3 ทำการ Build โปรเจคโดยใช้คำสั่ง `cd frontend && npm run build`
### Deployment
```
      stage('Deployment') {
            steps {
                echo '---------------------------- Deployment ----------------------------'
                // sh ''
            }
        }
    }
}
```
 * Stage 4 ทำการ Deploy โปรเจค
