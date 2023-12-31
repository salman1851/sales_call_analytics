# sales_call_analytics
This program analyses a sales call using a combination of speech processing and deep learning techniques. Specifically, it quantifies the quality of the sales call by a number of metrics, such as duration of conversation, loudness of speakers, the amount of cross-talk, etc. The results are stored in a text file. <br />

The pipeline starts with reading a raw 'wav' file of a sales call recording. The file is then segmented into parts uttered by each of the speakers using the 'pyannote.audio' speaker diarization toolkit. The diarized speech is then classified as 'customer' or 'agent' using a trained neural network. <br />

Once we have the classified audio segments, their loudnesses are calculated using a formula in signal processing theory. The loudnesses are compared as the call progresses.
Cross-talk is calculated by finding any instances of overlapping speech during the conversation. The direction of the cross-talk (that is the person who interrupted) is determined by the lateness of the start time of both speakers in each overlapping event. <br />

The log file contains the duration of the call, the duration of each speaker, the average loudness of each speaker, the number of times each speaker was the louder, cross-talk duration, the number of cross-talk events, the number of times each speaker interrupted, and the locations of the diarized and classified audio files. <br />
