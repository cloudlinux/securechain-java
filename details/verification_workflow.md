# SecureChain Java Library Verification Workflow

## Background

In the evolving landscape of application development, reliance on third-party and open-source libraries has become the norm rather than the exception. With each direct package bringing in an average of 77 transitive dependencies, security concerns are increasingly significant. Among the pressing challenges in software supply chain security is the risk of various types of attacks, such as Dependency Confusion, Typosquatting, and Malicious Updates. Our solution aims to mitigate these risks in the following ways:

-   **Malicious Updates**: By offering libraries that are frozen in secure versions, and updated only after thorough security reviews, we help you avoid automatically incorporating updates that might introduce vulnerabilities.
-   **Dependency Confusion**: We combat the risk of your dependency resolver being tricked into using rogue libraries by maintaining a repository of vetted, secure libraries that are clearly named and segregated.
-   **Typosquatting**: Our vetted repository lessens the chance of developers accidentally downloading libraries with names that closely resemble well-known packages but are malicious.
-   **Insecure Transitive Dependencies**: Our in-depth vetting process includes not just top-level packages but also their multiple layers of dependencies, thus providing a robust layer of security against hidden vulnerabilities.
-   **Code Tampering**: Our secure, signed libraries minimize the risk of code alterations after vetting but before your application incorporates them.

## The Process of Preparing Trusted Artifactory

To create a secure and trusted source of Java libraries for your application, we have instituted a rigorous vetting process. This multi-tiered approach combines static code analyzers with human and AI-based code reviews. Upon successful security validation, libraries are incorporated into our secure repository. Each library is then packaged with a Software Bill of Materials (SBOM) and signed JAR files for additional assurance.

**Note**: Our focus is on vetting for security, and we don't modify the original code to fix known vulnerabilities. This ensures the integrity of the libraries, making our repository a robust line of defense against dependency confusion attacks.

The accompanying graph outlines the steps involved in our vetting process, providing a visual guide to how we ensure the safety and reliability of each library in our Trusted Artifactory.

![image.png](/images/vetting_flow.png)

### How is the Service Delivered?

We offer access to a Nexus repository stocked with vetted libraries. This service is designed to be either complimentary or available for a minimal fee. Given that some clients necessitate sourcing third-party libraries exclusively from trusted providers, we posit that our repository can fulfill this need as a reliable source for secure open-source components.

          
