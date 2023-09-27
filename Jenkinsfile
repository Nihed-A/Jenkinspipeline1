pipeline {
 agent any
   stages{
       stage('Extract_Readme_Content'){
         steps{ 
           script{
             def readmeContent = sh(script: 'cat README.txt', returnStdout: true).trim()
             env.README_CONTENT = readmeContent
             }
              }
       }

       stage('Send_Content_Via_Email'){
         steps{ 
           script{
                 // Send an email with the README content from the environment variable
                    emailext(
                        subject: 'README Content',
                        body: env.README_CONTENT,
                        to: 'nihed.attia@esprit.tn',
                        mimeType: 'text/plain'
                    )
           }
            }
    }

}
}
