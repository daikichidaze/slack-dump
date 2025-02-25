# slack-dump
Generate an export of Channel, Private Group and / or Direct Message history and export it as a ZIP file compatible with Slack's import tool.

## Token

1. Visit https://api.slack.com/
2. Click "Create an app"
3. Select "From scratch"
4. Input App Name and pick a workspace
5. Click "Features" → "OAuth & Permissions" of sidebar
6. Go to "Scopes" and set **User Token** Scopes as follows

* channels:read
* channels:history
* groups:read
* groups:history
* im:read
* im:history
* mpim:read
* mpim:history
* users:read

7. Go to "OAuth Tokens for Your Workspace" and click "Install to Workspace"
8. Accept
9. OAuth Token is displayed in "OAuth Tokens for Your Workspace"

## Usage

```
$ slack-dump -h

NAME:
   slack-dump - export channel and group history to the Slack export format include Direct message

USAGE:
   main [global options] command [command options] [arguments...]

VERSION:
   1.3.0

AUTHORS:
   Joe Fitzgerald <jfitzgerald@pivotal.io>
   Sunyong Lim <dicebattle@gmail.com>
   Yoshihiro Misawa <myoshi321go@gmail.com>
   takameron <tech@takameron.info>

COMMANDS:
   help, h  Shows a list of commands or help for one command

GLOBAL OPTIONS:
   --token value, -t value   a Slack API token: (see: https://api.slack.com/apis) [$SLACK_API_TOKEN]
   --output value, -o value  Output directory path. Default: current directory path [$]
   --help, -h                show help (default: false)
   --version, -v             print the version (default: false)

```

### Export All Channels And Private Groups

```
$ slack-dump -t=YOURSLACKAPITOKENISHERE
```

### Export Specific Channels And Private Groups

```
$ slack-dump -t=YOURSLACKAPITOKENISHERE channel-name-here privategroup-name-here another-privategroup-name-here
```
