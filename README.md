# eBay Sniper Bot

eBay Sniper Bot is a Python-based automation tool designed to help users win eBay auctions by placing bids at the optimal moment - just 1 second before the auction ends. The bot uses DrissionPage to control a Chromium browser instance, allowing for precise timing and human-like interaction with eBay's interface.

The tool is particularly useful for competitive auctions where manual bidding might be too slow or imprecise. It pre-positions the cursor on the confirmation button and executes the bid at the exact specified time.

## Features

- **Precision Timing**: Execute bids with second-level accuracy
- **Browser Automation**: Uses DrissionPage for reliable web interaction
- **Manual Setup**: Allows manual login and bid amount entry for security
- **Headless Option**: Can run with or without visible browser window
- **Performance Optimized**: Disables images and audio for faster loading
- **Italian eBay Support**: Currently configured for eBay.it

## Requirements

- Python 3.7+
- Chrome/Chromium browser installed
- Active eBay account
- Stable internet connection

## Installation

1. Clone the repository:
```bash
git clone https://github.com/VincenzoImp/ebay-sniper-bot.git
cd ebay-sniper-bot
```

2. Create a virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

## Usage

### Basic Setup

1. **Start Jupyter Notebook**:
```bash
jupyter notebook
```

2. **Open the bidder.ipynb file**

3. **Configure your target time**:
```python
# Set execution time (1 second before auction end)
ora_esecuzione = "18:19:59"  # HH:MM:SS format
```

### Step-by-Step Process

1. **Initialize the browser**:
   - Run the first few cells to set up the driver
   - The browser will open automatically

2. **Manual login**:
   - Navigate to eBay and log into your account manually
   - Go to the auction page you want to bid on
   - Enter your maximum bid amount
   - **DO NOT click the final confirmation button**

3. **Prepare for sniping**:
   - The bot will move the cursor to the confirmation button
   - Set your target execution time
   - Run the final cell to start the timer

4. **Automated execution**:
   - The bot will wait until the specified time
   - At the exact moment, it will click the confirmation button
   - Your bid will be placed automatically

## Configuration Options

### Browser Settings
```python
driver = open_drission_driver(
    headless=False,    # Set to True for invisible browser
    no_imgs=True,      # Disable image loading for speed
    no_audio=True,     # Disable audio
    singleton_tab_obj=False
)
```

### Timing Configuration
```python
# Adjust timing based on your needs
ora_esecuzione = "HH:MM:SS"  # Target execution time
```

## Important Notes

### Legal and Ethical Considerations
- This tool is for educational purposes
- Ensure compliance with eBay's Terms of Service
- Use responsibly and ethically
- The author is not responsible for any violations or consequences

### Technical Limitations
- Requires stable internet connection
- System clock must be accurate
- eBay's interface changes may require code updates
- Currently optimized for eBay.it (Italian version)

### Security
- Manual login prevents storing credentials in code
- Browser session is isolated
- No sensitive data is logged

## Troubleshooting

### Common Issues

**Browser doesn't start:**
- Ensure Chrome/Chromium is installed
- Check if browser path is correct
- Try running with `headless=False`

**Timing is off:**
- Synchronize your system clock
- Account for network latency
- Test with non-critical auctions first

**Element not found:**
- eBay may have changed their interface
- Check the element selector `#confirmBid`
- Update selectors if necessary

**Connection issues:**
- Ensure stable internet connection
- Check if eBay is accessible
- Verify account login status

## File Structure

```
ebay-sniper-bot/
├── .gitignore          # Git ignore file
├── bidder.ipynb        # Main Jupyter notebook
├── requirements.txt    # Python dependencies
└── README.md          # This file
```

## Dependencies

Key dependencies include:
- `DrissionPage==4.1.0.7` - Browser automation framework
- `jupyter` - Notebook interface
- `requests==2.32.3` - HTTP library
- `lxml==5.3.0` - XML/HTML processing
- `websocket-client==1.8.0` - WebSocket support

See `requirements.txt` for complete list.

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## Disclaimer

This software is provided "as is" without warranty of any kind. The author assumes no responsibility for:
- Any violations of eBay's Terms of Service
- Financial losses from failed bids
- Technical issues or malfunctions
- Legal consequences of usage

Use at your own risk and ensure compliance with all applicable terms and conditions.

## License

This project is for educational purposes only. Users are responsible for ensuring their usage complies with eBay's Terms of Service and applicable laws.

---

**Note**: Always test with small, non-critical auctions before using for important bids. The timing and reliability depend on various factors including internet connection, system performance, and eBay's server response times.
