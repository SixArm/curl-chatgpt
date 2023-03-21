# curl-chatgpt

This is a unix shell script to connect to the OpenAI ChatGPT API,
use your own OpenAI API KEY to make request with prompt content, 
receive a result choice, and print its message content as text.

This script is deliberately simple to use as is, and also is
built so you can edit the source code if you want to change it.

The dependencies are POSIX shell, curl command, and jq command.

Syntax:

    curl-chatgpt <prompt-content>

    curl-chatgpt --output <output-file> <prompt-content>

    curl-chatgpt --input <input-file>

    curl-chatgpt --input <input-file> --output <output-file>

Examples:

    curl-chatgpt "What is the meaning of life?"

    curl-chatgpt --output result.txt "What is the meaning of life?"

    curl-chatgpt --input prompt.txt

    curl-chatgpt --input prompt.txt --output result.txt

## Setup

To use this program, you need to first do this:

  1. Get your own OpenAI ChatGPT API key from
     https://platform.openai.com/account/api-keys

  2. Export the key into your local environment:
     `export OPENAI_API_KEY=<KEY>`

  3. Be sure your system has the curl command and jq command.

## Options

  * `-h --help`: 
      print helpful information

  * `-v --verbose`: 
      print diagnostic information; use 2x or 3x for more

  * `-V --version`: 
      print the program version number

  * `-i --input <file>`:
      input the request content text from an exiting file

  * `-o --output <file>`:
      output the response content text into a new file

  * `-c --content <text>`:
      explicitly provide a request content prompt string

  * `--program-command`:
      print the program command name

  * `--program-version`:
      print the program version number

  * `--program-created`:
      print the program updated date

  * `--program-updated`:
      print the program updated date

  * `--program-license`:
      print the program license name

  * `--program-contact`:
      print the program contact information for the maintainer

  * `--program-website`:
      print the program website URL

## Repetition

The options for `--input`, `--output`, and `--content` may be repeated.

Examples:

    curl-chatgpt "prompt 1" "prompt 2" "prompt 3"

    curl-chatgpt -o out1.txt -c "prompt 1" -o out2.txt -c "prompt 2"

    curl-chatgpt -i in1.txt -o out1.txt -i in2.txt -o out2.txt


## Tracking

  * Command: curl-chatgpt
  * Version: 1.0.0
  * Created: 2023-03-11T20:50:17Z
  * Updated: 2023-03-13T05:55:35Z
  * License: GPL-2.0 or GPL-3.0 or contact us for more
  * Website: https://github.com/sixarm/curl-chatgpt
  * Contact: Joel Parker Henderson (joel@sixarm.com)
