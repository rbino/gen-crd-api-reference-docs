# Knative API Reference Docs generator

## Why?

Normally we would want to use [Kubernetes API
reference](https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.13/)
which is auto-generated. But for the time being, Kubernetes API does not provide
OpenAPI specs for CRDs (e.g. Knative), therefore we cannot use the same
generator.

## How?

This is a custom API Reference Docs generator that uses the
[k8s.io/gengo](https://godoc.org/k8s.io/gengo) project to parse types and
generate API documentation from it.

## Try it out

1. Clone this repository.

2. Make sure you have go1.11+ instaled.

3. Clone a Knative repository, set GOPATH correctly,
   and call the compiled binary within that directory.

    ```sh
    $ goclone knative/build

    $ refdocs \
        -api-dir "github.com/knative/build/pkg/apis/build/v1alpha1" \
        -api-prefix "github.com/knative/build/pkg/apis/"
    ```

4. Visit [localhost:8080](localhost:8080) to view generated documentation.

-----

This is not an official Google project. See [LICENSE](./LICENSE).
