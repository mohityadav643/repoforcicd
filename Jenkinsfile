pipeline
{
    agent any
    stages
    {
        stage('clone repository')
        {
            steps
            {
               git url: 'https://github.com/mohityadav643/repoforcicd.git', branch: 'master'

            }
        }
        stage('build and deploy')
        {
            steps
            {
                script
                {
                    bat 'docker-compose down || true'
                    bat 'docker-compose pull'
                    bat 'docker-compose up -d'
                }
            }
        }
    }
    post
    {
        always
        {
            echo 'pipeline finished successfully'
        }
    }
}