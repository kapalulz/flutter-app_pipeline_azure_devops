# Flutter CI/CD with Azure DevOps and App Center

A Flutter sample application with an Azure DevOps pipeline that demonstrates the path from source commit to mobile build and App Center distribution.

## Workflow

1. A source change triggers Azure DevOps.
2. The pipeline restores Flutter dependencies.
3. Static analysis and tests can run before packaging.
4. The application is built.
5. The resulting artifact is uploaded to App Center for distribution.

The application used by the pipeline is `simplistic_calculator`.

## Run the app

```bash
flutter pub get
flutter analyze
flutter test
flutter run
```

## Pipeline

The pipeline definition is stored in `azure-pipelines.yml`. Configure signing and App Center credentials through protected pipeline variables or a secret manager—never in the repository.

## Security note

Mobile signing files and passwords are sensitive. Use secure files in Azure DevOps and rotate any credential or signing material that has ever been committed to source control.
