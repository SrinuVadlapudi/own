pipeline {
agent any 
environment {
  Google_key = credentials('terraform-auth')
  }
  stages {  
	stage ('credential') {
	 steps {
	    sh 'mkdir -p creds'
		sh 'echo $Google_key | base64 -d > ./creds/key.json'
		}
		}
   
  stage ('Instance Creating') {
  steps {
//  sh 'gcloud compute instances create instance-001 --zone=asia-northeast2-b'
  sh 'sleep 1'                 
  }
  
  }
  
  stage ('DISK creating') {
  steps {
//   sh 'gcloud compute disks create disk-001 --zone=asia-northeast2-b --type=pd-ssd --size=100'
  sh 'sleep 2'
  }
  }
  
  
  
  stage ('DISK ADDING') {
  steps {
//   sh 'gcloud compute instances attach-disk instance-001 --disk=disk-001 --zone=asia-northeast2-b'
  sh 'sleep 7'
  }
  } 
   stage ('LIST INSTANCES')  {
       steps {
 sh 'gcloud compute instances list'
 sh 'sleep 10'
      }
  }
  stage ('LIST DISKS')  {
       steps {
 sh 'gcloud compute disks list'
 sh 'sleep 10'
      }
  }
 

 
 stage ('DISK REMOVING') {
  steps {
  sh 'gcloud compute instances detach-disk instance-001 --disk=disk-001 --zone=asia-northeast2-b'
  sh 'sleep 7'
  }
  } 
 
 
   stage ('LIST INSTANCES-1')  {
       steps {
  sh 'gcloud compute instances list'
 sh 'sleep 10'
      }
  }
  stage ('LIST DISKS-1')  {
       steps {
  sh 'gcloud compute disks list'
 sh 'sleep 10'
      }
  }
 
  }
}
  
