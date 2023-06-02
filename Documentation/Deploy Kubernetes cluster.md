# Deploying a Kubernetes Cluster

## Oracle Cloud
I already have an account on Oracle cloud with some free services. One of them are the creation of a few virtual machines, therefore I wanted to try to create a Kubernetes cluster on this cloud platform. I knew that I had to create at least a master node and a worker node. I started my journey to search for an article/tutorial about this and came across the following ones in chronological order.

### [How to create an always free K8S cluster in Oracle Cloud](https://medium.com/geekculture/how-to-create-an-always-free-k8s-cluster-in-oracle-cloud-60be3b107c44)
Everything in this article went great until I had to set up multiple ip registrations into the same virtual private network. The article also discussed some resources that were not longer free in my region. Therefore I gave up after a couple of hourt at trying. In addition I looked up other articles that went into the same direction.

### [Setup a Free Kubernetes Cluster on Oracle Cloud](https://faun.pub/free-ha-multi-architecture-kubernetes-cluster-from-oracle-c66b8ce7cc37)
By this one I got a little bit further, but I couldn't get the DNS to work with the platform discussed in the article or ones I found myself. Because it already took a lot of time I decided to look for other ways to deploy and I came across the next article.

### [Free Oracle Cloud Kubernetes Cluster With Terraform](https://arnoldgalovics.com/oracle-cloud-kubernetes-terraform/)
In this article they talked about terraform and after reading further I googled it because it seemed like another approach to try. For this use case terraform seemed great so I gave it a try. The most of it went smoothly when I tried it but then again some resources weren't found and I had little knowledge on how to adjust the configuration to address the right resources. So I started looking for other sources of this terraform files and tried a few [like the one in this repo](https://github.com/eficode/free-k8s-oci-tf). But it was either way an error with the resources, region settings or a setup in terraform. For the last try I wanted to mess around in the terraform file and tried a few things, but eventually I gave up and moved to Google Cloud.

