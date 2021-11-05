`
⎨ ❣️«💕   Ḻʸⁿˢᴱi  ❤🖤🔥» ⎬ ⏅sy⟗⦅ Environment for Multiple SHells ‣ ✨.

8""""8                           8""""8
8      e   e eeee e     e        8      e   e e  eeeee
8eeeee 8   8 8    8     8        8eeeee 8   8 8  8   8
    88 8eee8 8eee 8e    8e           88 8eee8 8e 8eee8
e   88 88  8 88   88    88       e   88 88  8 88 88
8eee88 88  8 88ee 88eee 88eee    8eee88 88  8 88 88    by Ḻʸⁿˢᴱi
`

# docker-compose
It is the same old docker-compose, except now you are in a docker container.
So basically it's docker-in-docker, just with compose too!


### usage instructions

Use it how you normally would go about things.  Mostly this is great for testing
inside a container, on a CI/CD provider for VCS such as Gitlab, or in a containerized workflow
for CI such as CirclCI (whom I personally won't use, but that's just out of principle).

```yaml
tests:
  stage: test
  image: stackops/dindc:1.0.0
  script:
    - docker-compose -f docker-compose.test.yml up --build -d 
    - echo "Run Commands Here"
  after_script:
    - docker-compose -f docker-compose.test.yml down
```

