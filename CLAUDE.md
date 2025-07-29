# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is an experimental PyTorch-based project for training neural networks to emulate audio effects. The goal is to train models that can replicate various audio effects like distortion, reverb, etc., by learning from input/output examples.

## Architecture Approach

The project uses a sequence-to-sequence approach where:
- Input: Previous `m` input samples + previous `m-1` output samples
- Output: Next output sample
- This allows the model to maintain state and generate coherent audio sequences

## Project Structure

- `audiofx.ipynb` - Main Jupyter notebook containing the experimental work and documentation
- `examples/` - Large collection of audio files (music library) used for training data
- `.gitignore` - Excludes examples folder and system files

## Development Environment

- **Python**: 3.11.11
- **Primary Framework**: PyTorch (torch 2.6.0.dev)
- **Audio Processing**: torchaudio (2.5.0.dev)
- **Development Interface**: Jupyter Lab/Notebook
- **Virtual Environment**: Located at `/Users/will/.venv/3.11/bin/python3`

## Common Development Tasks

### Starting Development
```bash
# Activate virtual environment (if not already active)
source /Users/will/.venv/3.11/bin/activate

# Start Jupyter Lab for notebook development
jupyter lab
```

### Running the Main Notebook
```bash
# Open the main experimental notebook
jupyter notebook audiofx.ipynb
```

## Audio Data

The `examples/` directory contains a large music library (75GB+) with various audio formats (.mp3, .m4a, .wav) used for training data generation. Training involves:

1. Selecting random audio slices from the library
2. Processing them through reference audio effects
3. Training models to predict the next audio sample

## Development Notes

- This is an experimental project without formal test suites or linting configuration
- Primary development happens in Jupyter notebooks
- Audio processing focuses on sample-level prediction
- The project explores different audio representations (raw floats, μ-law companding, etc.)
- Loss functions may evolve from simple squared error to perceptual similarity metrics