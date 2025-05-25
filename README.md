# 🚀 Qdrant Admin UI - Complete Vector Database Management Interface

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Qdrant Version](https://img.shields.io/badge/Qdrant-v1.9.2+-blue.svg)](https://qdrant.tech/)
[![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-f7df1e.svg)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![HTML5](https://img.shields.io/badge/HTML5-E34F26.svg)](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6.svg)](https://developer.mozilla.org/en-US/docs/Web/CSS)

A **beautiful, modern, and feature-rich web-based administration interface** for Qdrant vector database. Think of it as **"pgAdmin for Qdrant"** - providing comprehensive vector database management, collection operations, point management, and advanced vector search capabilities through an intuitive web interface.

## 🌟 Why Choose Qdrant Admin UI?

- **Zero Installation Required** - Single HTML file, runs in any modern browser
- **Complete Feature Set** - All essential Qdrant operations in one place  
- **Modern Design** - Beautiful glassmorphism UI with smooth animations
- **Mobile Responsive** - Works perfectly on desktop, tablet, and mobile devices
- **Real-time Updates** - Live connection status and auto-refresh capabilities
- **Developer Friendly** - Clean code, well-documented, easy to customize

![Qdrant Admin UI Screenshot](https://via.placeholder.com/800x400/667eea/ffffff?text=Qdrant+Admin+UI+Screenshot)

## ✨ Key Features

### 🔗 **Connection Management**
- **One-Click Connection** to local and remote Qdrant instances
- **API Key Authentication** support for secure connections
- **Real-time Connection Status** with visual indicators
- **Auto-reconnect** functionality for stable connections

### 📁 **Collection Management**
- **Create Collections** with custom vector dimensions and distance metrics
- **View Collection Details** including status, point count, and configuration
- **Delete Collections** with safety confirmations
- **Collection Health Monitoring** with real-time status updates

### 📍 **Point Operations**
- **Add New Points** with vectors and rich JSON payloads
- **Browse Existing Points** with pagination and detailed view
- **Bulk Point Operations** - delete multiple points with filters
- **JSON Payload Editor** with syntax highlighting and validation

### 🔍 **Advanced Vector Search**
- **Similarity Search** with custom query vectors
- **Advanced Filtering** using Qdrant's powerful filter syntax
- **Search Result Analysis** with similarity scores and detailed metadata
- **Configurable Parameters** - limit, score threshold, payload options

### 📊 **Monitoring & Analytics**
- **Real-time Statistics** - collections count, total points, cluster size
- **Server Information** display with detailed system metrics  
- **Cluster Management** for distributed Qdrant deployments
- **Performance Monitoring** with connection health checks

### 🎨 **User Experience**
- **Modern Glassmorphism Design** with gradient backgrounds
- **Smooth Animations** and micro-interactions
- **Responsive Grid Layouts** that adapt to any screen size
- **Dark Mode Code Viewers** for JSON data inspection
- **Keyboard Shortcuts** for power users (Ctrl+R, Ctrl+N, etc.)

## 🚀 Quick Start

### Prerequisites
- **Qdrant Server** running (local or remote)
- **Modern Web Browser** (Chrome, Firefox, Safari, Edge)

### Installation Methods

#### Method 1: Direct Download (Recommended)
```bash
# Download the HTML file
curl -O https://raw.githubusercontent.com/your-repo/qdrant-admin-ui/main/qdrant-admin.html

# Open in browser
open qdrant-admin.html
```

#### Method 2: Clone Repository
```bash
git clone https://github.com/your-repo/qdrant-admin-ui.git
cd qdrant-admin-ui
open qdrant-admin.html
```

#### Method 3: Docker Compose Integration
Add to your existing `docker-compose.yml`:

```yaml
version: '3.8'
services:
  qdrant:
    image: qdrant/qdrant:v1.9.2
    container_name: qdrant
    ports:
      - "6333:6333"  # HTTP API
      - "6334:6334"  # gRPC API
    volumes:
      - qdrant_storage:/qdrant/storage
    restart: unless-stopped

  qdrant-admin:
    image: nginx:alpine
    container_name: qdrant-admin-ui
    ports:
      - "8080:80"
    volumes:
      - ./qdrant-admin.html:/usr/share/nginx/html/index.html:ro
    depends_on:
      - qdrant

volumes:
  qdrant_storage:
```

## 🔧 Configuration

### Connection Settings
- **Default URL**: `http://localhost:6333` (perfect for local development)
- **API Key**: Optional, leave empty for local instances
- **Custom Endpoints**: Support for remote Qdrant clusters

### Supported Qdrant Versions
- ✅ **Qdrant v1.9.2+** (Recommended)
- ✅ **Qdrant v1.8.x** (Partial support)
- ✅ **Qdrant v1.7.x** (Basic operations)

## 📖 Usage Guide

### 1. **Connect to Qdrant**
```
1. Open qdrant-admin.html in your browser
2. Enter your Qdrant server URL (default: http://localhost:6333)
3. Add API key if required
4. Click "Connect"
```

### 2. **Create Your First Collection**
```
1. Click "Create Collection" button
2. Enter collection name (e.g., "my_vectors")
3. Set vector dimension (e.g., 384 for sentence transformers)
4. Choose distance metric (Cosine, Euclidean, Dot Product)
5. Click "Create"
```

### 3. **Add Vector Points**
```
1. Select a collection from the sidebar
2. Go to "Points" tab
3. Click "Add Point"
4. Enter vector data: [0.1, 0.2, 0.3, ...]
5. Add metadata payload: {"category": "example"}
6. Click "Add"
```

### 4. **Perform Vector Search**
```
1. Go to "Search" tab
2. Enter query vector: [0.15, 0.25, 0.35, ...]
3. Set search limit and filters
4. Click "Search"
5. Analyze results with similarity scores
```

## 🎯 Use Cases

### **AI/ML Development**
- **Vector Embeddings Management** for NLP models
- **Similarity Search Testing** during model development
- **Dataset Exploration** and vector analysis
- **Model Performance Evaluation** with search metrics

### **Production Operations**
- **Database Health Monitoring** for production Qdrant clusters
- **Data Migration Tools** for moving vector collections
- **Troubleshooting Interface** for investigating search issues
- **Administrative Tasks** like bulk operations and cleanup

### **Research & Prototyping**
- **Rapid Prototyping** of vector search applications
- **Data Science Workflows** with interactive vector exploration
- **Educational Tool** for learning vector databases
- **Benchmark Testing** with custom search parameters

## 🔧 Advanced Configuration

### Environment Variables
```bash
# For containerized deployments
QDRANT_URL=http://qdrant:6333
QDRANT_API_KEY=your-secret-key
AUTO_CONNECT=true
REFRESH_INTERVAL=30000
```

### Custom Styling
The interface supports easy customization through CSS variables:
```css
:root {
  --primary-color: #667eea;
  --secondary-color: #764ba2;
  --success-color: #10b981;
  --error-color: #ef4444;
}
```

## 🚀 Performance & Scalability

- **Lightweight**: Single HTML file under 100KB
- **Fast Loading**: Minimal dependencies, pure JavaScript
- **Memory Efficient**: Optimized for large vector collections
- **Responsive**: Handles thousands of points with pagination
- **Network Optimized**: Efficient API calls with request batching

## 🔒 Security Considerations

- **API Key Support** for authenticated Qdrant instances
- **HTTPS Compatible** for secure remote connections
- **No Data Storage** - all operations are direct API calls
- **Client-Side Only** - no server-side components required
- **CORS Compliant** for cross-origin requests

## 🤝 Contributing

We welcome contributions! Here's how you can help:

### **Bug Reports**
- Use GitHub Issues with detailed reproduction steps
- Include browser version and Qdrant version
- Provide error messages and console logs

### **Feature Requests**
- Check existing issues before creating new ones
- Describe the use case and expected behavior
- Consider contributing the implementation

### **Code Contributions**
```bash
1. Fork the repository
2. Create feature branch: git checkout -b feature/amazing-feature
3. Commit changes: git commit -m 'Add amazing feature'
4. Push to branch: git push origin feature/amazing-feature
5. Open Pull Request
```

### **Development Setup**
```bash
git clone https://github.com/your-repo/qdrant-admin-ui.git
cd qdrant-admin-ui

# Start local Qdrant for testing
docker run -p 6333:6333 qdrant/qdrant:v1.9.2

# Open in browser with live reload
python -m http.server 8000
```

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **Qdrant Team** for creating an amazing vector database
- **Open Source Community** for inspiration and feedback
- **Contributors** who help improve this project
- **Users** who provide valuable bug reports and feature requests

## 📞 Support & Community

- **GitHub Issues**: [Report bugs and request features](https://github.com/your-repo/qdrant-admin-ui/issues)
- **Discussions**: [Community discussions and Q&A](https://github.com/your-repo/qdrant-admin-ui/discussions)
- **Qdrant Discord**: [Join the official Qdrant community](https://discord.gg/qdrant)
- **Documentation**: [Official Qdrant docs](https://qdrant.tech/documentation/)

## 🔗 Related Projects

- **[Qdrant](https://github.com/qdrant/qdrant)** - The vector database this UI manages
- **[Qdrant Client](https://github.com/qdrant/qdrant-client)** - Official Python client
- **[Qdrant JS](https://github.com/qdrant/qdrant-js)** - Official JavaScript client

## 📈 Roadmap

### **Upcoming Features**
- [ ] **Advanced Analytics Dashboard** with vector statistics
- [ ] **Import/Export Tools** for vector data migration
- [ ] **Query Builder** with visual filter construction
- [ ] **Performance Profiler** for search optimization
- [ ] **Multi-tenancy Support** for enterprise deployments
- [ ] **Plugin System** for custom extensions

### **Long-term Goals**
- [ ] **Desktop App** with Electron wrapper
- [ ] **Mobile App** for iOS and Android
- [ ] **Enterprise Features** with RBAC and audit logs
- [ ] **Integration APIs** for CI/CD pipelines

---

<div align="center">

**⭐ Star this repository if you find it useful!**

**Made with ❤️ for the Vector Database Community**

[🌟 Give it a Star](https://github.com/your-repo/qdrant-admin-ui) | [🐛 Report Bug](https://github.com/your-repo/qdrant-admin-ui/issues) | [💡 Request Feature](https://github.com/your-repo/qdrant-admin-ui/issues)

</div>
