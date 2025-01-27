# On-Premises Document Intelligence Ingestion
On-Premises Document Intelligence Ingestion


## Various notes

All `yaml` files in the `/docint` folder are docker compose files.

To start a Form recognizer service, type:
`docker compose -f docint-generaldoc.yaml up`

The containers images can be prepositioned with this command:

```bash
#!/bin/bash

# List of Docker images to pull
images=(
    "businesscard-3.0"
    "layout-3.0"
    "document-3.0"
    "id-document-3.1"
    "read-3.1"
    "layout-3.1"
    "invoice-3.1"
)

# Loop through each image and pull it
for image in "${images[@]}"; do
    docker pull "mcr.microsoft.com/azure-cognitive-services/form-recognizer/$image"
done
```