# Nomad Musl Builds

Since Hashicorp does not provide non-enterprise musl binaries for their software
Nomad, I have decided to create a repository (that contains no source code) to
build musl binaries of the latest tag automatically using GitHub CI workflows.
This works by first fetching the latest tag information using GitHub's API, then
checking if there is already a cached binary for `linux_amd64-$TAG`, if there is
not already a binary for that key, it will then use an Alpine Linux container to
build the binary and then upload the zip file produced to a new GitHub release.

## License

While this repository is under the Unlicense, the artifacts produced however are
under Hashicorp's [BSL](https://github.com/hashicorp/nomad/blob/main/LICENSE)
license.
