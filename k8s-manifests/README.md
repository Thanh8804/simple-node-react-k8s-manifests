# K8s Manifests Documentation

This project utilizes Kustomize to manage Kubernetes manifests for different environments. The structure is organized into a base directory containing common configurations and overlays for specific environments (development and production).

## Project Structure

- **base/**: Contains the base configurations that are common across environments.
  - **deployment.yaml**: Defines the deployment configuration for the application.
  - **service.yaml**: Defines the service configuration for the application.
  - **kustomization.yaml**: Kustomize configuration for the base resources.

- **overlays/**: Contains environment-specific configurations.
  - **dev/**: Development environment configurations.
    - **kustomization.yaml**: Kustomize configuration for the development environment.
    - **service-path.yaml**: Environment-specific configurations for the service in development.
  - **prod/**: Production environment configurations.
    - **kustomization.yaml**: Kustomize configuration for the production environment.
    - **service-path.yaml**: Environment-specific configurations for the service in production.

## Usage

To deploy the configurations for a specific environment, navigate to the corresponding overlay directory and run the following command:

```bash
kubectl apply -k .
```

This command applies the Kustomize configurations, merging the base resources with any environment-specific modifications.

## Notes

- Ensure that you have Kustomize installed and configured in your environment.
- Modify the `service-path.yaml` files in the respective overlays to customize service settings for each environment as needed.