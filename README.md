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

  1. Ensure you have a payment plan and credits:
     https://platform.openai.com/settings/organization/billing/overview

  2. Get your own OpenAI ChatGPT API key from
     https://platform.openai.com/account/api-keys

  3. Export the key into your local environment:
     `export OPENAI_API_KEY=<KEY>`

  4. Be sure your system has the curl command and jq command.

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


## Troubleshooting

If you have problems, then try this example code from OpenAI, and you should see relevant error messages:

```sh
curl https://api.openai.com/v1/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer $OPENAI_API_KEY" \
  -d '{
    "model": "gpt-4o",
    "messages": [
      {
        "role": "system",
        "content": "You are a helpful assistant."
      },
      {
        "role": "user",
        "content": "Hello!"
      }
    ]
  }'
```

The error message could look like this:

```json
 "error": {
        "message": "You exceeded your current quota, please check your plan and billing details. For more information on this error, read the docs: https://platform.openai.com/docs/guides/error-codes/api-errors.",
        "type": "insufficient_quota",
        "param": null,
        "code": "insufficient_quota"
    }
}
```

The "insufficient_quota" error means you have used up your OpenAI API credits, or OpenAI needs you to add a payment method.


## Tracking

  * Command: curl-chatgpt
  * Version: 1.2.0
  * Created: 2023-03-11T20:50:17Z
  * Updated: 2024-10-22T08:42:08Z
  * License: GPL-2.0 or GPL-3.0 or contact us for more
  * Website: https://github.com/sixarm/curl-chatgpt
  * Contact: Joel Parker Henderson (joel@sixarm.com)
