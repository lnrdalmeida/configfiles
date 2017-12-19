node {
    try {
        stage("Git Checkout/Pull") {
            git branch: master,
            credentialsId: '8749ee32-2f72-4c77-a6c5-c916d0115132',
            url: "git@github.com:lnrdalmeida/configfiles.git"
        }

        stage("print variables") {
	    def config = new JsonSlurper().parse(new File("config.json")
	    print(config)
        }

    } catch (e) {
        currentBuild.result = "FAILED"
        throw e
    } finally {
        //notifyBuild(currentBuild.result)
    }
}

