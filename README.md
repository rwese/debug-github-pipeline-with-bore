# debug-github-pipeline-with-bore

Goal of this repository is to demonstrate how to use a reverse tunnelling proxy
to debug a github pipeline. This not only applies to github actions but any CI
pipeline that allows to run jobs on failure.

The only _restriction_ which will prevent this is when your network firewall
prevents you from connecting. To get around this issue you can use self-hosted
tunneling proxy. See [bore](https://github.com/ekzhang/bore) for example.

# using the reverse tunnel

```shell
$ nc $BORE_SERVER <remote_port of the listening process>

ls
bore
```

by default the shell is _unstable_, to stabilize the shell you can use the
following command:

```shell
python3 -c 'import pty;pty.spawn("/bin/bash")'
```

(Source: [maxat-akbanov.com](https://maxat-akbanov.com/how-to-stabilize-a-simple-reverse-shell-to-a-fully-interactive-terminal))
