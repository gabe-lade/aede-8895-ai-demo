# AI Workflow Talk - Quarto Presentation

## Files

- `ai-workflow-talk.qmd` - The main presentation source file
- `custom.scss` - Custom theme with OSU branding colors

## Rendering

Make sure you have Quarto installed, then:

```bash
quarto render ai-workflow-talk.qmd
```

This will generate `ai-workflow-talk.html` which you can open in any browser to present.

## Presenting

- Use arrow keys or spacebar to advance slides
- Press `S` for speaker notes view
- Press `F` for fullscreen
- Press `O` for slide overview
- Press `B` to black out the screen

## Customization

### Colors

The OSU colors are defined in `custom.scss`:
- Scarlet: `#BB0000`
- Gray: `#666666`

### Adding your demo code

The demo slides near the end have placeholder R code. Replace with your actual demo content:

```{r}
#| eval: true  # Change to true to run the code
#| echo: true  # Shows the code

# Your demo code here
```

### Live code execution

If you want code to actually run during the presentation, change `eval: false` to `eval: true` in the YAML header or individual code chunks.

## Git integration

This is now plain text! To track changes:

```bash
git add ai-workflow-talk.qmd custom.scss
git commit -m "Update presentation slides"
```

Now your students can see exactly what changed between versions.
