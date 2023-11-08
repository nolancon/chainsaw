# Error

The `error` operation lets you define a set of expected errors for a test step. If any of these errors occur during the test, they are treated as expected outcomes. However, if an error that's not on this list occurs, it will be treated as a test failure.

The full structure of the `Error` is documented [here](../../apis/chainsaw.v1alpha1.md#chainsaw-kyverno-io-v1alpha1-Error).

## Usage in `Test`

Below is an example of using `error` in a `Test` resource.

!!! example

    ```yaml
    apiVersion: chainsaw.kyverno.io/v1alpha1
    kind: Test
    metadata:
      name: example
    spec:
      steps:
      - try:
        # ...
        - error:
            file: ../resources/configmap-error.yaml
        # ...
    ```

## Usage in `TestStep`

Below is an example of using `error` in a `TestStep` resource.

!!! example

    ```yaml
    apiVersion: chainsaw.kyverno.io/v1alpha1
    kind: TestStep
    metadata:
      name: example
    spec:
      try:
      # ...
      - error:
          file: ../resources/configmap-error.yaml
      # ...
    ```