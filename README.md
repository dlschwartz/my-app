# my-app

[![License][license-img]][license-url]
[![GitHub release][release-img]][release-url]
![exist-db CI](https://github.com/dlschwartz/my-app/workflows/exist-db%20CI/badge.svg)

<img src="icon.png" align="left" width="25%"/>

My amazing app

## Requirements

*   [exist-db](http://exist-db.org/exist/apps/homepage/index.html) version: `5.3` or greater

*   [ant](http://ant.apache.org) version: `1.10.12` \(for building from source\)

*   [node](http://nodejs.org) version: `14.x` \(for building from source\)
    

## Installation

1.  Download  the `my-app-1.0.0.xar` file from GitHub [releases](https://github.com/dlschwartz/my-app/releases) page.

2.  Open the [dashboard](http://localhost:8080/exist/apps/dashboard/index.html) of your eXist-db instance and click on `package manager`.

    1.  Click on the `add package` symbol in the upper left corner and select the `.xar` file you just downloaded.

3.  You have successfully installed my-app into exist.

### Building from source

1.  Download, fork or clone this GitHub repository
2.  There are two default build targets in `build.xml`:
    *   `dev` including *all* files from the source folder including those with potentially sensitive information.
  
    *   `deploy` is the official release. It excludes files necessary for development but that have no effect upon deployment.
  
3.  Calling `ant`in your CLI will build both files:
  
```bash
cd my-app
ant
```

   1. to only build a specific target call either `dev` or `deploy` like this:
   ```bash   
   ant dev
   ```   

If you see `BUILD SUCCESSFUL` ant has generated a `my-app-1.0.0.xar` file in the `build/` folder. To install it, follow the instructions [above](#installation).



## Running Tests

To run tests locally your app needs to be installed in a running exist-db instance at the default port `8080` and with the default dba user `admin` with the default empty password.

A quick way to set this up for docker users is to simply issue:

```bash
docker run -dit -p 8080:8080 existdb/existdb:release
```

After you finished installing the application, you can run the full testsuite locally.

### Unit-tests

This app uses [mochajs](https://mochajs.org) as a test-runner. To run both xquery and javascript unit-tests type:

```bash
npm test
```

### Integration-tests

This app uses [cypress](https://www.cypress.io) for integration tests, just type:

```bash
npm run cypress
```

Alternatively, use npx:

```bash
npx cypress open
```


## Contributing

You can take a look at the [Contribution guidelines for this project](.github/CONTRIBUTING.md)

## License

AGPL-3.0 © [dlschwartz](https://dlschwartz.github.io/portfolio)

[license-img]: https://img.shields.io/badge/license-AGPL%20v3-blue.svg
[license-url]: https://www.gnu.org/licenses/agpl-3.0
[release-img]: https://img.shields.io/badge/release-1.0.0-green.svg
[release-url]: https://github.com/dlschwartz/my-app/releases/latest
