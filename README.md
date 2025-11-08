# WordDice - Interactive Vocabulary Learning App

WordDice is a modern, interactive web application designed to help users learn and practice new vocabulary words through engaging exercises and real-time feedback.

## 🎯 Overview

WordDice presents users with random vocabulary words daily, complete with definitions, pronunciations, and example sentences. Users can practice using these words through three different interactive modes: repeating sentences, filling in blanks, and creating their own sentences.

## ✨ Features

### 📚 Word Display
- **Random Word Selection**: Fetches random words from a CSV file or default word list
- **Complete Word Information**: 
  - Word spelling
  - Phonetic pronunciation
  - Definition
  - Example sentence
- **Audio Pronunciation**: Click the audio button to hear the word pronounced
- **Smooth Transitions**: Beautiful fade-in/fade-out animations when loading new words

### 🎮 Practice Modes

#### 1. **Repeat Sentence Mode**
- Listen to an example sentence containing the word
- Practice pronunciation by repeating the sentence
- Uses browser's speech recognition to capture your speech
- Real-time feedback on your pronunciation

#### 2. **Fill in Blank Mode**
- View a sentence with a blank where the word should go
- Type the correct word to complete the sentence
- Instant feedback on correctness

#### 3. **Create Sentence Mode**
- Create your own sentence using the vocabulary word
- Type a complete sentence that includes the word
- Validation ensures the word is used correctly

### 🎨 Visual Features
- **Loading Animation**: Animated GIF displayed while fetching new words
- **Smooth Fade Transitions**: Gentle fade-in/fade-out effects when switching between words
- **Modern UI**: Clean, responsive design with gradient background
- **Mobile-Friendly**: Responsive layout that works on all devices

## 🚀 How It Works

### Word Loading Process

1. **Initial Load**:
   - App loads and displays a loading screen with animated GIF
   - Fetches word list from CSV file (if configured) or uses default word list
   - Selects a random word from the list
   - Fetches word details from Free Dictionary API
   - Displays word with smooth fade-in animation

2. **Loading New Word** (when clicking "Next Word"):
   - Current word fades out smoothly
   - Loading screen with GIF animation fades in
   - New random word is selected and fetched
   - Word details are fetched from API
   - New word fades in smoothly

### Data Sources

- **Word List**: 
  - Primary: CSV file from GitHub repository (configurable via `CSV_URL`)
  - Fallback: Built-in default word list
- **Word Definitions**: Free Dictionary API (`https://api.dictionaryapi.dev/api/v2/entries/en/`)
- **Example Sentences**: 
  - Primary: From API response
  - Enhanced: Generated using local LLM (GPT-2 via Transformers.js) when available

### Speech Recognition

- Uses Web Speech API (SpeechRecognition)
- Works best in Chrome and Edge browsers
- Automatically stops after 3 seconds of silence
- Provides real-time transcription feedback

## 📖 Usage Instructions

### Getting Started

1. **Open the Application**:
   - Simply open `index.html` in a modern web browser
   - No installation or setup required!

2. **View Today's Word**:
   - The app automatically loads a random word on page load
   - Review the word, pronunciation, definition, and example

3. **Listen to Pronunciation**:
   - Click the circular audio button to hear the word pronounced
   - Uses browser's built-in text-to-speech

4. **Practice Using the Word**:
   - Select one of three practice modes:
     - **Repeat Sentence**: Click record and repeat the example sentence
     - **Fill in Blank**: Type the word to complete the sentence
     - **Create Sentence**: Write your own sentence using the word

5. **Get Feedback**:
   - In Repeat mode: See your transcribed speech
   - In Fill mode: Get instant correct/incorrect feedback
   - In Create mode: Validation confirms word usage

6. **Load New Word**:
   - Click the "Next Word" button to load a new random word
   - Watch the smooth fade transition with loading animation

## 🔧 Technical Details

### Technologies Used

- **HTML5**: Structure and semantic markup
- **CSS3**: Styling with gradients, transitions, and responsive design
- **JavaScript (ES6+)**: Core functionality and interactivity
- **Web Speech API**: Speech recognition and synthesis
- **Transformers.js**: Local LLM for sentence generation (optional)
- **Free Dictionary API**: Word definitions and pronunciations

### Browser Requirements

- **Speech Recognition**: Chrome or Edge (recommended)
- **Modern Browser**: Supports ES6+ JavaScript
- **Microphone Access**: Required for speech practice features

### Configuration

To use your own word list, update the `CSV_URL` variable in the JavaScript:

```javascript
const CSV_URL = 'https://your-url-to-csv-file.csv';
```

The CSV file should contain words separated by commas or newlines.

### File Structure

```
WordDice/
├── index.html          # Main application file
├── README.md          # This documentation
└── CNAME              # Domain configuration (if using GitHub Pages)
```

## 🎯 Key Functions

### `loadNewWord()`
- Handles the complete word loading process
- Manages fade transitions between states
- Fetches word data from API
- Displays word information

### `fadeIn()` / `fadeOut()`
- Smooth transition helpers
- Control opacity and visibility
- Used for loading and word container animations

### `initializeSpeechRecognition()`
- Sets up Web Speech API
- Configures recognition parameters
- Handles speech events and transcription

### `generateExampleSentence()`
- Uses local LLM to create example sentences
- Enhances word learning experience
- Falls back to API examples if LLM unavailable

## 🌐 API Integration

### Free Dictionary API
- **Endpoint**: `https://api.dictionaryapi.dev/api/v2/entries/en/{word}`
- **Returns**: Word definitions, pronunciations, examples, and more
- **Rate Limit**: No official limit, but be respectful

## 🎨 Customization

### Changing the Loading GIF
Update the image source in the HTML:
```html
<img src="your-gif-url-here.gif" alt="Loading animation">
```

### Adjusting Transition Speed
Modify CSS transition durations:
```css
.loading {
    transition: opacity 0.4s ease-in-out; /* Adjust duration */
}

#word-container {
    transition: opacity 0.5s ease-in-out; /* Adjust duration */
}
```

### Styling
All styles are contained in the `<style>` tag within `index.html`. Modify colors, fonts, and layouts as needed.

## 📝 Notes

- The app works offline for basic functionality (using cached words)
- Internet connection required for fetching new word definitions
- Speech recognition requires microphone permissions
- Local LLM (Transformers.js) is optional and loads in the background

## 🚀 Deployment

### GitHub Pages
1. Push your code to a GitHub repository
2. Enable GitHub Pages in repository settings
3. Set source to `main` branch
4. Your app will be live at `https://yourusername.github.io/WordDice/`

### Other Hosting
Simply upload `index.html` to any web hosting service. No build process required!

## 📄 License

This project is open source and available for personal and educational use.

## 🤝 Contributing

Feel free to fork, modify, and improve this application. Suggestions and contributions are welcome!

---

**Enjoy learning new words with WordDice! 🎲📚**

