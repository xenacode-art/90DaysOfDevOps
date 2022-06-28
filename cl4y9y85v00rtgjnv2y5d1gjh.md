## Best practices for DevSecOps

> In the following subsections, we present suggestions for each of the three most common DevOps stages: build, deploy, and runtime.

Securing containers and Kubernetes often requires multiple teams to collaborate across the application lifecycle. As applications move from dev and test to production runtime environments, new security use cases arise requiring different skill sets and responsibilities. At the build stage, for example, developers are often the primary guardians of security, ensuring that container images adhere to security best practices and catching fixable vulnerabilities early. The runtime phase introduces new attack vectors requiring a different set of security controls, such as identifying anomalous process execution indicative of a breach.
*
To better understand the delineation of security responsibility, we asked survey respondents, "What role at your organization is most responsible for container and Kubernetes security?" Nearly two-thirds of the more than 300 respondents said that it was the role of DevOps (43%) or DevSecOps (19%). DevOps and DevSecOps are both roles that bridge different functions, which further underscores the need to collaborate across teams to properly protect containerized applications in Kubernetes.

The responses show that modern organizations are well along the way to incorporating security into their DevOps pipelines. Only 16% of respondents assign primary responsibility to their security team, another 16% to operations, and 6% to developers.

One surprise finding was how few respondents assign responsibility to the central IT security team for Kubernetes security. One way to explain the low percentage is by looking at what motivates container and Kubernetes adoption. Developers and DevOps teams are often the first to adopt container technologies, limiting them to the dev and test stages. This is done outside the purview of central IT governance (a workaround also known as shadow IT). To bridge the gap between the official security team and the developers, security tooling for container and Kubernetes must facilitate close collaboration among different teams—from developers to DevOps to operators to security—instead of perpetuating team isolation that can plague organizations with slow roll-outs and security vulnerabilities.*


## Build stage

- Here, your goal is to catch issues early so they don't become blockers later in the development life cycle:

-     Use a trusted, enterprise-grade private image registry and limit access.
-     Use minimalist base images.
-     Update base images and their dependencies when new versions are available.
-     Remove exploitable and nonessential software such as:
-         Package managers (apt, yum, apk)
-         Network tools and clients (curl, wget, netcat)
-         Unix shells, compilers, and debuggers
-     Scan the image registry regularly for known operating system, application, and language vulnerabilities.
-     Integrate image scanners with CI tools and build vulnerability awareness early, especially when there are severe policy violations.
-     Follow best practices for sensitive data:
-         Do not use secrets in a risky manner.
-         Do not store secrets unencrypted.
-         Do not use secrets as environmental variables.
-         Understand where and how secrets are being used to remove unnecessary exposure.
-     Make sure that builds break if they exceed the security risk threshold. This would include builds that:
-         Contain high severity, fixable vulnerabilities.
-         Have not been scanned recently, or at all.
-         Contain misconfigurations missed by a scanner, such as identity configurations or environment variables.
## Deploy stage

1. This stage should automate a DevSecOps feedback loop and prioritize remediation:

2.     Combine security-relevant data from the build stage with the deployment configuration to determine the security risk of each deployment, including:
3.         Image vulnerabilities
4.         Access to secrets, storage, etc.
5.         Privileges and capabilities
6.         Workload isolation, network exposure, and blast radius
7.     Use a secrets management tool to protect sensitive data. Assess the privileges used by containers to keep them to a minimum viable set of capabilities.
8.     Avoid deployments without resource limits unless absolutely necessary.
9.     Annotate deployments with the name, email alias, or chat channel of the team responsible for the application.
10.     Block risky deployments and alert the correct team for automated and streamlined remediation.


## Runtime stage

In this stage, the need is to prevent, detect, and contain runtime attacks:

   - Implement dynamic scanning to detect vulnerabilities in running containers.
-     Use behavioral baselining and process allow-listing to identify unusual runtime activity, such as:
-         Privilege escalation
-         Unauthorized network flows
-         Cryptomining
-         Malicious process execution or other exploits
-     Mitigate threats with Kubernetes-native controls:
-         Scaling to zero
-         Killing pods and restarting

## More best practices

> I also recommend the following general practices:
> 
>     Private, internal registries often offer greater security capabilities. Choose a registry that offers advanced access control and built-in vulnerability scanning.
>     Use trusted content. To start with, use resilient, minimalist base images to build your containers.
>     The security of your continuous integration (CI) build infrastructure is as important as your production environment. Implement security as code using CI/CD. Limit administrative access and allow only required network ingress.
> 

##  Conclusion
> 
> Tools such as image scanners and registries can provide governance to projects and detect vulnerabilities. However, reducing risk from misconfigurations (such as when your containers run with root privileges) and runtime incidents requires processes and best practices that implement DevSecOps across the full application life cycle.

Organizations experience security incidents across all phases: build, deploy, and runtime. Implementing and automating DevSecOps provides developer-friendly guardrails that can decrease user error at the build and deploy stages and protect workloads at runtime.