# Set up Python with uv

Open your class folder in Codex, then copy and paste this prompt into a new chat. This asks Codex to install the tools and check that they work. You do not need to write or run the setup code yourself.

```text
Set up this Mac so I can run Python scripts through Codex and from the Mac Terminal app using uv. I am a beginner and may not have Python or any developer tools installed.

Please do the setup, rather than just giving me instructions:

1. Check whether uv is already installed and working. Reuse it if it is. Otherwise, install it using the official standalone installer:
   https://docs.astral.sh/uv/getting-started/installation/

2. Make sure the uv command is available both to Codex and in a newly opened Mac Terminal window. Make only the necessary shell configuration changes, preserve existing settings, and avoid duplicate PATH entries.

3. Use uv to install Python 3.12. Do not replace or modify Apple's system Python. Use uv to manage Python and script dependencies; do not install Homebrew, Xcode or Jupyter for this setup.

4. In my class folder, create check_setup.py. Give it a script dependency header specifying Python >=3.12,<3.13 and pandas. Have it import pandas, print the Python and pandas versions, and calculate the sum of 1, 2 and 3.

5. Run it with:
   uv run check_setup.py

6. Also check that uv is available from a fresh zsh shell. Fix any setup problems you encounter, requesting approval if needed. Do not report success unless the script actually runs and prints the expected sum of 6.

When finished, briefly explain what you installed or changed. Give me the exact commands to move into my class folder and run check_setup.py myself in Terminal. Tell me whether I need to restart Codex or open a new Terminal window.

For subsequent Python scripts in this class, use uv and declare each script's dependencies in its header.
```

After Codex finishes, follow its instructions to run `check_setup.py` yourself in Terminal. Check that the output shows the Python and pandas versions and a sum of **6**.

References: [Install uv](https://docs.astral.sh/uv/getting-started/installation/) · [Install and manage Python](https://docs.astral.sh/uv/guides/install-python/)
