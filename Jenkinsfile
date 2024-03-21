/**
 * Licensed to the Apache Software Foundation (ASF) under one
 * or more contributor license agreements.  See the NOTICE file
 * distributed with this work for additional information
 * regarding copyright ownership.  The ASF licenses this file
 * to you under the Apache License, Version 2.0 (the
 * "License"); you may not use this file except in compliance
 * with the License.  You may obtain a copy of the License at
 *
 *   http://www.apache.org/licenses/LICENSE-2.0
 *
 * Unless required by applicable law or agreed to in writing,
 * software distributed under the License is distributed on an
 * "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
 * KIND, either express or implied.  See the License for the
 * specific language governing permissions and limitations
 * under the License.
 */

pipeline {
    agent any 
    tools {
         maven 'maven'
         jdk 'java'
    }
    stages {
         stage('Stage-0 : Static Code Analysis Using SonarQube') { 
           steps {
                sh 'mvn clean verify sonar:sonar -DskipTests'
            }
        }
        stage('Stage-1 : Clean') { 
            steps {
                sh 'mvn clean'
            }
        }
         stage('Stage-2 : Validate') { 
            steps {
                sh 'mvn validate'
            }
        }
         stage('Stage-3 : Compile') { 
            steps {
                sh 'mvn compile'
            }
        }
         stage('Stage-4 : Test') { 
            steps {
                sh 'mvn test'
            }
        }
          stage('Stage-5 : Package') { 
            steps {
                sh 'mvn install'
            }
        }
          stage('Stage-6 : Verify') { 
            steps {
                sh 'mvn verify'
            }
        }
          stage('Stage-7 : Install') { 
            steps {
                sh 'mvn package'
            }
        }
    }
}

