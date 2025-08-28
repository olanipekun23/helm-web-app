pipeline {
  agent any

  environment {
    RELEASE   = 'my-webapp'
    NAMESPACE = 'default'
    CHART_DIR = 'webapp'
    HELM      = '/usr/local/bin/helm'  // <-- replace with your actual helm path
  }

  options { timestamps() }

  stages {
    stage('Checkout') {
      steps { checkout scm }
    }

    stage('Set kube context') {
      steps {
        withCredentials([file(credentialsId: 'kubeconfig', variable: 'KCFG')]) {
          sh '''
            mkdir -p $WORKSPACE/.kube
            cp "$KCFG" $WORKSPACE/.kube/config
            export KUBECONFIG=$WORKSPACE/.kube/config
            kubectl config current-context
            kubectl get ns
          '''
        }
      }
    }

    stage('Deploy with Helm') {
      steps {
        sh '''
          export KUBECONFIG=$WORKSPACE/.kube/config
          ${HELM} version
          ${HELM} lint ${CHART_DIR}
          ${HELM} template ${RELEASE} ${CHART_DIR} --namespace ${NAMESPACE} > helm-render.yaml
          ${HELM} upgrade --install ${RELEASE} ${CHART_DIR} --namespace ${NAMESPACE} --create-namespace
          ${HELM} status ${RELEASE} --namespace ${NAMESPACE}
        '''
      }
    }
  }

  post {
    always {
      archiveArtifacts artifacts: 'helm-render.yaml', allowEmptyArchive: true
    }
  }
}

