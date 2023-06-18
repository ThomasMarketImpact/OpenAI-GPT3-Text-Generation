## Readme

### Dependencies
- OpenAI
- dotenv
- datetime
- time
- logging
- glob

### What the code does
This code generates text using the GPT-3 API. It takes three input files, one for each of the following: system1, system2, and user. The contents of these files are used to generate a response from the GPT-3 API. The generated text is then saved to an output file.

### How to run it
1. Install the required dependencies.
2. Set up an OpenAI API key and add it to a `.env.local` file.
3. Update the `CONFIG` dictionary with the file paths for the input and output files.
4. Run the script using `python generate_text.py`.

### Other information
- The `MODEL_NAME` and `TEMPERATURE` variables can be adjusted to change the behavior of the GPT-3 API.
- The `validate_input_files` function checks if the input files exist. If any of the files are missing, a `FileNotFoundError` is raised.
- The `generate_text` function generates text using the GPT-3 API. If the API rate limit is exceeded, the function will pause for the amount of time specified in the `RateLimitedError` exception before retrying.
- The `save_output_file` function saves the generated text to an output file. The file name includes a timestamp to avoid overwriting previous output files.
- The `main` function runs the script and prints the generated text to the console if an output file is found.