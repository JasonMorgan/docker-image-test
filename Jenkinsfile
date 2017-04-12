node("docker") {
    docker.withRegistry('http://172.17.0.3:5000') {

        git url: "https://github.com/JasonMorgan/docker-image-test.git"

        sh "git rev-parse HEAD > .git/commit-id"
        def commit_id = readFile('.git/commit-id').trim()
        println commit_id

        stage "build"
        def app = docker.build "your-project-name"

        stage "publish"
        app.push 'master'
        app.push "${commit_id}"
    }
}