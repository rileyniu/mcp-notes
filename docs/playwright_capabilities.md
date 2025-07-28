# Playwright MCP Server: Complete Capabilities Guide

## 🔧 Available Tools

The Playwright MCP server provides these core browser automation tools:

### Navigation & Page Control
- **`navigate_to(url)`** - Go to any website
- **`go_back()`** - Browser back button
- **`go_forward()`** - Browser forward button
- **`reload()`** - Refresh current page
- **`new_tab()`** - Open new browser tab
- **`close_tab()`** - Close current tab
- **`switch_tab(index)`** - Switch between tabs

### Content Interaction
- **`click(selector)`** - Click any element (buttons, links, etc.)
- **`type(selector, text)`** - Type into input fields
- **`fill(selector, text)`** - Fill form fields
- **`select_option(selector, value)`** - Select dropdown options
- **`check(selector)`** - Check checkboxes
- **`uncheck(selector)`** - Uncheck checkboxes

### Data Extraction
- **`get_text(selector)`** - Extract text from elements
- **`get_attribute(selector, attribute)`** - Get element attributes
- **`get_page_title()`** - Get page title
- **`get_url()`** - Get current URL
- **`screenshot()`** - Take page screenshot
- **`get_page_content()`** - Get full HTML content

### Advanced Actions
- **`scroll(direction, amount)`** - Scroll page
- **`hover(selector)`** - Hover over elements
- **`drag_and_drop(source, target)`** - Drag and drop
- **`upload_file(selector, filepath)`** - Upload files
- **`execute_script(script)`** - Run custom JavaScript

---

## 🚀 Workflow Examples

### 1. Web Research & Data Collection

**Prompt:** 
```
Research the top 5 Python web frameworks by:
1. Going to Stack Overflow
2. Searching for "best Python web frameworks 2024"
3. Extracting the framework names from the top 3 results
4. For each framework, visit its official website and get the tagline
5. Create a summary report
```

**What happens:**
- Navigates to Stack Overflow
- Performs search
- Extracts data from multiple pages
- Compiles comprehensive report

### 2. E-commerce Price Monitoring

**Prompt:**
```
Monitor Amazon prices for "MacBook Pro M3":
1. Search for the product
2. Extract prices from first 5 results
3. Take screenshots of each listing
4. Save data to a JSON file
5. Set up to run this daily
```

**Automation Value:** Saves hours of manual price checking

### 3. Social Media Content Automation

**Prompt:**
```
Create a LinkedIn post about our new product:
1. Go to LinkedIn
2. Navigate to create post
3. Upload our product image
4. Write an engaging caption about our launch
5. Schedule for optimal posting time
```

### 4. Competitive Analysis

**Prompt:**
```
Analyze our competitor's website changes:
1. Visit competitor's homepage
2. Take full-page screenshot
3. Extract all navigation menu items
4. Check their pricing page
5. Compare with our stored data from last week
6. Generate change report
```

### 5. Lead Generation

**Prompt:**
```
Find potential clients in the SaaS space:
1. Go to Crunchbase
2. Search for "SaaS startups Series A"
3. Extract company names, descriptions, and contact info
4. Visit each company's website
5. Check if they have a careers page (indicates growth)
6. Compile qualified leads list
```

---

## 💡 Advanced MCP Workflows

### Multi-Server Orchestration

Combine Playwright with other MCP servers for powerful workflows:

```json
{
    "model": "Qwen/Qwen2.5-72B-Instruct",
    "provider": "nebius",
    "servers": [
        {
            "type": "stdio",
            "command": "npx",
            "args": ["@playwright/mcp@latest"]
        },
        {
            "type": "stdio", 
            "command": "npx",
            "args": ["@modelcontextprotocol/server-filesystem"]
        },
        {
            "type": "stdio",
            "command": "npx", 
            "args": ["@modelcontextprotocol/server-slack"]
        }
    ]
}
```

**Workflow Example:**
1. **Playwright** scrapes job postings
2. **Filesystem** saves data to CSV
3. **Slack** sends daily summary to team

### Content Management Workflow

**Prompt:**
```
Automate our blog content workflow:
1. Check our WordPress admin for pending posts
2. For each draft post:
   - Extract the content
   - Check for SEO optimization
   - Verify all images have alt text
   - Test internal links
3. Generate content improvement suggestions
4. Create a report and email it to the content team
```

### Customer Support Automation

**Prompt:**
```
Monitor our support system:
1. Login to our help desk
2. Check for tickets tagged "urgent"
3. For each urgent ticket:
   - Extract customer info and issue
   - Search our knowledge base for solutions
   - Draft response template
4. Notify support manager via Slack
```

---

## 🎯 Tips for Effective Usage

### 1. Selector Strategy
```bash
# Good selectors (reliable)
"button[data-testid='submit-btn']"
"#main-navigation"
".product-price"

# Avoid (fragile)
"div > div > span:nth-child(3)"
```

### 2. Wait for Elements
```bash
# Always wait for dynamic content
"Wait for the search results to load, then extract the data"
```

### 3. Error Handling
```bash
# Include fallback instructions
"If the login button isn't found, look for 'Sign In' or 'Log In' text"
```

### 4. Batch Operations
```bash
# Process multiple items efficiently
"For each product in the list, extract name and price in one operation"
```

### 5. Screenshot Documentation
```bash
# Use screenshots for verification
"Take a screenshot after each major step to confirm success"
```

---

## 🔥 Power User Workflows

### 1. Automated Testing Pipeline
```
Create a testing workflow:
1. Navigate to our staging environment
2. Run through critical user journeys
3. Compare with production screenshots
4. Report any visual differences
5. Test form submissions and API responses
```

### 2. SEO Audit Automation
```
Perform comprehensive SEO audit:
1. Crawl all pages on our website
2. Check meta descriptions, titles, H1 tags
3. Test page load speeds
4. Verify mobile responsiveness
5. Generate SEO improvement report
```

### 3. Competitor Intelligence
```
Weekly competitor monitoring:
1. Check 5 competitor websites for new features
2. Monitor their blog for new content
3. Track their social media activity
4. Analyze their pricing changes
5. Compile intelligence briefing
```

### 4. Data Migration Assistant
```
Help migrate data between platforms:
1. Export data from old CRM
2. Format according to new system requirements
3. Import data in batches
4. Verify data integrity after each batch
5. Generate migration report
```

---

## 🚨 Best Practices & Limitations

### Do's ✅
- Start with simple workflows and build complexity
- Use descriptive prompts with step-by-step instructions
- Include error handling and fallback strategies
- Test workflows on different websites/environments
- Use screenshots for important verification steps

### Don'ts ❌
- Don't rely on fragile selectors
- Avoid overwhelming the browser with too many rapid actions
- Don't ignore CAPTCHA or anti-bot protections
- Don't scrape data without checking terms of service
- Avoid hardcoding sensitive information in prompts

### Limitations 🚧
- May struggle with complex CAPTCHA systems
- Single-threaded (one browser action at a time)
- Limited by website's anti-automation measures
- Requires stable internet connection
- JavaScript-heavy sites may need wait strategies

---

## 🎓 Learning Path

### Beginner (Week 1)
- Simple navigation and clicking
- Basic form filling
- Screenshot taking
- Text extraction

### Intermediate (Week 2-3)
- Multi-step workflows
- Data extraction and organization
- Error handling patterns
- File operations

### Advanced (Week 4+)
- Multi-server orchestration
- Complex business workflows
- Custom JavaScript execution
- Performance optimization

---

This MCP server essentially gives Claude "eyes and hands" for the web - it can see, click, type, and extract information from any website, making it incredibly powerful for automation!