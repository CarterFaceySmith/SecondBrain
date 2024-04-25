
## Source Stage
- Getting code form code repository
- Ensure you have branch protection rules (e.g. you have to have PR reviewed to be able to push to main)
- Linting check, runs through and checks code for syntax errors

## Pre-commit
- Run checks prior to source stage

## Build Stage
- Compiles code
- Builds images if using things like [[Docker]]
	- Then runs unit tests
	- Code coverage checks (Checking to ensure devs are writing tests that test a certain percentage of the codebase)

## Test Stage
- Runs integration tests (Testing functionality of the application, i.e. tasks users would do)

## Release Stage
- Ships image to registry, now other environments can start pulling and running your app

Now go read [[Designing CD Pipelines]] for the next step.


See also:
- [[Continuous Integration and Deployment]]