#!groovy

// 起動メモ
// https://qiita.com/shirasaya0201/items/863a05117c934856e532

// メモ
// https://www.jenkins.io/doc/book/pipeline/syntax/
// https://qiita.com/dublog/items/38831adf42e3cfeed66a
// https://www.baeldung.com/ops/jenkins-pipeline-skip-stage
// https://www.jenkins.io/doc/book/pipeline/shared-libraries/

pipeline {
    agent any
    environment {
        work_dir='/home/jenkins/work'
        bundle='/home/jenkins/bin/bundle'
        deploy_dir='/home/jenkins/deploy'
    }
    parameters {
        booleanParam(name: 'skip_clone', defaultValue: true, description: '')
        booleanParam(name: 'skip_build', defaultValue: true, description: '')
        booleanParam(name: 'skip_idou', defaultValue: true, description: '')
    }
    stages {
        stage('clone') {
            when { expression { params.skip_clone != true } }
            steps {
                echo 'hello world!!'
            }
        }
        stage('build') {
            when { expression { params.skip_build != true } }
            steps {
                // sh 'mvn --version'
                sh 'java --version'
            }
        }
        stage('idou') {
            when { expression { params.skip_idou != true } }
            steps {
                sh 'pwd'
                // 移動する際
                dir('/Users/sugitaku03031/git') {
                    sh 'pwd'
                }
            }
        }
    }
}