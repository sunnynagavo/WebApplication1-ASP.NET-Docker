# WebApplication1 - ASP.NET Core Web Application with Docker

A modern ASP.NET Core web application built with Razor Pages and Docker support, demonstrating containerized deployment and development workflows.

## 🚀 Features

- **ASP.NET Core 10.0** - Latest .NET framework
- **Razor Pages** - Server-side rendered web pages
- **Bootstrap 5** - Responsive UI framework
- **Docker Support** - Containerized deployment
- **Docker Compose** - Multi-container orchestration
- **Development Environment** - Hot reload and debugging support

## 📋 Prerequisites

- [.NET 10.0 SDK](https://dotnet.microsoft.com/download/dotnet/10.0)
- [Docker](https://www.docker.com/get-started)
- [Docker Compose](https://docs.docker.com/compose/install/)

## 🛠️ Getting Started

### Local Development (without Docker)

1. **Clone the repository**
   ```bash
   git clone https://github.com/sunnynagavo/WebApplication1-ASP.NET-Docker.git
   cd WebApplication1-ASP.NET-Docker
   ```

2. **Restore dependencies**
   ```bash
   dotnet restore
   ```

3. **Run the application**
   ```bash
   dotnet run
   ```

4. **Open your browser**
   Navigate to `https://localhost:5001` or `http://localhost:5000`

### Docker Development

1. **Clone the repository**
   ```bash
   git clone https://github.com/sunnynagavo/WebApplication1-ASP.NET-Docker.git
   cd WebApplication1-ASP.NET-Docker
   ```

2. **Build and run with Docker Compose**
   ```bash
   docker compose up --build
   ```

3. **Access the application**
   Navigate to `http://localhost:8080`

## 🐳 Docker Commands

### Build the Docker image
```bash
docker build -t webapp1 .
```

### Run the container
```bash
docker run -p 8080:8080 webapp1
```

### Stop the container
```bash
docker compose down
```

## 🏗️ Project Structure

```
WebApplication1/
├── Pages/                          # Razor Pages
│   ├── Shared/                     # Shared layouts and partials
│   │   ├── _Layout.cshtml         # Main layout template
│   │   ├── _Layout.cshtml.css     # Layout-specific styles
│   │   └── _ValidationScriptsPartial.cshtml
│   ├── Index.cshtml               # Home page
│   ├── Index.cshtml.cs            # Home page model
│   ├── Privacy.cshtml             # Privacy page
│   ├── Privacy.cshtml.cs          # Privacy page model
│   ├── Error.cshtml               # Error page
│   ├── Error.cshtml.cs            # Error page model
│   ├── _ViewImports.cshtml        # Global view imports
│   └── _ViewStart.cshtml          # View start configuration
├── wwwroot/                       # Static files
│   ├── css/                       # Stylesheets
│   ├── js/                        # JavaScript files
│   ├── lib/                       # Client-side libraries
│   └── favicon.ico
├── Properties/
│   └── launchSettings.json        # Launch configuration
├── Program.cs                     # Application entry point
├── WebApplication1.csproj         # Project file
├── appsettings.json              # Application settings
├── appsettings.Development.json  # Development settings
├── Dockerfile                    # Docker configuration
├── .dockerignore                 # Docker ignore file
└── compose.yaml                  # Docker Compose configuration
```

## ⚙️ Configuration

### Application Settings

The application uses standard ASP.NET Core configuration:

- `appsettings.json` - Production settings
- `appsettings.Development.json` - Development-specific settings

### Environment Variables

You can override settings using environment variables:

```bash
export ASPNETCORE_ENVIRONMENT=Production
export ASPNETCORE_URLS=http://+:8080
```

## 🚀 Deployment

### Cloud Deployment

1. **Build for target platform**
   ```bash
   docker build --platform=linux/amd64 -t myapp .
   ```

2. **Push to registry**
   ```bash
   docker tag myapp myregistry.com/myapp
   docker push myregistry.com/myapp
   ```

3. **Deploy to your cloud provider**
   - Azure Container Instances
   - AWS ECS
   - Google Cloud Run
   - Kubernetes

### Production Considerations

- Configure HTTPS certificates
- Set up logging and monitoring
- Configure database connections
- Set environment-specific configurations
- Implement health checks

## 🧪 Development

### Adding New Pages

1. Create a new `.cshtml` file in the `Pages` directory
2. Create the corresponding `.cshtml.cs` page model
3. Update navigation in `_Layout.cshtml` if needed

### Styling

- Global styles: `wwwroot/css/site.css`
- Page-specific styles: Use scoped CSS files
- Bootstrap classes available throughout

### JavaScript

- Global scripts: `wwwroot/js/site.js`
- Page-specific scripts: Add to individual pages
- Client-side libraries: `wwwroot/lib/`

## 📝 Available Scripts

```bash
# Build the project
dotnet build

# Run in development mode
dotnet run

# Run tests (when added)
dotnet test

# Publish for production
dotnet publish -c Release

# Watch for file changes
dotnet watch run
```

## 🔧 Troubleshooting

### Common Issues

1. **Port already in use**
   ```bash
   # Find process using the port
   netstat -ano | findstr :8080
   # Kill the process or use a different port
   ```

2. **Docker build fails**
   ```bash
   # Clear Docker cache
   docker system prune -a
   # Rebuild without cache
   docker build --no-cache -t webapp1 .
   ```

3. **Dependencies not restored**
   ```bash
   # Clear NuGet cache
   dotnet nuget locals all --clear
   dotnet restore
   ```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [ASP.NET Core Documentation](https://docs.microsoft.com/en-us/aspnet/core/)
- [Docker .NET Guide](https://docs.docker.com/language/dotnet/)
- [Bootstrap](https://getbootstrap.com/)

## 📞 Support

If you encounter any issues or have questions:

1. Check the [Issues](https://github.com/sunnynagavo/WebApplication1-ASP.NET-Docker/issues) page
2. Create a new issue with detailed information
3. Contact the maintainers

---

**Built with ❤️ using ASP.NET Core and Docker**
