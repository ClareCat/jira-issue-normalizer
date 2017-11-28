# jira-issue-normalizer

Normalizes JIRA labels on issues in a project.

## Motivation

JIRA labels are case sensitive, meaning "my-label" and "my-LaBeL" are two different labels.
This is dumb.
`jira-issue-normalizer` combs through the labels in a project and does its best to standardize labels to their downcased and dash-separated forms ("my-label" is preferred over "mylabel", and "my-long-label" is preferred over "mylong-label" or "my-longlabel").

## How to Run This

### Setup Go

If you don't have Go installed and setup on your system, you'll need to do that first.
Follow instructions at [golang.org](https://golang.org).

### Running from binary

First, use `go` to install it (make sure `$GOPATH/bin` is in your $PATH):

```bash
$ go install github.com/ajm188/jira-issue-normalizer
```

Then just:

```bash
$ jira-issue-normalizer --jira-url <my-jira> --auth-file <path-to-creds> my-project
```

### Running from source

#### Install Glide

[Glide](https://glide.sh) is a package manager for Go.
You can install it via the instructions on their site, but I prefer using the built-in go tooling.
Simply `go install github.com/Masterminds/glide` and ensure that `$GOPATH/bin/` is in your $PATH, and you're good to go.

#### Install dependencies

```bash
$ glide install
```

#### Running

After completing the above, running is as simple as:

```bash
$ go build .
$ ./jira-issue-normalizer --jira-url <my-jira> --auth-file <path-to-creds> my-project
```

### Usage

For usage and a description of the various options, see `--help`.
