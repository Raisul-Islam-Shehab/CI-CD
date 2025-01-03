pipeline {
    agent none
    stages {
        stage('Build') {
            agent {
                    dockerfile {
                        filename 'Dockerfile.linux'
                        args '-w /'
                    }
                }
            steps {
                sh 'rm -rf ./Jenkinsfile && \
                npm run pack:linux && \
                npm run build:deb && \
                npm run build:deb-checksum'
                }
            }
        }
          stage('Build_Windows') {
            agent {
                    dockerfile {
                        filename 'Dockerfile.windows'
                        args '-u root'
                    }
                }
            steps {
             # Pack the application for Windows
RUN npm run pack:windows

# Download the Inno Setup installer
WORKDIR /app/windows
RUN curl.exe --max-time 30 --retry 3 -L -o innosetup.exe https://files.jrsoftware.org/is/6/innosetup-6.2.0.exe

# Install Inno Setup silently
RUN .\innosetup.exe /SP- /VERYSILENT /SUPPRESSMSGBOXES /NORESTART /NOCANCEL

# Create the Windows installer
WORKDIR /app
RUN npm run build:windows
                }
            }
        }
}
