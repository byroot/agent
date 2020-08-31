我是光年实验室高级招聘经理。
我在github上访问了你的开源项目，你的代码超赞。你最近有没有在看工作机会，我们在招软件开发工程师，拉钩和BOSS等招聘网站也发布了相关岗位，有公司和职位的详细信息。
我们公司在杭州，业务主要做流量增长，是很多大型互联网公司的流量顾问。公司弹性工作制，福利齐全，发展潜力大，良好的办公环境和学习氛围。
公司官网是http://www.gnlab.com,公司地址是杭州市西湖区古墩路紫金广场B座，若你感兴趣，欢迎与我联系，
电话是0571-88839161，手机号：18668131388，微信号：echo 'bGhsaGxoMTEyNAo='|base64 -D ,静待佳音。如有打扰，还请见谅，祝生活愉快工作顺利。

# Buildkite Agent ![Build status](https://badge.buildkite.com/08e4e12a0a1e478f0994eb1e8d51822c5c74d395.svg?branch=master)

The buildkite-agent is a small, reliable, and cross-platform build runner that makes it easy to run automated builds on your own infrastructure. It’s main responsibilities are polling [buildkite.com](https://buildkite.com/) for work, running build jobs, reporting back the status code and output log of the job, and uploading the job's artifacts.

```
$ buildkite-agent --help
Usage:

  buildkite-agent <command> [arguments...]

Available commands are:

  start		Starts a Buildkite agent
  artifact	Upload/download artifacts from Buildkite jobs
  meta-data	Get/set data from Buildkite jobs
  pipeline	Make changes to the pipeline of the currently running build
  help, h	Shows a list of commands or help for one command

Use "buildkite-agent <command> --help" for more information about a command.
```

## Installing

The agents page on Buildkite has personalised instructions for installing the agent with Ubuntu (via apt), Debian (via apt), Mac OS X (via homebrew), Windows and Linux. You can also run the agent [via Docker](http://hub.docker.com/u/buildkite/agent).

## Starting

To start an agent all you need is your agent token, which you an find on your Agents page within Buildkite.

```
$ buildkite-agent start --token
```

## Development

### With Docker

```bash
$ docker-compose run agent bash
root@d854f845511a:/go/src/github.com/buildkite/agent# go run *.go start --token xxx --debug
```

### Without Docker

```bash
# Make sure you have go installed.
brew install go --cross-compile-common
brew install mercurial

# Setup your GOPATH
export GOPATH="$HOME/Code/go"
export PATH="$HOME/Code/go/bin:$PATH"

# Checkout the code
mkdir -p $GOPATH/src/github.com/buildkite/agent
git clone git@github.com:buildkite/agent.git $GOPATH/src/github.com/buildkite/agent
cd $GOPATH/src/github.com/buildkite/agent
```

To test the commands locally:

```bash
go run *.go start --debug --token "abc123"
```

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

## Copyright

Copyright (c) 2014-2015 Keith Pitt, Buildkite Pty Ltd. See LICENSE for details.
