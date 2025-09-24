# Agent Axum

A modern Rust backend application built with Axum web framework.

## Prerequisites

- [Rust](https://rustup.rs/) (latest stable version)
- Cargo (comes with Rust)

## Quick Start

1. **Clone and navigate to the project:**
   ```bash
   cd agent-axum
   ```

2. **Install dependencies:**
   ```bash
   cargo build
   ```

3. **Run the development server:**
   ```bash
   cargo run
   ```

4. **The server will start on:** `http://localhost:8000`

## API Endpoints

### Root Endpoint
- **GET** `/`
- **Description**: Welcome message and API status
- **Response**: JSON with success status and welcome message

### Health Check
- **GET** `/health`
- **Description**: Server health status
- **Response**: JSON with health status and server information

### Echo Endpoint
- **GET** `/echo?param1=value1&param2=value2`
- **Description**: Echo back query parameters
- **Response**: JSON with the provided query parameters

## Example Usage

```bash
# Check if the server is running
curl http://localhost:8000/health

# Get welcome message
curl http://localhost:8000/

# Test echo endpoint
curl "http://localhost:8000/echo?name=John&age=30"
```

## Development

### Running in Development Mode

```bash
# Run with debug logging
RUST_LOG=debug cargo run

# Run with specific log level
RUST_LOG=agent_axum=debug,tower_http=debug cargo run
```

### Building for Production

```bash
# Build optimized release
cargo build --release

# Run the release binary
./target/release/agent-axum
```

## Project Structure

```
agent-axum/
├── src/
│   └── main.rs          # Main application entry point
├── Cargo.toml           # Dependencies and project configuration
└── README.md            # This file
```

## Dependencies

- **axum**: Modern web framework for Rust
- **tokio**: Async runtime
- **tower**: Middleware and service abstractions
- **tower-http**: HTTP-specific middleware (CORS, tracing)
- **tracing**: Structured logging
- **serde**: Serialization/deserialization
- **serde_json**: JSON support

## Configuration

The server runs on `127.0.0.1:8000` by default. To change the port or host, modify the `TcpListener::bind()` call in `main.rs`.

## Logging

The application uses structured logging with the `tracing` crate. Set the `RUST_LOG` environment variable to control log levels:

- `RUST_LOG=debug` - Debug level logging
- `RUST_LOG=agent_axum=debug,tower_http=debug` - Specific module logging
- `RUST_LOG=info` - Info level logging (default)

## Next Steps

This is a basic Axum application ready for extension. Consider adding:

- Database integration (SQLx, Diesel)
- Authentication middleware
- Request validation
- Error handling middleware
- API documentation (Swagger/OpenAPI)
- Testing framework
- Docker containerization

## License

This project is open source and available under the MIT License.
