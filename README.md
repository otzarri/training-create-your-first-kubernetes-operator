# Training: Create your first Kubernetes operator

Tutorial to learn the basics about creating a Kubernetes operator.


## ❤️ Recognition

Most of the content is copied from the work done by [Abby Bangser](https://hachyderm.io/@abangser) for [this talk](https://www.youtube.com/watch?v=fDkoxrz7BXw):

- The [slides of the talk](https://static.sched.com/hosted_files/kccncna2022/52/Tutorial%20Becoming%20a%20Kubernetes%20Developer_%20Writing%20Your%20First%20Operator.pdf).
- The [online tutorial](https://abangser.gitbook.io/kubecon2022/content/online-tutorial).
- The [instruqt track](https://play.instruqt.com/syntasso/invite/oqyqsyhwlzyi) of the online tutorial.
- The [source code](https://play.instruqt.com/syntasso/invite/oqyqsyhwlzyi) of the instruqt track.

I found this tutorial quite helpful so I wanted to document it here.

As the original work is licensed under the MIT license, I'll use the same [license](LICENSE.md) for this repository.


## 🐾 Tutorial

> 💡 **This tutorial assumes that you have three terminal tabs open:**
  • `K8S Shell`: A terminal to run quick responding commands.
  • `Run Shell`: A terminal to run commands that take long time.
  • `Code editor`: A terminal to edit files. You can use a GUI text editor instead.

This tutorial is divided in several chapters, each of them into a different subdirectory containing:

- The `README.md` file with documentation and exercises.
- The `demo` directory with the source code ready to complete the exercises.

Chapters:

1. [Setup environment](01-setup-environment)
1. [Generate application scaffolding](02-generate-application-scaffolding)
1. [Generate a new operator and custom resource](03-generate-a-new-operator-and-custom-resource)
1. [Install the new crd on kubernetes](04-install-the-new-crd-on-kubernetes)
1. [Understand the new operator by adding logs](05-understand-the-new-operator-by-adding-logs)
1. [Use data defined in the crd within the operator](06-use-data-defined-in-the-crd-within-the-operator)
1. [Deploy your website from the operator](07-deploy-your-website-from-the-operator)
1. [View your website by including a service](08-view-your-website-by-including-a-service)
1. [Gracefully detect an update request](09-gracefully-detect-an-update-request)
1. [Update the deployment when imagetag changes](10-update-the-deployment-when-imagetag-changes)
1. [Delete a website deployment](11-delete-a-website-deployment)
1. [Bonus: Deploy operator to kubernetes](12-bonus-deploy-operator-to-kubernetes)


<hr>
<a href="12-bonus-deploy-operator-to-kubernetes/README.md">⬅️</a> <a href="01-setup-environment/README.md">➡️</a>
