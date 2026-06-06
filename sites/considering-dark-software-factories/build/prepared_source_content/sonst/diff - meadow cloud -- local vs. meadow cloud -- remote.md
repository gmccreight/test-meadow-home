^ diff - [[meadow cloud -- local]] vs. [[meadow cloud -- remote]]

---

### App publish files to cloud object storage

In [[meadow cloud -- local]] we just sync the files directly to [[S3 Local]], AKA [[project - MinIO]]
:
In [[meadow cloud -- remote]] the [[publisher]] sends their [[meadowAPIKey]] to [[Meadow Lambda -- prefix_auth_lambda]] and in AWS, it gets an [[AWS STS - assumed role]], then returns a set of [[AWS access keys]] to the [[meadow app]] that the [[publisher]] uses to publish their site directly to [[AWS S3]] (at [[published site type -- remote html]])

### Serving the meadow site from the cloud

In [[meadow cloud -- local]] we have a [[node http server]] that the [[meadow e2e tests -- runner]] runs, which serves the files from [[project - MinIO]]
:
In [[meadow cloud -- remote]] we have [[AWS Cloudfront]] which fronts [[AWS S3 - bucket -- meadow-notes.com]]