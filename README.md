Implementation of Vanilla LSTM and Multi Layer LSTM:


Vanilla LSTM

Definition:

A Vanilla LSTM is a single-layer recurrent neural network that uses LSTM (Long Short-Term Memory) units. It processes sequence data step-by-step, learning patterns and dependencies over time. LSTMs overcome issues like vanishing gradients that are common in simple RNNs by incorporating a gating mechanism to control the flow of information.

Characteristics:

1. Single LSTM Layer:

Only one LSTM layer is used to process the input sequence.
Outputs from this single layer are passed directly to a fully connected (Dense) layer for predictions.

2. Simpler Architecture:

Vanilla LSTM models have a simpler architecture compared to their multi-layer counterparts. This makes them computationally less expensive and easier to train.

3. Limited Representational Power:

With just one LSTM layer, the model's capacity to learn hierarchical features is limited. While sufficient for simple sequential tasks, it may struggle with complex patterns in the data.

4. Output:

The output at the last time step is typically used for prediction tasks. For example, in music generation, the output corresponds to the predicted pitch for the next note.

Used in the Project:
In the Vanilla LSTM implementation, the input sequence (encoded MIDI pitches) was passed through:
An embedding layer: Converts pitch indices into dense vector representations.
A single LSTM layer: Learns dependencies in the sequence.
A Dense layer with softmax: Maps the LSTM output to a probability distribution over possible pitches.


Multi-Layer LSTM (Stacked LSTM)

Definition:

A Multi-Layer LSTM, also called a Stacked LSTM, consists of multiple LSTM layers stacked on top of each other. The output from one LSTM layer serves as the input to the next. This deeper architecture enables the model to capture hierarchical features and complex patterns in the data.

Characteristics:

1. Multiple LSTM Layers:

Each layer processes sequential data passed from the previous layer.
This stacking allows the model to learn features at different levels of abstraction.

2. Hierarchical Learning:

Lower layers capture simple dependencies (e.g., pitch transitions).
Higher layers capture more abstract patterns (e.g., harmonic or rhythmic structures).

3. Increased Representational Power:

With multiple layers, the model can learn richer and more complex representations, making it suitable for tasks involving intricate patterns.

4. Dropout Regularization:

Dropout is often applied between LSTM layers to reduce overfitting by randomly deactivating some neurons during training.

5. Computational Cost:

Stacking layers increases the number of trainable parameters, leading to higher memory and computational requirements.

Used in the Project:
In the Multi-Layer LSTM implementation, the input sequence was processed through:
An embedding layer: Converts pitch indices into dense vectors.
Multiple LSTM layers: Each layer feeds into the next, progressively capturing higher-order dependencies.
A Dense layer with softmax: Maps the final LSTM output to a probability distribution over pitches.
