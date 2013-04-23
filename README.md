# Go Buildpack

This is a [Heroku buildpack][buildpack]'s fork for [Go][go].

## Getting Started

Follow the guide at
<http://mmcgrana.github.com/2012/09/getting-started-with-go-on-heroku.html>.

There's also a hello world sample app at
<https://github.com/kr/go-heroku-example>.

## Example

```
$ ls -A1
./.git
./.godir
./Procfile
./web.go

$ cctrlapp APP_NAME create custom --buildpack https://github.com/fern4lvarez/buildpack-go.git
...

$ cctrlapp APP_NAME/default push
...
-----> Receiving push
-----> Custom buildpack provided
-----> Installing Go 1.0.3... done
-----> Running: go get -tags cctrl ./...
-----> Building image
-----> Uploading image (1.1M)


$ cctrlapp APP_NAME/default deploy
```


The buildpack will detect your repository as Go if it
contains a `.go` file.

## Hacking on this Buildpack

To change this buildpack, fork it on GitHub. Push
changes to your fork, then create a test app with
`--buildpack YOUR_GITHUB_GIT_URL` and push to it.

[go]: http://golang.org/
[buildpack]: http://devcenter.heroku.com/articles/buildpacks
[quickstart]: http://mmcgrana.github.com/2012/09/getting-started-with-go-on-heroku.html
[build-constraint]: http://golang.org/pkg/go/build/
[app-engine-build-constraints]: http://blog.golang.org/2013/01/the-app-engine-sdk-and-workspaces-gopath.html
