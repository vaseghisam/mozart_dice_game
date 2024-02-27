import random
from pydub import AudioSegment

# Function to simulate rolling N six-sided dice and summing their outcomes
def roll_dice(n=1):
    return sum(random.randint(1, 6) for _ in range(n))

# Function to concatenate WAV files into a single output
def concatenate_wavs(output_path, wav_files):
    combined = AudioSegment.empty()
    for wav_file in wav_files:
        combined += AudioSegment.from_wav(wav_file)
    combined.export(output_path, format="wav")

# Base directory where your WAV files are stored
base_directory = "./mozart_wav/piano/"  # Adjust this path to where you've extracted the WAV files

# Constructing the sequences for the Minuet and Trio
# Minuet: 16 phrases, chosen based on the sum of two dice rolls
selected_minuet_files = [f"{base_directory}minuet{i}-{roll_dice(2)}.wav" for i in range(16)]
# Trio: 16 phrases, chosen based on the roll of one die
selected_trio_files = [f"{base_directory}trio{i}-{roll_dice(1)}.wav" for i in range(16)]

# Concatenate the selected measures into a single WAV file
output_path = "viennese_waltz_output.wav"
concatenate_wavs(output_path, selected_minuet_files + selected_trio_files)

print(f"Generated Viennese waltz saved to {output_path}")
