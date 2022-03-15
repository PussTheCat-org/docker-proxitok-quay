# docker-proxitok-quay

A [ProxiTok](https://github.com/pablouser1/ProxiTok) image, on Quay.

[Quay page](https://quay.io/repository/pussthecatorg/proxitok) | [GitHub page](https://github.com/PussTheCat-org/docker-proxitok-quay)

This image mostly exist for the [PussTheCat.org](https://pussthecat.org/) [instance](https://proxitok.pussthecat.org/), but others are free to use it.

## Usage:

- Download (or copy the content of) the `docker-compose.yml`
- `docker-compose up -d`

## Credit:

- [@Lomanic](https://github.com/Lomanic) for helping me figuring how to pass a GitHub token to composer (necessary because CI is rate limited)
- [@MoriTanosuke](https://github.com/MoriTanosuke) for [going further than me](https://github.com/pablouser1/ProxiTok/issues/13#issuecomment-1067748033) in the creation of a working Dockerfile.
- [@pablouser1](https://github.com/pablouser1) for making ProxiTok, and getting the Dockerfile from an experimental, to a production ready state.
