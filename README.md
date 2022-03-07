# Build Java Service Image

Builds a Java service Docker image.

- Installs JDK 8
- Runs the Maven `install` command to compile the service
- Builds the Docker image and names it `service`.

Required environment variables:
```sh
# The token to use while pulling the private GitHub Maven Packages
GITHUB_TOKEN=....
```

Example usage:
```yaml
jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout repository
        uses: actions/checkout@v2

      - name: Test and build Docker image
        uses: QActions/build-java-service-image@1.0.0
        env:
          GITHUB_TOKEN: ${{ secrets.GH_PACKAGES_FULL_READ_ACCESS_TOKEN }}
```
