# My Project

This is a sample project demonstrating the use of Mermaid diagrams within a GitHub `README.md` file.

## Flowchart Example

Below is a simple flowchart illustrating a process.

```mermaid
graph TD
    A[Start] --> B{Is it true?};
    B -- Yes --> C[Process True];
    B -- No --> D[Process False];
    C --> E[End];
    D --> E;
