# 🎯 Script Execution Guide: Ultimate LLM Scraper

## 🚀 Quick Start Commands

### Basic Execution
```bash
python ultimate_scraper.py
```
This launches the interactive menu where you can select different scraping modes.

### Direct Mode Execution
```bash
# Test run (5 minutes, sample data)
python ultimate_scraper.py --mode test

# Fast collection (1 hour, GitHub + HF + Academic)
python ultimate_scraper.py --mode fast

# Comprehensive (2-4 hours, all platforms)
python ultimate_scraper.py --mode comprehensive

# GitHub only (30 minutes)
python ultimate_scraper.py --mode github

# Qwen focused (45 minutes)
python ultimate_scraper.py --mode qwen
```

## 📋 Interactive Menu Options

When you run `python ultimate_scraper.py`, you'll see:

```
🚀 Ultimate Multi-Platform LLM Contributors Scraper
Combines GitHub, HuggingFace, Twitter, Academic Papers, Reddit
================================================================================

Execution modes:
1. Comprehensive collection (all platforms, ~2-4 hours)
2. Fast collection (GitHub + HuggingFace + Academic, ~1 hour)
3. GitHub only (fastest, ~30 minutes)
4. Qwen focused (Qwen repos + HF Qwen models, ~45 minutes)
5. Test run (sample data, ~5 minutes)

Select mode (1-5) [default: 2]:
```

## 🎛️ Detailed Mode Explanations

### Mode 1: Comprehensive Collection
**Duration:** 2-4 hours  
**Contacts:** 2,000-5,000  
**Platforms:** All (GitHub, HuggingFace, Academic, Twitter, Reddit)

```bash
What it does:
✅ Scrapes 50+ GitHub repositories
✅ Processes 300+ academic papers
✅ Extracts HuggingFace model authors
✅ Discovers Twitter LLM community
✅ Finds Reddit contributors
✅ Full enrichment and scoring
✅ Real-time Google Sheets upload
```

**Best for:** Initial database building, monthly refreshes

### Mode 2: Fast Collection (Default)
**Duration:** 1 hour  
**Contacts:** 1,000-2,000  
**Platforms:** GitHub, HuggingFace, Academic

```bash
What it does:
✅ Scrapes 25 top GitHub repositories
✅ Processes 100 academic papers
✅ Extracts top HuggingFace models
✅ Quick enrichment and scoring
✅ Real-time Google Sheets upload
❌ Skips Twitter and Reddit
```

**Best for:** Regular updates, weekly runs

### Mode 3: GitHub Only
**Duration:** 30 minutes  
**Contacts:** 500-1,500  
**Platforms:** GitHub only

```bash
What it does:
✅ Scrapes 20 GitHub repositories
✅ Focuses on high-activity repos
✅ Quick enrichment and scoring
✅ Real-time Google Sheets upload
❌ Skips all other platforms
```

**Best for:** Developer-focused outreach, quick updates

### Mode 4: Qwen Focused
**Duration:** 45 minutes  
**Contacts:** 300-800  
**Platforms:** Qwen ecosystem

```bash
What it does:
✅ All Qwen GitHub repositories
✅ Qwen-related HuggingFace models
✅ Qwen academic papers
✅ Priority scoring for Qwen contributors
✅ Real-time Google Sheets upload
```

**Best for:** Qwen ecosystem engagement, targeted campaigns

### Mode 5: Test Run
**Duration:** 5 minutes  
**Contacts:** 10-20  
**Platforms:** Sample from GitHub

```bash
What it does:
✅ Scrapes 2 repositories (3 contributors each)
✅ Basic enrichment
✅ Sample Google Sheets upload
✅ Tests all API connections
```

**Best for:** Setup validation, API testing

## 🔧 Command Line Arguments

### Advanced Usage
```bash
# Set custom contact limits
python ultimate_scraper.py --mode fast --max-contacts 500

# Specify custom repositories
python ultimate_scraper.py --mode github --repos "unslothai/unsloth,karpathy/nanoGPT"

# Custom output file
python ultimate_scraper.py --mode test --output custom_contacts.csv

# Enable debug logging
python ultimate_scraper.py --mode fast --debug

# Dry run (no Google Sheets upload)
python ultimate_scraper.py --mode test --dry-run

# Resume from checkpoint
python ultimate_scraper.py --mode comprehensive --resume
```

### Environment-specific Execution
```bash
# Production environment
ENVIRONMENT=production python ultimate_scraper.py --mode comprehensive

# Development with verbose logging
LOG_LEVEL=DEBUG python ultimate_scraper.py --mode test

# Custom Google Sheet
SHEET_NAME="Custom Contact List" python ultimate_scraper.py --mode fast
```

## 📊 Output and Results

### Console Output Example
```bash
🚀 Starting Ultimate Multi-Platform LLM Collection
📅 Mode: fast
📊 Existing: 1,247 URLs, 892 usernames

============================================================
PHASE 1: GitHub Repository Scraping
============================================================
Scraping QwenLM/Qwen2.5-Coder (qwen_ecosystem)
Scraping unslothai/unsloth (fine_tuning)
Scraping mistralai/Mistral-src (llm_development)
💾 Checkpoint saved: checkpoints/github_ultimate_20241215_143022.json
📊 GitHub: 847 contacts

============================================================
PHASE 2: HuggingFace Model Hub Scraping
============================================================
Searching HF for: Qwen
Searching HF for: LLM
💾 Checkpoint saved: checkpoints/huggingface_ultimate_20241215_143845.json
📊 HuggingFace: 234 contacts

============================================================
PHASE 3: Academic Research Scraping
============================================================
Searching papers for: Qwen
Searching papers for: LLM
💾 Checkpoint saved: checkpoints/academic_ultimate_20241215_144201.json
📊 Academic: 156 contacts

============================================================
PHASE 5: Scoring, Deduplication & Upload
============================================================
🔍 Performing advanced deduplication...
📊 Deduplication: 1,237 → 1,089 unique contacts
💾 Local backups saved: ultimate_llm_contacts_20241215_144523.csv

================================================================================
🎉 ULTIMATE COLLECTION COMPLETE
================================================================================
📊 Total unique contacts: 1,089
⏱️  Duration: 67.3 minutes
💾 Uploaded to: OptiML Hiring Contacts

📈 Summary by platform:
  github         :  847 ( 77.8%)
  huggingface    :  234 ( 21.5%)
  academic       :  156 ( 14.3%)

🎯 Summary by technical focus:
  fine_tuning         :  412 ( 37.8%)
  llm_development     :  298 ( 27.4%)
  qwen_ecosystem      :  203 ( 18.6%)
  model_compression   :  176 ( 16.2%)

📊 Quality metrics:
  With email:     432 ( 39.7%)
  With LinkedIn:  678 ( 62.3%)
  With Twitter:   534 ( 49.0%)
  High score:     287 ( 26.4%)

🏆 TOP 15 CONTACTS BY HIRE SCORE:
 1. Daniel Han             Score:  9.2 📧💼🐦 github       (fine_tuning)
 2. Tim Dettmers           Score:  8.8 📧💼❌ github       (model_compression)
 3. Edward Hu              Score:  8.5 📧💼🐦 github       (fine_tuning)
 4. Susan Zhang            Score:  8.1 ❌💼🐦 huggingface  (qwen_ecosystem)
...
```

### Generated Files
```bash
# Main output file
ultimate_llm_contacts_20241215_144523.csv

# JSON backup with full data
ultimate_llm_contacts_20241215_144523.json

# Checkpoint files (for resuming)
checkpoints/github_ultimate_20241215_143022.json
checkpoints/huggingface_ultimate_20241215_143845.json
checkpoints/academic_ultimate_20241215_144201.json

# Log file
ultimate_scraper_20241215.log
```

## 🔄 Scheduling & Automation

### Cron Job Examples
```bash
# Daily Qwen monitoring (10 AM)
0 10 * * * cd /path/to/scraper && python ultimate_scraper.py --mode qwen --quiet

# Weekly fast updates (Sunday 6 AM)  
0 6 * * 0 cd /path/to/scraper && python ultimate_scraper.py --mode fast --quiet

# Monthly comprehensive (1st of month, 2 AM)
0 2 1 * * cd /path/to/scraper && python ultimate_scraper.py --mode comprehensive --quiet

# Daily GitHub monitoring for high-priority repos
0 14 * * * cd /path/to/scraper && python ultimate_scraper.py --mode github --repos "QwenLM/Qwen2.5,unslothai/unsloth" --min-score 7.0
```

### Systemd Service (Linux)
```bash
# Create service file: /etc/systemd/system/llm-scraper.service
[Unit]
Description=LLM Scraper Daily Run
After=network.target

[Service]
Type=oneshot
User=your_username
WorkingDirectory=/path/to/scraper
ExecStart=/usr/bin/python3 ultimate_scraper.py --mode fast --quiet
Environment=PYTHONPATH=/path/to/scraper

[Install]
WantedBy=multi-user.target

# Create timer: /etc/systemd/system/llm-scraper.timer
[Unit]
Description=Run LLM Scraper Daily
Requires=llm-scraper.service

[Timer]
OnCalendar=daily
Persistent=true

[Install]
WantedBy=timers.target

# Enable and start
sudo systemctl enable llm-scraper.timer
sudo systemctl start llm-scraper.timer
```

## 🛠️ Advanced Configuration

### Custom Repository Lists
```python
# Edit ultimate_scraper.py - PLATFORM_CONFIGS section
CUSTOM_REPOS = [
    "your-org/custom-llm-repo",
    "another-org/ml-project",
    "research-lab/new-architecture"
]

# Add to qwen_priority or create new category
"custom_category": {
    "repos": CUSTOM_REPOS,
    "focus": "custom_focus",
    "priority_multiplier": 1.5
}
```

### Custom Scoring Weights
```python
# Edit calculate_enhanced_hire_score() function
def calculate_enhanced_hire_score(contributor):
    score = 0
    
    # Custom weights
    EMAIL_WEIGHT = 5      # Increase email importance
    LINKEDIN_WEIGHT = 3   # Increase LinkedIn importance
    TWITTER_WEIGHT = 1    # Keep Twitter weight low
    
    # Custom scoring logic
    if contributor.get("company") in ["OpenAI", "Anthropic", "Hugging Face"]:
        score += 2  # Bonus for target companies
    
    return score
```

### Custom Google Sheets Tabs
```python
# Edit SHEET_TABS in ultimate_scraper.py
SHEET_TABS = {
    "custom_category": "Custom LLM Developers",
    "high_priority": "High Priority Contacts (Score > 8)",
    "regional_focus": "Contacts in Target Regions",
    # ... add your custom tabs
}
```

## 📈 Monitoring and Optimization

### Performance Monitoring
```bash
# Monitor resource usage during execution
top -p $(pgrep -f ultimate_scraper.py)

# Check memory usage
ps aux | grep ultimate_scraper.py

# Monitor network connections
netstat -an | grep :443  # HTTPS connections
```

### Log Analysis
```bash
# Monitor real-time logs
tail -f ultimate_scraper_$(date +%Y%m%d).log

# Count contacts by platform
grep "Found.*contacts" ultimate_scraper_*.log

# Check for errors
grep "ERROR\|Failed" ultimate_scraper_*.log

# API rate limiting analysis
grep "Rate limited\|429\|403" ultimate_scraper_*.log
```

### Performance Optimization
```bash
# Increase parallel processing (edit script)
MAX_WORKERS = 10  # Default is 5

# Reduce rate limiting delays
time.sleep(0.5)  # Reduce from 1 second

# Use SSD storage for checkpoints
CHECKPOINT_DIR = "/fast-storage/checkpoints"
```

## 🚨 Error Handling and Recovery

### Common Error Scenarios

#### 1. API Rate Limiting
```bash
Error: 403 API rate limit exceeded
Recovery: Script automatically waits and retries
Manual: Add more GitHub tokens or increase delays
```

#### 2. Network Interruption
```bash
Error: Connection timeout
Recovery: Script resumes from last checkpoint
Manual: python ultimate_scraper.py --mode [mode] --resume
```

#### 3. Google Sheets Quota
```bash
Error: Quota exceeded
Recovery: Script waits and retries with exponential backoff
Manual: Reduce batch sizes or use multiple sheets
```

#### 4. Memory Issues
```bash
Error: Memory allocation failed
Recovery: Process in smaller batches
Manual: Increase system RAM or reduce MAX_CONTACTS
```

### Recovery Commands
```bash
# Resume from checkpoint
python ultimate_scraper.py --mode comprehensive --resume

# Start from specific platform
python ultimate_scraper.py --mode fast --start-from huggingface

# Skip problematic repositories
python ultimate_scraper.py --mode github --exclude-repos "large-repo,problematic-repo"

# Reduce memory usage
python ultimate_scraper.py --mode fast --batch-size 50 --max-workers 3
```

## 🎯 Success Metrics

### Immediate Success Indicators
- [ ] Script completes without errors
- [ ] Google Sheets populated with new contacts
- [ ] Checkpoint files created successfully
- [ ] Log file shows expected contact counts

### Quality Metrics
- [ ] 30%+ contacts have email addresses
- [ ] 50%+ contacts have LinkedIn profiles
- [ ] 20%+ contacts have hire score > 5.0
- [ ] Deduplication reduces contacts by 10-20%

### Performance Benchmarks
- [ ] GitHub: 20-30 contacts per minute
- [ ] HuggingFace: 10-15 contacts per minute
- [ ] Academic: 5-10 contacts per minute
- [ ] Memory usage stays under 2GB

**🚀 Ready to execute your first scrape? Start with Mode 5 (test run) to validate your setup!**