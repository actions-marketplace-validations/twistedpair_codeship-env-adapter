If you would like to contribute, please submit a PR. If you encounter an
problem, please file an Issue in this repo.

### Releasing

Releases are built on release branches. Each major release version should get
its own branch, e.g. release_v1.  
Releases can then be built from that branch by running

```bash
# Bring changes into relesae branch
git checkout main
git pull
git checkout release_v1
git pull
git merge main

# Compile release
npm run release

# Commit the built release files
git commit -m "<version, e.g. v1.4> release"

# Tag the release
git tag <version, e.g. v1.4>
git push origin <version, e.g. v1.4>

# Update floating tags
git tag --delete v1
git push origin :refs/tags/v1
git tag v1
git push origin v1
```

Once the tag exists, you make a new release from it in the github UI.
