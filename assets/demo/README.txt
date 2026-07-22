The four demo recordings, and how they were made (22 Jul 2026)

  appointment-de.mp3  36s  AI voice: Telnyx.Ultra Lukas  - the LIVE agent voice
  appointment-en.mp3  37s  AI voice: Telnyx.Ultra Clara  - the LIVE agent voice
  appointment-fr.mp3  38s  AI voice: AWS.Polly.Lea-Neural    (native French)
  appointment-it.mp3  43s  AI voice: AWS.Polly.Bianca-Neural (native Italian)

Rendered through Telnyx's own text-to-speech API (the engine the receptionist
runs on), stitched with ffmpeg, 350ms gaps, 24kHz mono 64kbps. The AI's opening
line in each is the EXACT disclosure sentence from server/compliance.py -
the demo says precisely what the product says, including "KI-Assistentin".
Caller side is a second synthetic voice (Polly Daniel/Remi/Adriano/Matthew).
The site caption calls this what it is: re-enacted example call, real voices.

PARITY - so live French/Italian callers hear the SAME voices as the demo, set
in Render (mechanism shipped in the app, commit 8f33fae):

  CA_VOICE_FR = AWS.Polly.Lea-Neural
  CA_VOICE_IT = AWS.Polly.Bianca-Neural

then make ONE test call in each language: the assistant's voice field is
expected to accept Polly ids like the TTS API does, but that has not been
proven on a live call yet. de/en need nothing - the demo already uses the
live agent voices.

To re-record: the script that generated these lives in the session scratchpad;
ask Claude to regenerate with new wording, or use the Telnyx portal preview.
