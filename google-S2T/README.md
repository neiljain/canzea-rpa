



# Export token created from google

export GOOGLE_APPLICATION_CREDENTIALS=canzea-text-to-speech-8fba9cceae11.json


# Docker Setup

docker build -t rpa-speech-2-text .

docker run -e "GOOGLE_APPLICATION_CREDENTIALS=canzea-text-to-speech-8fba9cceae11.json" rpa-speech-2-text

# AWS input
http://intg.186527.xyz:4022/read?voiceId=Salli&text=Hackathon%20Day&outputFormat=ogg_vorbis
