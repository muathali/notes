# Mac OS

## Launch Agent

```shell
launchctl unload -w /Library/LaunchAgents/com.contesa.fix.plist
launchctl load -w /Library/LaunchAgents/com.contesa.fix.plist
```

## MKDocs

```shell
mkdocs gh-deploy
```

## Elastic Beanstalk

```shell
dotnet eb deploy-environment
```
