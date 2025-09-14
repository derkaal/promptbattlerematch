# LLM Experiment Environment

A comprehensive multi-provider testing platform for evaluating Large Language Model (LLM) performance across different prompting frameworks in tool-calling scenarios. This project enables researchers and developers to compare the effectiveness of various prompting strategies using real API calls to OpenAI, Google Gemini, Mistral AI, and Anthropic Claude.

## 🎯 Project Overview

### Purpose

The LLM Experiment Environment is designed to scientifically evaluate and compare the effectiveness of different prompting frameworks when LLMs are tasked with tool-calling scenarios. By testing against multiple difficulty tiers and real-world ambiguity levels, this platform provides quantitative insights into which prompting approaches work best for specific use cases.

### Key Objectives

- **Framework Comparison**: Evaluate 4 distinct prompting frameworks across standardized scenarios
- **Multi-Provider Testing**: Support for OpenAI, Google Gemini, Mistral AI, and Anthropic Claude APIs
- **Quantitative Analysis**: Provide precise metrics including Tool Call Precision, Argument F1 Score, and Ambiguity Hit Rate
- **Reproducible Results**: Enable consistent, repeatable experiments without external dependencies
- **Real-World Validation**: Test with live API calls rather than simulated responses

## ✨ Features and Capabilities

### 🧠 Prompting Frameworks

#### 1. Designer's Paradigm
- **Philosophy**: Visual-spatial reasoning with structured decomposition
- **Strengths**: Complex multi-tool scenarios, spatial reasoning
- **Best For**: Architectural problems, system design tasks

#### 2. Linguistic Imperative
- **Philosophy**: Natural language flow with contextual reasoning
- **Strengths**: Ambiguous scenarios, contextual understanding
- **Best For**: Natural language processing, conversational tasks

#### 3. Managerial Directive
- **Philosophy**: Goal-oriented execution with clear hierarchies
- **Strengths**: Multi-step workflows, structured execution
- **Best For**: Business processes, project management tasks

#### 4. Hip-Hop G-Funk Protocol
- **Philosophy**: Rhythmic pattern recognition with creative synthesis
- **Strengths**: Pattern recognition, creative problem-solving
- **Best For**: Creative tasks, unconventional problem approaches

### 📊 Testing Capabilities

- **Three Difficulty Tiers**: Easy (single tool calls), Medium (multi-step workflows), Hard (complex reasoning)
- **15 Test Scenarios**: 5 scenarios per difficulty tier covering diverse use cases
- **Real-Time Execution**: Live API calls with progress tracking and detailed logging
- **Comprehensive Metrics**: Tool precision, argument accuracy, and ambiguity handling
- **Interactive Results**: Sortable tables with color-coded performance indicators

### 🔧 Tool Integration

The platform includes 6 core tools designed to cover common LLM use cases:
- [`get_weather`](llm-experiment-environment.html:757): Weather information retrieval
- [`search_database`](llm-experiment-environment.html:772): Database search operations
- [`create_file`](llm-experiment-environment.html:788): File creation and management
- [`calculate`](llm-experiment-environment.html:804): Mathematical operations and analysis
- [`send_email`](llm-experiment-environment.html:820): Communication workflows
- [`analyze_data`](llm-experiment-environment.html:837): Data analysis and insights

## 🚀 Installation and Setup

### Prerequisites

- Modern web browser (Chrome 90+, Firefox 88+, Safari 14+)
- API keys for one or more supported providers
- Internet connection for API calls

### Quick Start

1. **Download the Application**
   ```bash
   # Clone the repository or download the HTML file
   git clone https://github.com/your-repo/llm-experiment-environment.git
   cd llm-experiment-environment
   ```

2. **Open the Application**
   ```bash
   # Simply open the HTML file in your browser
   open llm-experiment-environment.html
   # or
   python -m http.server 8000  # For local server
   ```

3. **No Installation Required**
   - The application is a single, self-contained HTML file
   - All dependencies are embedded (CSS, JavaScript)
   - No external libraries or frameworks needed

### System Requirements

- **File Size**: < 2MB total (optimized for quick loading)
- **Memory Usage**: < 50MB during execution
- **Network**: Required for API calls only
- **Storage**: No local storage requirements

## 📖 Usage Guide

### Basic Workflow

1. **Select API Provider**
   - Choose from OpenAI, Google Gemini, Mistral AI, or Anthropic Claude
   - Each provider uses different models optimized for tool calling

2. **Enter API Key**
   - Input your API key for the selected provider
   - The system automatically validates the key connection

3. **Choose Framework**
   - Select a specific prompting framework or "All Frameworks" for comparison
   - View framework descriptions and strengths

4. **Run Tests**
   - Click "Run Tests" to begin live API testing
   - Monitor progress through real-time status indicators

5. **Analyze Results**
   - Review detailed metrics in the sortable results table
   - Examine execution logs for detailed insights

### Example Test Scenarios

#### Easy Tier Example
```
Scenario: "Create a new file called 'report.txt' with summary content"
Expected Tool: create_file
Expected Args: {filename: "report.txt", content: "Summary report", format: "txt"}
```

#### Medium Tier Example
```
Scenario: "Analyze sales data and create a summary report file"
Expected Tools: 
1. analyze_data (data_source: "sales", analysis_type: "summary")
2. create_file (filename: "sales_summary.txt", content: "Analysis results")
```

#### Hard Tier Example
```
Scenario: "The system performance seems off - investigate and report findings"
Expected Tools: 
1. search_database (query: "system performance", database: "logs")
2. analyze_data (data_source: "performance_logs", analysis_type: "summary")
3. create_file (filename: "performance_report.txt", content: "Investigation results")
```

### Understanding Metrics

#### Tool Call Precision
- **Formula**: `(Correct Tools Called / Total Tools Called) × 100`
- **Measures**: Accuracy of tool selection
- **Range**: 0-100%

#### Argument F1 Score
- **Formula**: `2 × (Precision × Recall) / (Precision + Recall)`
- **Measures**: Completeness and accuracy of tool parameters
- **Range**: 0.0-1.0

#### Ambiguity Hit Rate
- **Formula**: `(Successful Ambiguous Scenarios / Total Ambiguous) × 100`
- **Measures**: Success in handling unclear requirements
- **Range**: 0-100%

#### Composite Score
- **Weights**: Tool Precision (40%), Argument F1 (35%), Ambiguity Hit Rate (25%)
- **Purpose**: Overall framework effectiveness indicator

## 🔑 API Provider Setup

### OpenAI Setup

1. **Get API Key**
   - Visit [OpenAI API Platform](https://platform.openai.com/api-keys)
   - Create new API key with appropriate permissions

2. **Configuration**
   - **Model**: `gpt-4-turbo-preview`
   - **Endpoint**: `https://api.openai.com/v1/`
   - **Authentication**: Bearer token

3. **Required Permissions**
   - Chat completions access
   - Function calling capabilities

### Google Gemini Setup

1. **Get API Key**
   - Visit [Google AI Studio](https://makersuite.google.com/app/apikey)
   - Generate API key for Gemini API

2. **Configuration**
   - **Model**: `gemini-1.5-flash-latest`
   - **Endpoint**: `https://generativelanguage.googleapis.com/v1beta/`
   - **Authentication**: API key parameter

3. **Enable APIs**
   - Generative Language API
   - Function calling support

### Mistral AI Setup

1. **Get API Key**
   - Visit [Mistral AI Console](https://console.mistral.ai/)
   - Create API key in your account settings

2. **Configuration**
   - **Model**: `mistral-large-latest`
   - **Endpoint**: `https://api.mistral.ai/v1/`
   - **Authentication**: Bearer token

3. **Account Requirements**
   - Active Mistral AI account
   - Sufficient API credits

### Anthropic Claude Setup

1. **Get API Key**
   - Visit [Anthropic Console](https://console.anthropic.com/)
   - Generate API key with appropriate usage limits

2. **Configuration**
   - **Model**: `claude-3-5-sonnet-20241022`
   - **Endpoint**: `https://api.anthropic.com/v1/`
   - **Authentication**: x-api-key header

3. **Special Requirements**
   - Anthropic version header: `2023-06-01`
   - Tool use capabilities enabled

### API Key Security

⚠️ **Important Security Notes**:
- API keys are stored only in browser memory during session
- Keys are never logged or transmitted to third parties
- Clear browser data to remove any cached keys
- Use environment-specific keys for testing vs production

## 🏗️ Technical Architecture

### System Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                    HTML Container                           │
├─────────────────────────────────────────────────────────────┤
│  ┌─────────────────┐  ┌─────────────────┐  ┌─────────────┐ │
│  │   UI Controller │  │ API Integration │  │ Evaluation  │ │
│  │   - Framework   │  │ - Multi-Provider│  │ Metrics     │ │
│  │     Selection   │  │ - Live Calls    │  │ - Precision │ │
│  │   - Status Log  │  │ - Response Parse│  │ - F1 Score  │ │
│  │   - Results     │  │ - Error Handle  │  │ - Hit Rate  │ │
│  └─────────────────┘  └─────────────────┘  └─────────────┘ │
│                                                             │
│  ┌─────────────────────────────────────────────────────────┐ │
│  │              Test Battery Manager                       │ │
│  │  - Easy Tier (Basic tool calls)                        │ │
│  │  - Medium Tier (Multi-step scenarios)                  │ │
│  │  - Hard Tier (Complex reasoning + tools)               │ │
│  └─────────────────────────────────────────────────────────┘ │
└─────────────────────────────────────────────────────────────┘
```

### Core Components

#### Framework Manager
- **Purpose**: Manages the 4 prompting frameworks and their templates
- **Key Functions**: [`generatePrompt()`](llm-experiment-environment.html:1174), framework selection, template application
- **Location**: [`FRAMEWORKS`](llm-experiment-environment.html:566) object definition

#### API Integration Layer
- **Purpose**: Handles multi-provider API communication
- **Key Functions**: [`callProviderAPI()`](llm-experiment-environment.html:1187), provider-specific implementations
- **Supported Providers**: OpenAI, Gemini, Mistral, Claude

#### Test Battery System
- **Purpose**: Manages test scenarios across difficulty tiers
- **Key Functions**: [`runFrameworkTests()`](llm-experiment-environment.html:1093), scenario execution
- **Test Scenarios**: [`TEST_SCENARIOS`](llm-experiment-environment.html:607) configuration

#### Evaluation Engine
- **Purpose**: Calculates performance metrics and aggregates results
- **Key Functions**: [`evaluateResponse()`](llm-experiment-environment.html:1423), [`aggregateResults()`](llm-experiment-environment.html:1531)
- **Metrics**: Tool precision, argument F1, ambiguity hit rate

### Data Flow

1. **User Input** → Framework selection, API key validation
2. **Test Execution** → Prompt generation, API calls, response parsing
3. **Evaluation** → Metric calculation, result aggregation
4. **Display** → Table rendering, progress updates, logging

### Performance Optimizations

- **Rate Limiting**: 1-second delays between API calls to prevent throttling
- **Error Handling**: Graceful degradation with detailed error reporting
- **Memory Management**: Efficient result aggregation and display
- **Responsive Design**: Optimized for desktop, tablet, and mobile devices

## 🤝 Contributing Guidelines

### Development Setup

1. **Fork the Repository**
   ```bash
   git fork https://github.com/your-repo/llm-experiment-environment.git
   cd llm-experiment-environment
   ```

2. **Development Environment**
   - Any text editor or IDE
   - Modern web browser for testing
   - API keys for testing (use development keys)

### Code Structure

- **Single File Architecture**: All code contained in [`llm-experiment-environment.html`](llm-experiment-environment.html:1)
- **Modular JavaScript**: Organized into logical sections with clear separation
- **Embedded CSS**: Responsive design with mobile-first approach
- **No Build Process**: Direct editing and testing in browser

### Adding New Features

#### Adding a New API Provider

1. **Update Provider Configuration**
   ```javascript
   // Add to API_PROVIDERS object
   newprovider: {
       name: 'New Provider',
       endpoint: 'https://api.newprovider.com/v1/',
       model: 'new-model-name',
       keyPlaceholder: 'Enter New Provider API Key',
       testEndpoint: 'models',
       authHeader: 'Bearer'
   }
   ```

2. **Implement API Handler**
   ```javascript
   async function callNewProviderAPI(prompt, provider) {
       // Implementation specific to provider's API format
   }
   ```

3. **Add Response Parser**
   ```javascript
   function extractNewProviderToolCalls(response) {
       // Parse provider-specific response format
   }
   ```

#### Adding New Test Scenarios

1. **Define Scenario Structure**
   ```javascript
   {
       id: 'tier-number',
       description: 'Clear scenario description',
       expectedTools: [{ name: 'tool_name', args: {...} }],
       ambiguityLevel: 0.0-1.0,
       expectsNoTools: false
   }
   ```

2. **Add to Appropriate Tier**
   - Easy: Single tool, clear objectives
   - Medium: Multi-tool, moderate complexity
   - Hard: Complex reasoning, high ambiguity

#### Adding New Prompting Frameworks

1. **Framework Definition**
   ```javascript
   'new-framework': {
       name: "New Framework Name",
       description: "Framework philosophy and strengths",
       template: `Framework-specific prompt template`,
       effectiveness: { easy: 0.8, medium: 0.7, hard: 0.9 }
   }
   ```

2. **Update UI Elements**
   - Add option to framework selector
   - Update framework descriptions

### Testing Guidelines

1. **Manual Testing**
   - Test with multiple API providers
   - Verify all difficulty tiers
   - Check responsive design on different devices

2. **API Key Testing**
   - Use development/test API keys
   - Verify error handling for invalid keys
   - Test rate limiting behavior

3. **Cross-Browser Testing**
   - Chrome, Firefox, Safari compatibility
   - Mobile browser testing
   - JavaScript console error checking

### Submission Process

1. **Create Feature Branch**
   ```bash
   git checkout -b feature/new-feature-name
   ```

2. **Make Changes**
   - Follow existing code style and patterns
   - Add comments for complex logic
   - Test thoroughly across providers

3. **Submit Pull Request**
   - Clear description of changes
   - Include testing results
   - Reference any related issues

### Code Style Guidelines

- **JavaScript**: ES6+ features, async/await for API calls
- **CSS**: Mobile-first responsive design, consistent naming
- **HTML**: Semantic structure, accessibility considerations
- **Comments**: Explain complex logic and scientific rationale

## 📄 License Information

### MIT License

```
MIT License

Copyright (c) 2024 LLM Experiment Environment Contributors

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

### Third-Party Dependencies

This project is designed to be dependency-free, but it does interact with third-party APIs:

- **OpenAI API**: Subject to OpenAI's Terms of Service and Usage Policies
- **Google Gemini API**: Subject to Google's AI/ML Terms of Service
- **Mistral AI API**: Subject to Mistral AI's Terms of Service
- **Anthropic Claude API**: Subject to Anthropic's Commercial Terms of Service

### Usage Rights

- ✅ Commercial use permitted
- ✅ Modification and distribution allowed
- ✅ Private use encouraged
- ✅ Patent use granted
- ❌ No warranty provided
- ❌ No liability assumed

### Attribution

When using this software in research or commercial applications, please consider citing:

```
LLM Experiment Environment - A Multi-Provider Framework Testing Platform
Available at: https://github.com/your-repo/llm-experiment-environment
```

## 🔒 Security Considerations

### API Key Security

#### Storage and Handling
- **Memory Only**: API keys stored exclusively in browser memory during session
- **No Persistence**: Keys are never saved to localStorage, cookies, or files
- **No Transmission**: Keys only sent to respective API providers, never to third parties
- **Session Cleanup**: Keys cleared when browser tab is closed or refreshed

#### Best Practices
```javascript
// Example of secure key handling
function handleApiKeyChange() {
    currentApiKey = apiKeyInput.value.trim();
    // Key validation without logging
    if (currentApiKey.length > 10) {
        testApiConnection(); // Secure validation
    }
}
```

#### Recommendations
- Use development/testing API keys for experiments
- Set usage limits on API keys through provider consoles
- Regularly rotate API keys
- Monitor API usage through provider dashboards

### Network Security

#### HTTPS Requirements
- All API providers require HTTPS connections
- Browser enforces secure connections for API calls
- No mixed content warnings or security issues

#### CORS and CSP
- Application respects Cross-Origin Resource Sharing policies
- Content Security Policy compatible
- No external script dependencies that could introduce vulnerabilities

### Data Privacy

#### User Data
- **No User Data Collection**: Application doesn't collect personal information
- **No Analytics**: No tracking scripts or analytics services
- **Local Processing**: All data processing happens in browser

#### API Response Handling
- API responses processed locally in browser
- No response data sent to external services
- Temporary storage only during test execution

### Vulnerability Mitigation

#### Input Validation
```javascript
// Example of input sanitization
function validateApiKey(key) {
    // Remove potentially harmful characters
    return key.trim().replace(/[<>\"']/g, '');
}
```

#### Error Handling
- Detailed error messages without exposing sensitive information
- Graceful degradation when API calls fail
- No stack traces or internal details exposed to users

#### Rate Limiting Protection
- Built-in delays between API calls (1 second minimum)
- Prevents accidental API abuse
- Respects provider rate limits

### Security Audit Checklist

- [ ] API keys never logged or exposed
- [ ] All network requests use HTTPS
- [ ] No external dependencies loaded
- [ ] Input validation on all user inputs
- [ ] Error messages don't expose sensitive data
- [ ] No persistent storage of sensitive information
- [ ] Rate limiting implemented
- [ ] Cross-browser security testing completed

### Reporting Security Issues

If you discover a security vulnerability, please:

1. **Do Not** create a public GitHub issue
2. **Email** security concerns to: [security@your-domain.com]
3. **Include** detailed description and reproduction steps
4. **Allow** reasonable time for response and fix

We take security seriously and will respond to legitimate security concerns promptly.

## 🛠️ Troubleshooting

### Common Issues and Solutions

#### API Connection Problems

**Issue**: "API key validation failed" error
```
Solutions:
1. Verify API key is correct and active
2. Check API key permissions in provider console
3. Ensure sufficient API credits/quota
4. Try refreshing the page and re-entering key
```

**Issue**: "HTTP 429: Too Many Requests" error
```
Solutions:
1. Wait 60 seconds before retrying
2. Check your API usage limits
3. Reduce test frequency
4. Consider upgrading API plan
```

**Issue**: "CORS error" or "Network error"
```
Solutions:
1. Ensure stable internet connection
2. Check if corporate firewall blocks API endpoints
3. Try different network (mobile hotspot)
4. Verify API endpoint URLs are correct
```

#### Framework and Testing Issues

**Issue**: Tests fail with "No tool calls detected"
```
Possible Causes:
1. API provider doesn't support function calling
2. Model version doesn't support tools
3. Prompt template incompatible with provider

Solutions:
1. Verify provider supports function calling
2. Check model compatibility in provider docs
3. Try different framework or provider
```

**Issue**: Inconsistent results across runs
```
Possible Causes:
1. API provider temperature settings
2. Model non-determinism
3. Rate limiting affecting responses

Solutions:
1. Run multiple test iterations
2. Check for API provider status issues
3. Ensure consistent network conditions
```

**Issue**: "Argument F1 Score always 0"
```
Possible Causes:
1. Tool arguments don't match expected format
2. Case sensitivity in argument comparison
3. Provider returns different argument structure

Solutions:
1. Check expected vs actual arguments in logs
2. Verify tool definitions match provider format
3. Review argument parsing logic
```

#### Browser and Performance Issues

**Issue**: Application runs slowly or freezes
```
Solutions:
1. Close other browser tabs to free memory
2. Disable browser extensions temporarily
3. Clear browser cache and cookies
4. Try incognito/private browsing mode
5. Use Chrome or Firefox for best performance
```

**Issue**: Results table doesn't display correctly
```
Solutions:
1. Refresh the page
2. Check browser console for JavaScript errors
3. Ensure browser supports modern JavaScript (ES6+)
4. Try different browser
```

**Issue**: Mobile display problems
```
Solutions:
1. Rotate device to landscape mode
2. Zoom out to see full interface
3. Use tablet or desktop for better experience
4. Check responsive design in browser dev tools
```

#### Provider-Specific Issues

**OpenAI Issues**
```
Common Problems:
- Model deprecation warnings
- Function calling format changes
- Rate limit variations

Solutions:
- Check OpenAI status page
- Verify model availability
- Review OpenAI API documentation
```

**Google Gemini Issues**
```
Common Problems:
- API key format differences
- Function declaration format
- Regional availability

Solutions:
- Ensure API key from Google AI Studio
- Check Gemini API documentation
- Verify service availability in your region
```

**Mistral AI Issues**
```
Common Problems:
- Limited function calling support
- Model availability
- Credit requirements

Solutions:
- Verify function calling is supported
- Check account credits
- Review Mistral AI documentation
```

**Anthropic Claude Issues**
```
Common Problems:
- Special header requirements
- Tool use format differences
- Usage tier limitations

Solutions:
- Ensure anthropic-version header is set
- Check tool format in Claude documentation
- Verify account tier supports tool use
```

### Debugging Steps

#### Step 1: Check Browser Console
```javascript
// Open browser developer tools (F12)
// Look for JavaScript errors in Console tab
// Common errors and meanings:
// - "Fetch failed" = Network/API issue
// - "JSON parse error" = Response format issue
// - "Undefined function" = JavaScript compatibility issue
```

#### Step 2: Verify API Configuration
```javascript
// Check these values in browser console:
console.log('Current Provider:', currentProvider);
console.log('API Key Length:', currentApiKey.length);
console.log('Provider Config:', API_PROVIDERS[currentProvider]);
```

#### Step 3: Test API Connection Manually
```bash
# Test OpenAI API
curl -H "Authorization: Bearer YOUR_API_KEY" \
     https://api.openai.com/v1/models

# Test Gemini API
curl "https://generativelanguage.googleapis.com/v1beta/models?key=YOUR_API_KEY"

# Test Mistral API
curl -H "Authorization: Bearer YOUR_API_KEY" \
     https://api.mistral.ai/v1/models

# Test Claude API
curl -H "x-api-key: YOUR_API_KEY" \
     -H "anthropic-version: 2023-06-01" \
     https://api.anthropic.com/v1/messages
```

#### Step 4: Enable Detailed Logging
```javascript
// Add this to browser console for verbose logging:
window.DEBUG_MODE = true;

// This will show additional debug information in logs
```

### Getting Help

#### Community Support
- **GitHub Issues**: Report bugs and request features
- **Discussions**: Ask questions and share experiences
- **Wiki**: Community-maintained documentation and tips

#### Documentation Resources
- **API Provider Docs**: Official documentation for each provider
- **Framework Research**: Academic papers on prompting strategies
- **Tool Calling Guides**: Best practices for function calling

#### Professional Support
For enterprise users requiring dedicated support:
- Custom framework development
- Large-scale testing infrastructure
- Integration consulting
- Performance optimization

### Performance Optimization Tips

#### For Large Test Runs
1. **Batch Testing**: Run frameworks individually rather than "All Frameworks"
2. **Rate Limiting**: Increase delays between calls if experiencing timeouts
3. **Memory Management**: Refresh page between large test runs
4. **Network Optimization**: Use stable, high-speed internet connection

#### For Better Results
1. **Multiple Runs**: Execute tests multiple times for statistical significance
2. **Provider Comparison**: Test same framework across different providers
3. **Scenario Customization**: Modify test scenarios for your specific use case
4. **Metric Analysis**: Focus on metrics most relevant to your application

---

*For additional support, please check our [GitHub Issues](https://github.com/your-repo/llm-experiment-environment/issues) or create a new issue with detailed information about your problem.*