

# Pipeline Definitions

## job-1

```
pipeline {
    agent any
    stages {
        stage('Hello') {
            steps {
                echo 'this is the echo step'
            }
            post {
                success {
                    echo 'this is the stage post message'
                }
            }
        }
    }
}
```

## job-2

```
pipeline {
    agent any
    stages {
        stage('Hello') {
            steps {
                echo 'this is the echo step'
            }
            post {
                success {
                    echo 'this is the stage post success message'
                }
            }
        }
    }
    post {
        success {
            echo 'this is the overall post success message'
        }
        failure {
            echo 'this is the overall post failure message'
        }
    }
}
```

## job-3

```
pipeline {
    agent any
    stages {
        stage('Hello') {
            steps {
                echo 'this is the echo step'
            }
            post {
                success {
                    echo 'this is the stage post success message'
                }
            }
        }
    }
    post {
        success {
            echo 'this is the overall post success message'
        }
        failure {
            echo 'this is the overall post failure message'
        }
        cleanup {
            echo 'this is the overall post cleanup message'
        }
    }
}
```

## job-4

```
pipeline {
    agent any
    stages {
        stage('Hello') {
            steps {
                sh 'false'
            }
            post {
                success {
                    echo 'this is the stage post success message'
                }
            }
        }
    }
    post {
        success {
            echo 'this is the overall post success message'
        }
        failure {
            echo 'this is the overall post failure message'
        }
        cleanup {
            echo 'this is the overall post cleanup message'
        }
    }
}
```