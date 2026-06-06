https://github.com/anthropics/claude-code/tree/main/plugins/ralph-wiggum

[[claude code plugin]] implements Ralph using a [[stop hook]] that intercepts Claude's exit attempts

In the prompt you put an output promise of

```
- Output: <promise>COMPLETE</promise>
```

