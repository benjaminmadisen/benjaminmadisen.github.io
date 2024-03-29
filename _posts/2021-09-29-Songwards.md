---
title:  "Songwards"
layout: default
---

# Songwards

Located [here](https://songwards.dev) with github repository [here](https://github.com/benjaminmadisen/songwards)!

This is an ongoing project, started out of curiosity of what data Spotify made publicly available! It currently consists of two steps.

## Song-word vectorization

This is the bad pun the project is named after! This step leverages the well-established Word2Vec algorithm for generating a vectorization library using input texts. The goal is to generate vectorizations that are particularly appropriate in how people describe music: while "bass" and "heavy" might not be similar in normal speech, they can be used to describe the same songs. To generate an input corpora, I combine the words used in playlist titles with the URI used for songs in that playlist; because Word2Vec uses a sliding window for input, I put each word between a number of randomly selected songs from the playlist. The output of this model causes songs that are described by the same words have similar vectors, and similarly words that described the same songs have matching vectors - which is exactly what I am looking for! I've only done a first pass at this modeling to this point, and intend to iterate and explore more in the future.

## Song feature-word probability modeling

After generating vectors for words commonly used in playlist titles, my model is intended to estimate the probability a word describes a track. The track vectors from above would be perfect for this approach - but they are limited to tracks that appear in playlists! The dataset I have available is not being updated, so critically this would mean I could not predict values for any song released after mid-2020. To get around this, I estimate the probability that a word is associated with the "track features" Spotify provides for each song - features like valence, danceability, and time signature. These provide something for the model to catch onto - words similar to "pop" are more commonly paired with songs that have high danceability. I build an input dataset consisting of two halves: first, track features paired with the vectors of words used in playlists they appear on; and second, track features paired with vectors of words chosen randomly by how frequently each word appears in playlist titles. The first half is labeled one, and the second half is labeled zero, and I train a simple two-layer neural net using categorical cross-entropy loss. The result is a model which outputs a number between zero and one estimating the probability that a word vector really appeared describing its paired track features, or if it was random - an association of words with tracks! I've done two passes at this, and am actively working on improving the model. I intend to come back to this page to write more about the modeling once I get further along!