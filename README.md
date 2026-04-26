# 🎙️ AuctionScribe

**AI-powered auction transcription with Excel export**

AuctionScribe transcribes live or recorded auction audio using either Deepgram or AssemblyAI, then exports a formatted Excel workbook with full transcript, speaker summary, and raw data sheets.

---

## Features

- **Live mic recording** — real-time transcription via Deepgram WebSocket (sub-300ms latency)
- **File upload** — transcribe MP3, WAV, M4A, OGG, MP4, WEBM via Deepgram or AssemblyAI
- **Speaker identification** — automatically labels each speaker (Speaker 1, Speaker 2, etc.)
- **Excel export** — 3-sheet workbook: Transcript, Speaker Summary, Raw Data
- **Auction metadata** — attach auction name, date, location, and auctioneer to every export
- **No backend required** — pure browser app, API keys never leave your machine

---

## Quick Start

1. **Clone the repo**
   ```bash
   git clone https://github.com/YOUR_USERNAME/auction-transcriber.git
   cd auction-transcriber
   ```

2. **Open the app**
   ```bash
   # Option A: Open directly in browser
   open index.html

   # Option B: Serve locally (recommended for mic access in some browsers)
   npx serve .
   # or
   python3 -m http.server 8080
   ```

3. **Get an API key**
   - **Deepgram**: Sign up at [deepgram.com](https://deepgram.com) — $200 free credit, no credit card required
   - **AssemblyAI**: Sign up at [assemblyai.com](https://assemblyai.com) — $50 free credit

4. **Paste your API key** into the app and start transcribing

---

## Service Comparison

| Feature | Deepgram | AssemblyAI |
|---|---|---|
| Base price | $0.0077/min | $0.0025/min |
| Real-time (live mic) | ✅ Yes | ⚠️ File upload only in this app |
| File upload | ✅ Yes | ✅ Yes |
| Speaker ID | ✅ Included | ⚠️ +$0.02/hr |
| Free tier | $200 credit | $50 credit |
| Best for | Live auctions | Recorded files |

---

## Excel Output

Each export produces a `.xlsx` file with three sheets:

### Sheet 1 — Transcript
Full formatted transcript with auction metadata header, timestamps, speaker labels, and word counts.

### Sheet 2 — Speaker Summary
Per-speaker breakdown: line count, total words, and percentage of conversation.

### Sheet 3 — Raw Data
Clean tabular data for further analysis or import into other systems.

---

## Supported Audio Formats

MP3, WAV, M4A, OGG, FLAC, MP4, WEBM, and most common audio/video formats.

---

## Privacy & Security

- Your API key is stored in your browser's memory only during the session
- Audio is sent directly from your browser to Deepgram or AssemblyAI — it does not pass through any intermediate server
- No data is stored or logged by this application

---

## Usage Tips for Auction Audio

- **Position mic close** to the auctioneer for best accuracy
- **Add custom vocabulary** in Deepgram's console for auction-specific terms (lot numbers, item names)
- For multi-auctioneer sessions, speaker diarization will label each voice separately
- Use **File mode** for post-auction review of recorded sessions

---

## Tech Stack

- Vanilla HTML/CSS/JavaScript — no build step, no dependencies to install
- [SheetJS (xlsx)](https://sheetjs.com/) for Excel generation
- Deepgram WebSocket API for real-time streaming
- AssemblyAI REST API for file transcription

---

## License

MIT
