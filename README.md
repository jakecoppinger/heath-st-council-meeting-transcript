Heath St Canada Bay Council Meeting Transcript
==============================================

AI Generated text transcript of the Tuesday 28th March City of Canada Bay Council Meeting.

Raw output is it `/raw-transcript.tsv`. Cleaned up output at `/transcript.tsv`.

PRs welcome improving `/transcript.tsv`!

# Method

- Download video of meeting from https://www.facebook.com/canadabay/videos/1404568383639112/ (I'm iunaware of official uploads elsewhere)
- Trim video to segment about the cycleway (from about 1:05)
- Convert video to mp3:

```
ffmpeg -i input.mp4  -vn -b:a 128k output.mp3
```
- Run Docker container with OpenAI Whisper AI text transcription (open source) with `medium` model

```
docker run -d -p 9000:9000 -e ASR_MODEL=medium onerahmet/openai-whisper-asr-webservice:latest
```

- Use the `/asr` endpoint on http://localhost:9000/ to transcribe the `mp3` (overnight, takes a while!)

