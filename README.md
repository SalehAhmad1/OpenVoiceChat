# Voice Chat

Trying to create a pipeline where I can talk to an LLM.

STT + LLM + TTS

## What models should be used?

| STT | TTS | LLM |
| --- | --- | --- |
| [VITS](https://jaywalnut310.github.io/vits-demo/index.html) | [Whisper](https://github.com/openai/whisper) | [gpt-neo](https://huggingface.co/EleutherAI/gpt-neo-2.7B) atm |

Using [M4T](https://github.com/facebookresearch/seamless_communication) one model can do stt + tts + translation.
The translation [quality is almost](./media/translation_quality.png) there.


## TODO:
- [x] ~~Fix LLM log (or atleast test it to make sure it works)~~ seems to work
- [ ] Handle interruptions
- [ ] Better LLM prompt


## Notes
How to handle interruptions? We constantly listen and transcribe and then stop tts. TTS has to stop on a word to make it natural. 
Also do we even stop. Sometimes the other person just says "yes" or "yeah". The stop recording policy is bad, it just stops recording after x
number of silent seconds. There should be an EOS predictor for whisper and we should stop using it, this will allow having pauses in the middle.