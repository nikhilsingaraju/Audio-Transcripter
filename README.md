# Audio-Transcripter
This program is designed to download audio from a YouTube video, transcribe the audio using the OpenAI Whisper ASR (Automatic Speech Recognition) model, and save the transcriptions to a CSV file. It utilizes the `yt-dlp` library to download the audio and the `openai-whisper` library for speech transcription.

The program begins by installing the necessary libraries `openai-whisper` and `yt-dlp` using the `%pip install` commands.

Next, it imports the required modules and sets up the YouTube downloader settings (`YDL_OPTS`) for downloading the best audio quality from a given YouTube URL. The audio is post-processed using FFmpeg to extract the audio and convert it to MP3 format with a preferred quality of 192. Additionally, the audio sampling rate is set to 16kHz, which is suitable for the Whisper model.

The program defines three main functions:
1. `download_audio`: This function takes a filename and a YouTube URL as inputs and uses `yt-dlp` to download the audio from the YouTube video and save it as the specified filename.
2. `transcribe_audio`: This function takes an audio file path as input and uses the Whisper ASR model to transcribe the audio. It loads the pre-trained Whisper model and suppresses warnings related to FP16 (16-bit floating-point) usage.
3. `save_transcriptions`: This function takes the transcription result and an output file path as inputs. It saves the transcriptions, including the start time, end time, and corresponding text, to a CSV file.

The program then prompts the user to upload an audio file. It uses the `files.upload()` function from Google Colab to upload the file and stores the uploaded filename.

After that, it downloads the audio from a specified YouTube URL using the `download_audio` function.

Next, it transcribes the downloaded audio using the `transcribe_audio` function, which returns the transcription result.

The program saves the transcriptions to a CSV file using the `save_transcriptions` function.

Finally, it displays a download link to the generated CSV file using the `FileLink` function from the IPython.display module.

Overall, this program provides a convenient way to download audio from YouTube, transcribe it using the OpenAI Whisper ASR model, and save the transcriptions in a CSV file. It leverages the capabilities of `yt-dlp` and `openai-whisper` libraries to simplify the process of audio transcription from YouTube videos.
