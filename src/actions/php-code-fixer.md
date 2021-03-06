---
path: '/php-code-fixer'
title: 'PHP Code Fixer'
github_url: 'https://github.com/OskarStark/php-cs-fixer-ga'
author: 'OskarStark'
tags: []
subtitle: 'Github Action for PHP-CS-Fixer.'
---

## Usage

You can use it as a Github Action like this:

_.github/main.workflow_

```
workflow "Main" {
  on = "push"
  resolves = ["PHP-CS-Fixer"]
}

action "PHP-CS-Fixer" {
  uses = "docker://oskarstark/php-cs-fixer-ga"
  secrets = ["GITHUB_TOKEN"]
}
```

_to use a custom config for example, --diff and --dry-run option:_

```diff
workflow "Main" {
  on = "push"
  resolves = ["PHP-CS-Fixer"]
}

action "PHP-CS-Fixer" {
  uses = "docker://oskarstark/php-cs-fixer-ga"
  secrets = ["GITHUB_TOKEN"]
+  args = "--config=.project.php_cs --diff --dry-run"
}
```

**You can copy/paste the .github folder (under examples/) to your project and thats all!**

## Docker

A Docker-Image is built automatically and located here:
https://cloud.docker.com/u/oskarstark/repository/docker/oskarstark/php-cs-fixer-ga

You can run it in any given directory like this:

`docker run --rm -it -w=/app -v ${PWD}:/app oskarstark/php-cs-fixer-ga:latest`

## A picture is worth a thousand words

You can find a working and not working PR here:
https://github.com/OskarStark/test-php-cs-fixer-ga/pulls
