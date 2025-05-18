# Emotion Tracker Desktop App (v3.10.3)

**Track, understand, and visualize your emotional landscape with this feature-rich desktop application.**

This Python-based Emotion Tracker, envisioned and inspired by **stelliro** and assisted in development by Gemini, allows you to log your feelings with intensity and optional notes. It then provides insightful visualizations to help you identify patterns and trends over time. Built with CustomTkinter for a modern user interface and Matplotlib for dynamic charting, it offers a personalized and visually appealing experience.

<!--
Consider adding a screenshot or a short GIF of your app in action here!
Example:
<p align="center">
  <img src="docs/screenshot.png" width="600">
</p>
-->

## Key Features:

*   **Intuitive Emotion Logging:**
    *   Select from a customizable list of emotions.
    *   Set an intensity level (1-5) for each entry.
    *   Add optional notes for context.
*   **Flexible Data Viewing:**
    *   View your emotion logs for "Today," "Yesterday," "Last 7 Days," or "All Time."
*   **Insightful Visualizations:**
    *   **Intensity Trend Chart:** See how your emotions (and their intensities) fluctuate over time.
        *   Filter the trend chart by a specific emotion.
        *   Data points are colored according to the emotion for easy identification.
        *   Dynamically generated legend for "All Emotions" view.
    *   **Emotion Frequency Pie Chart:** Get a clear breakdown of how often you experience different emotions.
*   **Customizable Experience:**
    *   **Personalized Emotion List:** Add, remove, and manage your own list of emotions.
    *   **Appearance Modes:** Choose between "System," "Light," and "Dark" themes. Matplotlib charts adapt to the selected theme!
    *   **Logging Reminders:**
        *   Set reminders at customizable intervals (e.g., 15 min, 1 hour, custom values).
        *   Option to play a custom sound (.wav or .mp3) for reminders.
        *   Toggle visual reminder popups.
    *   **Data Storage:** Specify a custom directory for storing your emotion log data.
*   **Persistent Settings:** All your customizations (theme, emotions, reminders, paths) are saved locally in an `app_settings.json` file.
*   **Local Data Storage:** Emotion logs are stored in daily CSV files (`YYYY-MM-DD_emotions.csv`) in your chosen data directory, ensuring privacy and easy access.
*   **Performance Optimized:** Includes theme color caching for smoother UI performance on desktop.
*   **Changelog & Credits:** In-app section to track updates and acknowledge contributions.

## Technologies Used:

*   **Python 3**
*   **CustomTkinter:** For the modern graphical user interface.
*   **Matplotlib:** For generating interactive charts.
*   **Pandas:** For efficient data manipulation and analysis.
*   **Playsound (Optional):** For custom reminder sounds.
*   Standard Python libraries: `csv`, `os`, `glob`, `json`, `datetime`, `threading`, `re`.
*   Packaged into an executable using a tool like PyInstaller or auto-py-to-exe.

## How it Works:

The application allows users to input their current emotion, its intensity, and an optional note. This data is timestamped and saved into a CSV file corresponding to the current date. Users can then view this data aggregated over various periods. Matplotlib is used to render an intensity trend line chart (showing intensity over time, with individual emotion points colored) and an emotion frequency pie chart. All settings, including the list of available emotions, reminder preferences, and appearance, are configurable through a dedicated settings window and stored in a JSON file.

## Getting Started:

### For Users (Using the Executable):

1.  Download the `EmotionTracker.exe` (or the specific `.exe` file for the latest version) from the **[Releases page](https://github.com/Stelliro/Emotion-Tracker/releases)**.
2.  Simply run the downloaded executable file. No installation of Python or any libraries is required.
3.  On first run, or if not configured, the app will typically create an `Emotion_Logs` directory (or use the one you specify in settings) in the same folder as the executable (or your user's AppData, depending on how it was packaged) to store data, and an `app_settings.json` file for your preferences.

### For Developers (Running from Source):

1.  Clone this repository to your local machine:
    ```bash
    git clone https://github.com/Stelliro/Emotion-Tracker.git
    cd Emotion-Tracker
    ```
2.  Ensure you have Python 3 installed (Python 3.7+ recommended).
3.  It's highly recommended to create and activate a virtual environment:
    ```bash
    python -m venv venv
    # On Windows
    venv\Scripts\activate
    # On macOS/Linux
    # source venv/bin/activate
    ```
4.  Install the required libraries:
    ```bash
    pip install customtkinter matplotlib pandas playsound
    ```
    *(Note: `playsound` is optional; the app will function without it from source, but custom sound reminders won't work unless the library is present and functional. On Linux, you might need to install additional dependencies for `playsound` like `python3-gst-1.0` or `gstreamer1.0-plugins-good`.)*
5.  Run the main Python script:
    ```bash
    python Emotion_Tracker.py
    ```

## Building the Executable (for Developers):

If you want to build the executable yourself, you can use a tool like PyInstaller:

1.  Ensure PyInstaller is installed in your virtual environment:
    ```bash
    pip install pyinstaller
    ```
2.  Navigate to your project directory in the terminal.
3.  Run PyInstaller. You might need to include data files (like icons or default settings) or specify hidden imports if your application uses them.
    A basic command would be:
    ```bash
    pyinstaller --name EmotionTracker --onefile --windowed Emotion_Tracker.py
    ```
    <!-- You may need additional flags, e.g., --add-data for assets or --icon=your_icon.ico. -->
    <!-- Check the PyInstaller documentation for more advanced usage. -->

## Distribution:

This application is distributed as a standalone executable (`.exe` for Windows). You can find the latest version and older releases on the **[Releases page](https://github.com/Stelliro/Emotion-Tracker/releases)**.

## Contributing:

Contributions are welcome! If you have suggestions for improvements or bug fixes, please feel free to:

1.  Fork the repository (`https://github.com/Stelliro/Emotion-Tracker/fork`).
2.  Create a new branch (`git checkout -b feature/AmazingFeature`).
3.  Make your changes.
4.  Commit your changes (`git commit -m 'Add some AmazingFeature'`).
5.  Push to the branch (`git push origin feature/AmazingFeature`).
6.  Open a Pull Request.

## License:

<!--
IMPORTANT: You need to choose a license for your project!
Common choices include MIT, Apache 2.0, GPLv3.
Once you choose one, create a `LICENSE` or `LICENSE.md` file in your repository
with the full text of the license, and then update the line below.
-->
This project is licensed under the [Your Chosen License Here] - see the `LICENSE.md` file for details.
*Example: This project is licensed under the MIT License - see the `LICENSE.md` file for details.*

## Acknowledgements:

*   **stelliro:** For the original vision, inspiration, and guidance for this application.
*   **Google Gemini:** For assistance in code generation, refinement, and documentation.
*   The **CustomTkinter** library for making modern GUIs in Python easy.
*   **Matplotlib** for powerful plotting capabilities.
*   **Pandas** for efficient data handling.
