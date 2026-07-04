# 🧠 MCP - Titan Memory Server implementation

## Featured TalkToAI Ecosystem Video

[![TalkToAI: Sovereignty Through ZeroThink and OpenZero Infrastructure](https://i.ytimg.com/vi/R52hsRdCmSM/hqdefault.jpg)](https://www.youtube.com/watch?v=R52hsRdCmSM)

A public overview of ZeroThink, OpenZero, FreeWebPanel, ZSEC, and the wider TalkToAI infrastructure. Watch it here: https://www.youtube.com/watch?v=R52hsRdCmSM

Colaboration between [@jasonkneen](https://github.com/jasonkneen) and [@ExpressionsBot](https://github.com/ExpressionsBot) 

Follow us on X
- [jasonkneen](https://x.com/jasonkneen)
- [megaprompt](https://x.com/megaprompt)

An implementation inspired by Google Research's paper ["Generative AI for Programming: A Common Task Framework"](https://arxiv.org/abs/2501.00663). This server provides a neural memory system that can learn and predict sequences while maintaining state through a memory vector, following principles outlined in the research for improved code generation and understanding.

## 📚 Research Background

This implementation draws from the concepts presented in the Google Research paper (Muennighoff et al., 2024) which introduces a framework for evaluating and improving code generation models. The Titan Memory Server implements key concepts from the paper:

- Memory-augmented sequence learning
- Surprise metric for novelty detection
- Manifold optimization for stable learning
- State maintenance through memory vectors

These features align with the paper's goals of improving code understanding and generation through better memory and state management.

## 🚀 Features

- Neural memory model with configurable dimensions
- Sequence learning and prediction
- Surprise metric calculation
- Model persistence (save/load)
- Memory state management
- Full MCP tool integration


## Downloads, Releases, And Discovery

| Need | Link |
| --- | --- |
| GitHub repository | https://github.com/ResearchForumOnline/mcp-titan-cognative-memory |
| Source ZIP | https://github.com/ResearchForumOnline/mcp-titan-cognative-memory/archive/refs/heads/main.zip |
| GitHub releases | https://github.com/ResearchForumOnline/mcp-titan-cognative-memory/releases |
| TalkToAI ecosystem | https://talktoai.org/ |
| Docs hub | https://docs.talktoai.org/ |

MCP memory server implementation for sequence learning, stateful memory vectors, model persistence, and memory-augmented tool workflows.

Clone, install dependencies, build, and connect it to an MCP-compatible client.

~~~bash
git clone https://github.com/ResearchForumOnline/mcp-titan-cognative-memory.git
cd mcp-titan-cognative-memory
npm install
npm run build
~~~

Search-friendly topics: MCP server, cognitive memory, Titan memory, model context protocol, local agent memory, AI memory server.

## 📦 Installation

```bash
# Install dependencies
npm install

# Build the project
npm run build

# Run tests
npm test
```

## 🛠️ Available MCP Tools

### 1. 🎯 init_model
Initialize the Titan Memory model with custom configuration.
```typescript
{
  inputDim?: number;  // Input dimension (default: 64)
  outputDim?: number; // Output/Memory dimension (default: 64)
}
```

### 2. 📚 train_step
Perform a single training step with current and next state vectors.
```typescript
{
  x_t: number[];    // Current state vector
  x_next: number[]; // Next state vector
}
```

### 3. 🔄 forward_pass
Run a forward pass through the model with an input vector.
```typescript
{
  x: number[]; // Input vector
}
```

### 4. 💾 save_model
Save the model to a specified path.
```typescript
{
  path: string; // Path to save the model
}
```

### 5. 📂 load_model
Load the model from a specified path.
```typescript
{
  path: string; // Path to load the model from
}
```

### 6. ℹ️ get_status
Get current model status and configuration.
```typescript
{} // No parameters required
```

### 7. 🔄 train_sequence
Train the model on a sequence of vectors.
```typescript
{
  sequence: number[][]; // Array of vectors to train on
}
```

## 🌟 Example Usage

```typescript
// Initialize model
await callTool('init_model', { inputDim: 64, outputDim: 64 });

// Train on a sequence
const sequence = [
  [1, 0, 0, /* ... */],
  [0, 1, 0, /* ... */],
  [0, 0, 1, /* ... */]
];
await callTool('train_sequence', { sequence });

// Run forward pass
const result = await callTool('forward_pass', {
  x: [1, 0, 0, /* ... */]
});
```

## 🔧 Technical Details

- Built with TensorFlow.js for efficient tensor operations
- Uses manifold optimization for stable learning
- Implements surprise metric for novelty detection
- Memory management with proper tensor cleanup
- Type-safe implementation with TypeScript
- Comprehensive error handling

## 🧪 Testing

The project includes comprehensive tests covering:
- Model initialization and configuration
- Training and forward pass operations
- Memory state management
- Model persistence
- Edge cases and error handling
- Tensor cleanup and memory management

Run tests with:
```bash
npm test
```

## 🔍 Implementation Notes

- All tensor operations are wrapped in `tf.tidy()` for proper memory management
- Implements proper error handling with detailed error messages
- Uses type-safe MCP tool definitions
- Maintains memory state between operations
- Handles floating-point precision issues with epsilon tolerance

## 📝 License

MIT License - feel free to use and modify as needed!

