# LPV - Live Video Wallpaper

A Python-based application to set a video as your Windows desktop wallpaper. This project leverages PyQt5, ffpyplayer, and the Windows API to provide a seamless experience of playing videos directly on your desktop background.

## Features

- **Live Video Wallpaper**: Play a video as your desktop background.
- **Command Interface**: Control playback via command-line input (play, pause, volume control, frame rate adjustments, etc.).
- **Auto Looping**: Videos automatically loop when they reach the end.
- **Volume and Frame Rate Control**: Dynamically adjust video volume and frame rate through commands.
- **Wallpaper Restoration**: Automatically restores the original wallpaper when the video stops or the application exits.

## Requirements

- Python 3.x
- PyQt5
- ffpyplayer
- Pillow (PIL)
- Windows OS (uses Windows APIs and registry to set and restore wallpapers)

## Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/NSTechBytes/Lpv.git
   ```

2. Install the required Python packages:

   ```bash
   pip install -r requirements.txt
   ```

3. Ensure you are running on a Windows environment since this project uses the Windows API to manage wallpapers.

## Usage

To run the application and set a video as wallpaper:

```bash
python lpv.py <path_to_video_file>
```

### Available Commands

Once the application is running, you can use the following commands via stdin to control playback:

- **play**: Resume video playback and restore audio.
- **pause**: Pause video playback and mute audio.
- **volume `<level>`**: Adjust the volume (e.g., `volume 0.5` sets the volume to 50%).
- **frames `<rate>`**: Adjust the frame rate (e.g., `frames 30` sets the playback to 30 fps).
- **remove**: Remove the video wallpaper and restore the original wallpaper.
- **exit**: Exit the application and restore the original wallpaper.

### Example

To set a video located at `C:\Videos\myvideo.mp4` as your wallpaper, run:

```bash
python lpv.py "C:\Videos\myvideo.mp4"
```

Once the application is running, you can control playback by typing commands in the terminal, like:

```bash
play
pause
volume 0.8
frames 60
remove
exit
```

## How It Works

- The script uses **PyQt5** to create a windowless desktop overlay that displays the video.
- **ffpyplayer** handles video playback, while **Pillow** processes video frames for rendering as QPixmap images.
- The app interacts with the Windows **WorkerW** window to set the video beneath the icons on the desktop.
- Commands can be issued through stdin to control the video playback, including play, pause, volume, and frame rate adjustments.
- When the app exits, the original desktop wallpaper is restored automatically.

## Contributing

If you’d like to contribute to this project, feel free to open issues or submit pull requests. Any contributions are welcome!

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

