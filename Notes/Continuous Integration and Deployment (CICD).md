## A Review: The Principles of Software Delivery

- Automate almost everything
- Keep everything in version control
- If it hurts, do it more frequently, and bring the pain forward
- Done means release
- Continous improvement

## Continuous Integration

### Things We Do Before We Commence
1. Double check we have everything in version control, incl. tests
2. [[Build Systems]]
3. Agreement of the team

### A Continuous Integration System
1. Check if build is running, if so wait until finish
2. Once tests have passed, update code in dev environment to get updates
3. Run build script and tests on dev machine to double check
4. If local build passes, check code into version control
5. Wait for CI tool to run the build with changes
6. It fails, stop and fix problem on dev machine then go to step 3
7. If passes, move on to next task

## Deployment Pipeline

![[Pasted image 20220809160757.png]]


See also:
[[Extreme Programming Development Practices]]
