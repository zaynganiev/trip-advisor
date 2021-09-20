# trip-advisor
my first python learning project

```javascript
dialogflowService.on("interrupted", transcript => {
    console.log(`Interrupted with "${transcript}"`);
    mediaStream.pause();
    const twiml = new Twilio.twiml.VoiceResponse();
    const gather = twiml.gather({
      numDigits: 1,
      input: "speech, dtmf",
    });
    gather.say('Enter your SSN');
    client.calls(callSid).update({
      twiml: gather.toString(),
    });
    mediaStream.resume();
    if (!dialogflowService.isInterrupted) {
      console.log("Clearing...");
      const clearMessage = {
        event: "clear",
        streamSid
      };
      mediaStream.write(JSON.stringify(clearMessage));
      dialogflowService.isInterrupted = true;
    }
  });
  ```
