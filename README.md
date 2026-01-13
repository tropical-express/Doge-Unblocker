# Doge Unblocker

A powerful and easy-to-use proxy/unblocker application designed to help users access blocked content and bypass network restrictions safely and securely.

## 📋 Table of Contents

- [Features](#features)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)
- [Architecture](#architecture)
- [Contributing](#contributing)
- [License](#license)
- [Support](#support)

## ✨ Features

- **Fast & Reliable**: High-performance proxy with minimal latency
- **Easy Setup**: Simple installation process with minimal configuration
- **Secure Connection**: Encrypted communications for privacy
- **Multiple Protocols**: Support for various proxy protocols
- **User-Friendly**: Intuitive interface for both beginners and advanced users
- **Cross-Platform**: Works on Windows, macOS, and Linux
- **Lightweight**: Minimal resource consumption
- **Active Development**: Regular updates and improvements

## 📋 Prerequisites

Before you begin, ensure you have the following installed on your system:

- **Node.js** (v14.0.0 or higher) - [Download](https://nodejs.org/)
- **npm** (v6.0.0 or higher) - Comes with Node.js
- **Git** - [Download](https://git-scm.com/)

**Optional:**
- Docker (for containerized deployment)
- Python 3.8+ (for certain utilities)

## 🚀 Installation

### Option 1: Clone from GitHub

```bash
# Clone the repository
git clone https://github.com/tropical-express/Doge-Unblocker.git

# Navigate to the project directory
cd Doge-Unblocker

# Install dependencies
npm install
```

### Option 2: Using npm Package

```bash
npm install -g doge-unblocker
```

### Option 3: Docker Installation

```bash
# Build the Docker image
docker build -t doge-unblocker .

# Run the container
docker run -p 8080:8080 doge-unblocker
```

## ⚙️ Configuration

### Basic Configuration

Create a `.env` file in the project root directory:

```env
# Server Configuration
PORT=8080
HOST=localhost
NODE_ENV=development

# Proxy Settings
PROXY_TIMEOUT=30000
MAX_CONNECTIONS=100

# Security
ENABLE_SSL=false
SSL_KEY_PATH=./ssl/key.pem
SSL_CERT_PATH=./ssl/cert.pem

# Logging
LOG_LEVEL=info
LOG_FILE=./logs/app.log
```

### Advanced Configuration

Edit `config/settings.json` for more granular control:

```json
{
  "server": {
    "port": 8080,
    "host": "0.0.0.0",
    "keepAliveTimeout": 60000
  },
  "proxy": {
    "timeout": 30000,
    "maxConnections": 100,
    "retryAttempts": 3
  },
  "security": {
    "enableSSL": false,
    "enableAuthentication": false,
    "allowedOrigins": ["*"]
  }
}
```

## 📖 Usage

### Starting the Server

```bash
# Development mode
npm run dev

# Production mode
npm start

# Using nodemon for auto-reload
npm run watch
```

The application will be available at `http://localhost:8080`

### Command Line Options

```bash
# Custom port
npm start -- --port 3000

# Custom configuration file
npm start -- --config ./custom-config.json

# Verbose logging
npm start -- --verbose
```

### Client Integration

```javascript
// Example client usage
const ProxyClient = require('doge-unblocker');

const client = new ProxyClient({
  host: 'localhost',
  port: 8080,
  protocol: 'http'
});

client.connect().then(() => {
  console.log('Connected to unblocker');
}).catch(err => {
  console.error('Connection failed:', err);
});
```

## 🏗️ Architecture

### Project Structure

```
Doge-Unblocker/
├── src/
│   ├── server.js          # Main server entry point
│   ├── proxy/             # Proxy logic and handlers
│   ├── routes/            # API routes
│   ├── middleware/        # Express middleware
│   ├── utils/             # Utility functions
│   └── config/            # Configuration files
├── tests/                 # Test suite
├── docs/                  # Documentation
├── .env.example           # Example environment variables
├── package.json           # Project dependencies
├── README.md              # This file
└── LICENSE                # License information
```

### Key Components

- **Server**: Express.js based HTTP/HTTPS server
- **Proxy Layer**: Handles request/response proxying
- **Authentication**: Optional user authentication
- **Logging**: Comprehensive logging system
- **Error Handling**: Robust error management

## 🧪 Testing

```bash
# Run all tests
npm test

# Run tests with coverage
npm run test:coverage

# Run specific test suite
npm test -- tests/proxy.test.js

# Watch mode
npm run test:watch
```

## 📦 Building

```bash
# Create production build
npm run build

# Bundle for distribution
npm run bundle
```

## 🔧 Troubleshooting

### Port Already in Use

```bash
# Find process using port 8080
lsof -i :8080

# Kill the process
kill -9 <PID>

# Or use a different port
PORT=3000 npm start
```

### Connection Issues

1. Check firewall settings
2. Verify network connectivity
3. Review logs: `tail -f logs/app.log`
4. Ensure proxy settings are correctly configured

### SSL/TLS Errors

```bash
# Generate self-signed certificate
openssl req -x509 -newkey rsa:4096 -keyout key.pem -out cert.pem -days 365 -nodes
```

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Development Guidelines

- Follow the existing code style
- Add tests for new features
- Update documentation as needed
- Keep commits small and descriptive

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🆘 Support

- **Issues**: [GitHub Issues](https://github.com/tropical-express/Doge-Unblocker/issues)
- **Discussions**: [GitHub Discussions](https://github.com/tropical-express/Doge-Unblocker/discussions)
- **Documentation**: [Full Docs](./docs/)

## 🙏 Acknowledgments

- Community contributors and testers
- Open-source libraries and frameworks
- All users providing feedback and suggestions

---

**Last Updated**: 2026-01-13

For the latest updates, visit [GitHub Repository](https://github.com/tropical-express/Doge-Unblocker)
