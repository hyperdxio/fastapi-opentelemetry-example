# FastAPI OpenTelemetry Example

This is an example of auto-instrumenting a FastAPI app using OpenTelemetry.

## Getting Started

```
git clone https://github.com/hyperdxio/fastapi-opentelemetry-example.git
cd fastapi-opentelemetry-example

# Create virtualenv
virtualenv -p python3 venv
source venv/bin/activate

# Install Dependencies
pip install -r requirements.txt
```

## Running Instrumented Application

You can run the instrumented application sending telemetry to HyperDX cloud via:

```
HYPERDX_API_KEY='<YOUR_HYPERDX_API_KEY_HERE>' \
OTEL_SERVICE_NAME='<NAME_OF_YOUR_APP_OR_SERVICE>' \
opentelemetry-instrument uvicorn main:app
```

Or to send to any OpenTelemetry compatible collector:

```
OTEL_EXPORTER_OTLP_ENDPOINT=http://localhost:4318 \
OTEL_PYTHON_LOGGING_AUTO_INSTRUMENTATION_ENABLED=true \
OTEL_SERVICE_NAME='<NAME_OF_YOUR_APP_OR_SERVICE>' \
opentelemetry-instrument uvicorn main:app
```
