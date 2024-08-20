node {
    def mvnHome
    stage('Preparation') { // for display purposes
        // Get some code from a GitHub repository
        git 'https://github.com/deftdeft2000/DGB'
        // Get the Maven tool.
        // ** NOTE: This 'M3' Maven tool must be configured
        // **       in the global configuration.
        mvnHome = tool 'M3'
}
    stage('Build') {
        bat """
          java -Xms512m -Xmx1024m \
          -Djava.security.egd="file:/dev/./urandom" \
          -Djavax.net.debug=ssl,handshake \
          -jar "C:\\Program Files\\cxflow\\cx-flow-1.7.03.jar" --spring.config.location=./application.yml \
          --scan \
          --cx-project="cx-demo-webgoat" \
          --app="cx-demo-webgoat-master" \
          --branch="master" \
          --repo-name="cx-demo-webgoat" \
          --namespace="security" \
          --cx-flow.break-build="true" \
          --f=.
         """
    }
}
