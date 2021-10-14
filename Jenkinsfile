node {
    
   stage('Build') {
       try {
           script {
               currentBuild.result = 'SUCCESS'
           } 
        } catch(err) {
                 
        }  finally {
           def currentResult = currentBuild.result
           echo "always code is executed"
           if(currentbuild.previousBuild != null) {
                def previousResult = currentBuild.previousBuild.result
                if (previousResult != null && previousResult != currentResult) {
                   echo 'changed() code is executed'                                                       
                }
            }
            
            if(currentBuild.previousBuild != null) {
            	def previousResult = currentBuild.previousBuild.result 
            	if(previousResult !=null && (previousResult == 'FAILURE'
            	                             || previousResult == 'UNSTABLE' || previousResult == 'ABORTED')
            	                         && currentResult == 'SUCCESS') {
                                    
            	    echo 'fixed() is executed'
                }
                                     
            }


        }      
   }
   
   stage('Deploy') {
       echo 'This is Deploy stage'
   }
}
