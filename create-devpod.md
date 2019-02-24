# Create a DevPod

A DevPod allows you to develop in a K8s pod running in the same cluster where Jenkins X is running. DevPods allow you to build and test your Jenkins X application before you are ready to create a Pull Request - all without installing any developer tools on your computer. 

DevPods provide terminal/shell that is based on the exact same operating system, docker containers and tools that are installed in the pod templates used in the Jenkins X CI/CD pipelines. This allows you to build, run tests or redeploy apps using the exact same tools as the CI/CD pipelines and before you commit to git.

Before creating a DevPod you want to be in the source code repository for which you want to makie changes: `cd ./{GitHub username}-go-http` 

To create your own DevPod use the command [`jx create devpod`](https://jenkins-x.io/commands/jx_create_devpod/). Run the `jx create devpod` command to get a list of all available DevPods. Once you have reviewed the list cancel with `ctrl+c`.

For the workshop we want to create a simple http Golang project with the following command where the `-l go` - but make sure you are in your quickstart repository directory that you created in the previous exercise:
```
jx create devpod -l go --username='[your GitHub username]'
```

This will then create a new DevPod based on the `go` based pod template and open your terminal inside that pod. You are now free to use the various pre-installed tools like git, docker, go, skaffold, jx which will all be using the same exact configuration as the automated Jenkins X CI/CD pipelines.
