[![Pub Package](https://img.shields.io/pub/v/dhttpd.svg)](https://pub.dev/packages/dhttpd)
[![CI](https://github.com/kevmoo/dhttp/workflows/CI/badge.svg?branch=master)](https://github.com/kevmoo/dhttp/actions?query=workflow%3ACI+branch%3Amaster)

A simple HTTP(s) server that can serve up any directory, built with Dart.
Inspired by `python -m SimpleHTTPServer`.

## Install

Use the `pub global` command to install this into your system.

```console
$ pub global activate dhttpd
```

## Use

If you have [modified your PATH][path], you can run this server from any
local directory.

```console
$ dhttpd
```

Otherwise you can use the `pub global` command.

```console
$ pub global run dhttpd
```

Here's an example of creating a web app with [Stagehand](https://pub.dev/packages/stagehand)
and then running it with this server:

```console
$ stagehand web-angular
$ pub get
$ pub build
$ dhttpd --path build/web/  # Serves app at http://localhost:8080
```

## Configure

```console
$ dhttpd --help
-p, --port=<port>    The port to listen on.
                     (defaults to "8080")
    --path=<path>    The path to serve. If not set, the current directory is used.
    --cert=<cert>    The certificate to use.
                     If not set, https will not be used.
                     See the dart documentation about SecurityContext.useCertificateChain for more.
    --key=<key>      The key of the certificate to use.
                     If not set, https will not be used.
                     See the dart documentation about SecurityContext.usePrivateKey for more.
    --host=<host>    The hostname to listen on.
                     (defaults to "localhost")
-h, --help           Displays the help.
```
[path]: https://dart.dev/tools/pub/cmd/pub-global#running-a-script-from-your-path
