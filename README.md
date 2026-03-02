# Artemis Financial Security Enhancements

## Client Summary
**Artemis Financial** is a consulting company that develops individualized financial plans for its customers, including savings, retirement, investments, and insurance. The company sought to modernize its operations and required a software security enhancement to protect sensitive client data. Specifically, I was tasked with adding a data verification step (a checksum) to their web application to ensure secure data transfer.

## Security Vulnerabilities & Importance of Secure Coding
I effectively pinpointed software security improvements by relying on both manual code reviews and automated static testing (using OWASP Dependency-Check). Coding securely is absolutely critical because vulnerabilities in software can be exploited to steal highly sensitive personal and financial data. For a company like Artemis Financial, robust software security protects their clients' assets, prevents costly data breaches, ensures continuous regulatory compliance, and builds long-term trust—adding immense value to the company's overall well-being and reputation.

## Challenges & Helpful Assessments
The automated static analysis using the **OWASP Dependency-Check** plugin was incredibly helpful. While configuring the plugin and managing the NVD data feeds presented an initial challenge, the resulting HTML report offered a tremendously clear and actionable breakdown of the specific Common Vulnerabilities and Exposures (CVEs) residing in the third-party libraries. This exercise clearly highlighted the often-overlooked risk that outdated dependencies impose on an application.

## Increasing Layers of Security & Future Mitigation
I increased layers of security by implementing a **SHA-256 cryptographic hash** for data verification (ensuring data integrity) and by configuring a self-signed **RSA-2048 certificate to strictly enforce HTTPS** (ensuring secure, encrypted data transport). In the future, I would continue to rely on automated Static Application Security Testing (SAST) tools integrated directly into the CI/CD pipeline, combined with Dynamic Analysis (DAST) and routine manual reviews against OWASP industry standards to dictate mitigation techniques.

## Ensuring Functionality and Security
To guarantee the application remained functional and secure, I compiled the Spring Boot application locally and manually verified the REST endpoint via a web browser to confirm the checksum generated perfectly and that the secure https:// protocol was strictly enforced with no fallback. After refactoring the codebase, I re-ran the OWASP Dependency-Check and conducted a manual code review to verify that my new implementation (utilizing Java's MessageDigest and SSL configurations) did not introduce any hardcoded secrets or logical flaws.

## Helpful Resources & Practices
Throughout this assignment, several tools and practices proved invaluable:
- **OWASP Dependency-Check** for auditing vulnerable third-party libraries.
- The **Java Keytool utility** for generating secure cryptographic keys and certificates.
- The concept of **Defense in Depth**: intelligently layering encryption (HTTPS) on top of data integrity checks (SHA-256 signatures).
These assets and security-first mindsets will definitely be a standard foundation for any future software development tasks I undertake.

## Portfolio Relevance for Employers
If asked by future employers, I would highlight the **Practices for Secure Software Report** (included in this repository). This document serves as concrete proof of my ability to successfully implement industry-standard encryption algorithms, generate and apply SSL certificates to secure web traffic, correctly utilize automated vulnerability scanning tools, and comprehensively document security implementations in a clear, professional manner.
