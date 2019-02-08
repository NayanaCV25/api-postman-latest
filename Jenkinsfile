pipeline {
  agent none
  stages {
    stage('API Testing') {
	  agent { docker 'node:7' }
      steps {
			parallel(
				NewmanAPI: {

					sh '''
						echo "Starting Newman"
						chmod 777 ./ci/scripts/functional-test.sh
						./ci/scripts/functional-test.sh
            sleep 8
					'''

					sh 'echo "Archieving test results..."'
					
					junit 'tests/*.xml'
					sh 'echo "Complete"'

				},
				Notifications: {
					sh 'echo "Notify"'
					sh 'sleep 10'
					
					sh 'sleep 1'
					
					sh 'sleep 1'
					
					sh 'sleep 1'
					
					sh 'sleep 1'
					
					sh 'sleep 1'


				}
			)
		}
    }
  }
}
