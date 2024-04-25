
So your app is now tested and on the registry, what next?

Deployment pipelines are generally triggered at the end of your CI pipeline.

The CD pipeline pushes the image via some mechanism (git push or whatever) to your environment. Generally configured via a yml file.





See also:
- [[Continuous Integration and Deployment]]