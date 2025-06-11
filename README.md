# 📸 Ultimate Web Screenshot & Video Capture Tool 🎥

[![Apify Actor](https://img.shields.io/badge/Apify-Actor-blue?logo=apify)](https://apify.com)

Transform any webpage into high-quality screenshots, PDFs, or engaging videos/GIFs with our powerful web capture tool. Perfect for web monitoring, content creation, documentation, and automated testing.

## ✨ Key Features

### 📷 Multiple Output Formats
- **Static Images**: High-quality PNG/JPEG screenshots
- **PDF Documents**: Professional document generation with custom margins
- **Video Content**: MP4 recordings and animated GIFs
- **Full-Page Capture**: Capture entire webpage length, not just viewport

### 🎬 Advanced Video & Animation
- **Screen Recording**: Create MP4 videos of webpage interactions
- **Animated GIFs**: Generate engaging animated captures
- **Scrolling Effects**: Smooth scroll-through animations for long pages
- **Custom Frame Rates**: Control video quality and file size

### 📱 Device Emulation
- **100+ Device Presets**: iPhone, iPad, Android, tablets, and more
- **Responsive Testing**: See how your site looks on different devices
- **Custom Dimensions**: Set any viewport size for testing
- **Orientation Support**: Portrait and landscape modes

### 🌐 Advanced Web Features
- **Proxy Support**: Bypass geo-restrictions and rate limits
- **Cookie Management**: Maintain sessions and bypass paywalls
- **SSL Flexibility**: Handle sites with certificate issues
- **Custom User Agents**: Simulate different browsers and devices

## 🚀 Quick Start

### Basic Screenshot
```json
{
  "linkUrls": ["https://example.com"],
  "outputFormat": "png",
  "fullPage": true
}
```

### Mobile Device Emulation
```json
{
  "linkUrls": ["https://example.com"],
  "device": "iPhone 14 Pro",
  "outputFormat": "jpeg"
}
```

### Video Capture
```json
{
  "linkUrls": ["https://example.com"],
  "outputFormat": "mp4",
  "fullPage": true,
  "frameCounT": 20,
  "frameIntervaL": 500
}
```

### PDF Generation
```json
{
  "linkUrls": ["https://example.com"],
  "outputFormat": "pdf",
  "formaT": "A4",
  "printBackground": true
}
```

## 📋 Input Configuration

### 🎯 Basic Settings

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| `linkUrls` | Array | `["https://apify.com"]` | URLs to capture |
| `outputFormat` | String | `"jpeg"` | Output format: `jpeg`, `png`, `pdf`, `gif`, `mp4` |
| `fullPage` | Boolean | `false` | Capture entire page length |
| `waitUntil` | String | `"networkidle0"` | Page load condition |
| `timeouT` | Integer | `15` | Page load timeout (seconds) |
| `delayBeforeScreenshot` | Integer | `1500` | Pre-capture delay (ms) |

### 📱 Device & Viewport

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| `device` | String | - | Device preset (iPhone 14, iPad Pro, etc.) |
| `window_Width` | Integer | `1920` | Custom viewport width |
| `window_Height` | Integer | `1080` | Custom viewport height |

### 🎬 Video/GIF Options

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| `frameCounT` | Integer | `15` | Number of frames to capture |
| `frameIntervaL` | Integer | `10` | Milliseconds between frames |
| `frame` | Integer | `10` | Frames per second (FPS) |
| `scrollSteP` | Integer | `300` | Scroll distance per frame |

### 📄 PDF Options

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| `formaT` | String | `"A4"` | Paper size (A4, Letter, Legal, etc.) |
| `printBackground` | Boolean | `true` | Include background colors/images |
| `toP`, `righT`, `bottoM`, `lefT` | Integer | `0` | Margins in millimeters |

### 🌐 Advanced Options

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| `scrollToBottom` | Boolean | `false` | Auto-scroll before capture |
| `cookies` | Array | `[]` | Custom cookies for authentication |
| `proxyConfig` | Object | `{}` | Proxy configuration |
| `enableSSL` | Boolean | `false` | Strict SSL validation |

## 📊 Output Data

Each successful capture returns:

```json
{
  "screenshot_image": "https://api.apify.com/v2/...",
  "content_Type": "image/png",
  "linkUrl": "https://example.com",
  "screenshot_url": "https://api.apify.com/v2/..."
}
```

## 🎯 Use Cases

### 📈 Business & Marketing
- **Website Monitoring**: Track visual changes and performance
- **Competitor Analysis**: Capture competitor pages regularly
- **Social Media Content**: Create engaging visuals for posts
- **Portfolio Documentation**: Showcase web projects

### 🧪 Development & Testing
- **Responsive Testing**: Verify mobile compatibility
- **Cross-Browser Testing**: Ensure consistent appearance
- **Automated Screenshots**: Integrate with CI/CD pipelines
- **Bug Documentation**: Capture error states visually

### 📚 Content Creation
- **Tutorial Videos**: Create step-by-step guides
- **Documentation**: Generate visual documentation
- **Presentations**: Professional webpage captures
- **Archive Pages**: Preserve webpage states

### 🔍 Research & Monitoring
- **Price Monitoring**: Track e-commerce changes
- **News Archival**: Preserve article layouts
- **Social Media Tracking**: Monitor profiles and posts
- **Academic Research**: Capture web-based data

## ⚙️ Advanced Configuration Examples

### Authenticated Capture with Cookies
```json
{
  "linkUrls": ["https://secure-site.com/dashboard"],
  "cookies": [
    {
      "name": "session_token",
      "value": "abc123xyz",
      "domain": ".secure-site.com"
    }
  ],
  "outputFormat": "png"
}
```

### Proxy-Enabled Capture
```json
{
  "linkUrls": ["https://geo-restricted-site.com"],
  "proxyConfig": {
    "useApifyProxy": true,
    "proxyUrls": ["http://proxy.example.com:8080"]
  },
  "outputFormat": "jpeg"
}
```

### High-Quality Video Recording
```json
{
  "linkUrls": ["https://interactive-demo.com"],
  "outputFormat": "mp4",
  "fullPage": true,
  "frameCounT": 30,
  "frameIntervaL": 100,
  "frame": 24,
  "scrollSteP": 200
}
```

## 🔧 Technical Details

### Supported Devices
Over 100 device presets including:
- **iPhones**: 4, 5, 6, 7, 8, X, 11, 12, 13, 14, 15 series
- **iPads**: Mini, Pro, Air, all generations
- **Android**: Galaxy, Pixel, Nexus series
- **Tablets**: Various Android and Windows tablets

### Output Formats
- **JPEG**: Smaller file size, good for web use
- **PNG**: Lossless quality, supports transparency
- **PDF**: Document format with custom page sizes
- **GIF**: Animated format, perfect for demos
- **MP4**: High-quality video format

### Performance
- **Speed**: Optimized for fast capture and processing
- **Reliability**: Built-in retry mechanisms and error handling
- **Scalability**: Handle multiple URLs efficiently
- **Memory**: Efficient frame management for video capture

## 🛠️ Installation & Usage

1. **Find this Actor** on [Apify Store](https://apify.com/store)
2. **Configure Input** using the visual editor or JSON
3. **Run the Actor** and wait for completion
4. **Download Results** from the generated dataset

### Integration Options
- **Apify API**: Programmatic access via REST API
- **Webhooks**: Automated notifications on completion
- **Scheduling**: Run captures at regular intervals
- **Zapier/Make**: Connect with other tools and services

## 🔍 Troubleshooting

### Common Issues

**Page won't load?**
- Increase `timeouT` value
- Check `enableSSL` setting for HTTPS sites
- Verify URL accessibility

**Screenshots are blank?**
- Increase `delayBeforeScreenshot`
- Try different `waitUntil` conditions
- Check if site blocks automation

**Video too short/long?**
- Adjust `frameCounT` and `frameIntervaL`
- Modify `scrollSteP` for better pacing
- Use `timefullPagE` to control duration

**Device emulation not working?**
- Ensure device name matches exactly
- Check if site has responsive design
- Try custom dimensions instead

## 📄 API Reference

### Input Schema
The actor accepts a comprehensive input schema with validation for all parameters. See the complete schema in the actor's input configuration.

### Output Schema
Results are stored in Apify Dataset with the following structure:
- `screenshot_image`: Preview URL
- `content_Type`: MIME type
- `linkUrl`: Source URL
- `screenshot_url`: Download URL

## 🏆 Best Practices

1. **Optimize for Purpose**: Choose the right format for your use case
2. **Test Settings**: Start with default values and adjust as needed
3. **Handle Failures**: Use retry mechanisms for critical captures
4. **Monitor Usage**: Track actor runs and optimize for efficiency
5. **Respect Limits**: Be mindful of target site rate limits

## 📈 Performance Tips

- Use `jpeg` for smaller file sizes
- Reduce `frameCounT` for faster video processing
- Enable `scrollToBottom` for dynamic content
- Set appropriate `delayBeforeScreenshot` for complex pages

## 🤝 Support & Contact

For assistance or custom implementations:

- 📧 Email: [fridaytechnolog@gmail.com](mailto:fridaytechnolog@gmail.com)
- 🐙 GitHub: [DZ-ABDLHAKIM](https://github.com/DZ-ABDLHAKIM)
- 🐦 Twitter: [@DZ_45Omar](https://x.com/DZ_45Omar)
- 🔧 Apify: [dz_omar](https://apify.com/dz_omar)
