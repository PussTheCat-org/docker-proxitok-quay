# docker-proxitok-quay

According to the documentation https://github.com/docker/build-push-action/blob/master/docs/advanced/secrets.md :

https://github.com/PussTheCat-org/docker-proxitok-quay/blob/master/.github/workflows/container-release.yml#L49

Is supposed to expose a token to `/run/secrets/`

It doesn't: https://github.com/PussTheCat-org/docker-proxitok-quay/runs/5452247802?check_suite_focus=true#step:6:562

I wasted more than 3 hours on that.
