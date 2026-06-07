^ diff - [[meadow cloud -- local]] vs. <span class="link-not-tracked">link not tracked</span>

---

### App publish files to cloud object storage

In [[meadow cloud -- local]] we just sync the files directly to [[S3 Local]], AKA [[project - MinIO]]
:
In <span class="link-not-tracked">link not tracked</span> the [[publisher]] sends their <span class="link-not-tracked">link not tracked</span> to <span class="link-not-tracked">link not tracked</span> and in AWS, it gets an [[AWS STS - assumed role]], then returns a set of <span class="link-not-tracked">link not tracked</span> to the <span class="link-not-tracked">link not tracked</span> that the [[publisher]] uses to publish their site directly to <span class="link-not-tracked">link not tracked</span> (at <span class="link-not-tracked">link not tracked</span>)

### Serving the meadow site from the cloud

In [[meadow cloud -- local]] we have a <span class="link-not-tracked">link not tracked</span> that the <span class="link-not-tracked">link not tracked</span> runs, which serves the files from [[project - MinIO]]
:
In <span class="link-not-tracked">link not tracked</span> we have <span class="link-not-tracked">link not tracked</span> which fronts <span class="link-not-tracked">link not tracked</span>