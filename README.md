<h1 align="center">gpt-cli</h1>
<p align="center">
<a href="https://github.com/Simatwa/gpt-cli"><img src="https://img.shields.io/static/v1?logo=Github&label=Github&message=Passing" alt="Gihtub"/></a>
<a href="https://wakatime.com/badge/github/Simatwa/gpt-cli"><img src="https://wakatime.com/badge/github/Simatwa/gpt-cli.svg" alt="wakatime"/></a>
<a href="#"><img src="https://img.shields.io/static/v1?label=License&message=MIT&color=green&logo=MIT" alt="license"/></a>
<a href="#"><img src="https://img.shields.io/static/v1?label=Development&message=Beta&color=Orange&logo=progress" alt="Progress"/></a>
<a href="#"><img src="https://img.shields.io/static/v1?label=Code Style&message=Black&color=black&logo=Black" alt="Code-style"/></a>
<a href="#"><img src="https://img.shields.io/static/v1?label=Coverage&message=80%&color=red" alt="Coverage"/></a>
</p>

CLI tool for interacting with [ChatGPT](https://openai.com). 
> Chat and generate images.

![screenshot](assets/Screenshot1.png)

## [Independencies](requirements.txt)

* [Openai](https://github.com/openai/openai-python)
* [Numpy](https://github.com/numpy/numpy)
* [Colorama](https://github.com/tartley/colorama)
* [revChatGPT](https://github.com/acheong08/ChatGPT)

### Features

- Chat with ChatGPT conversationally.
 - Stream or Non-stream responses
 - Maintain record of the chats
- Generate Images - Based on your prompt or ChatGPT generated description
- Interact with the system commands on the fly
- Fully customizable Commandline Interface

### Prerequisites

- [x] [OPENAI_API_KEY](https://platform.openai.com/account/api-keys)

## Installation

Running the following commands at the `terminal` will get you ready.

```sh
$ git clone https://github.com/Simatwa/gpt-cli.git
$ cd gpt-cli
$ bash install.sh
 #or
$ sudo bash install.sh
```

## Usage 

- Make OPENAI_API_KEY an environment variable.

`$ export OPENAI_API_KEY=<openai-api-key>`

After that you can launch the script with or without a prompt

> For instance :
```sh 
    #Without a prompt
   $ gpt-cli 
      # With a prompt 
   $ gpt-cli Write a conversation between Sun and Pluto.`
```

- Parsing OPENAI_API_KEY as one of the arguments

Run `$ gpt-cli -k <gpt-api-key> <Your query>` at the terminal.

> For instance :

```sh
$ gpt-cli -k xxxxxxxxxxxxxxxxxx How to scan for SMB vulnerability using NMAP?
```

## Highlight
<details>
<summary>
<table>
<thead>
<tr><th style="text-align: right;">  No.</th><th>Command          </th><th>Action                                     </th></tr>
</thead>
<tbody>
<tr><td style="text-align: right;">    1</td><td>./{command}      </td><td>Run command against system                 </td></tr>
<tr><td style="text-align: right;">    2</td><td>img              </td><td>Generate image based on prompt             </td></tr>
<tr><td style="text-align: right;">    3</td><td>txt2img          </td><td>Generate image based on GPT description    </td></tr>
<tr><td style="text-align: right;">    4</td><td>_font_color      </td><td>Modify font-color                          </td></tr>
<tr><td style="text-align: right;">    5</td><td>_background_color</td><td>Modify background_color                    </td></tr>
<tr><td style="text-align: right;">    6</td><td>_prompt          </td><td>Modify terminal prompt                     </td></tr>
<tr><td style="text-align: right;">    7</td><td>_save            </td><td>Save current configurations to `.json` file</td></tr>
<tr><td style="text-align: right;">    8</td><td>_load            </td><td>Load configurations from file              </td></tr>
<tr><td style="text-align: right;">    9</td><td>_rollback        </td><td>Rollback Chat by {n} times                 </td></tr>
<tr><td style="text-align: right;">   10</td><td>_reset           </td><td>Reset current chat and start new           </td></tr>
<tr><td style="text-align: right;">   11</td><td>_help            </td><td>Show this help info                        </td></tr>
<tr><td style="text-align: right;">   12</td><td>{Any Other}      </td><td>Chat with ChatGPT                          </td></tr>
</tbody>
</table>
</summary>

1.img : Text-to-Image converter (EXPERIMENTAL)
 - e.g ```img Toddler cartoon coding in Python```

2.txt2img : Generate image based on GPT description
 - e.g ```txt2img Describe phenotype anatomy of ancient dinosaurs```

3._font_color : modifies font-color
 - e.g ```font_color input red```

4._background_color : modifies background_color
 - e.g ```background_color cyan```

5._prompt : Modify CMD prompt
 - e.g ```prompt ┌─[Smartwa@ChatGPT4]─(%H:%M:%S)```

6._load : Load configurations from the json file
 - e.g ```load DAN.json```

7._save : Save the current Chat Configurations
 - e.g ```load DAN.json```

8._rollback : Rollback the Chat by the {n} time(s)
 - e.g ```_rollback 2```

9._reset : Reset current chat and start new
 - e.g ```_reset Chat as if you are a 10 year old child```

10._help : Show this help info

* Use double `./` *(fullstop and foward slash)* to interact with **system commands**
  e.g './ifconfig'
</details>

<details>
<summary>

  For more info run `gpt-cli -h`.

  </summary>

```
  usage: main.py [-h] [-v] [-m davinci|curie|babbage] [-t [0.1-1]]
               [-mt [1-4000]] [-tp [0.1-1]] [-f [0.1-2]] [-p [0.1-2]] [-k KEY]
               [-kp path] [-ic [cyan|green|yellow|red]]
               [-oc [cyan|green|yellow|red]] [-bc [blue,magenta,black,reset]]
               [-pc [cyan|green|yellow|red]] [--prompt [SETTINGS ...]]
               [-tm TIMEOUT] [-pr PROXY] [-rc value] [-g 1,4] [-sp [Text ...]]
               [-o OUTPUT] [-pp prefix] [-rp prefix] [--disable-stream]
               [--new-record] [--disable-recording]
               [message ...]

Interact with ChatGPT at the terminal

positional arguments:
  message               Message to be send.

optional arguments:
  -h, --help            show this help message and exit
  -v, --version         show program's version number and exit
  -m davinci|curie|babbage, --model davinci|curie|babbage
                        ChatGPT model to be used
  -t [0.1-1], --temperature [0.1-1]
                        Charge of the generated text's randomness
  -mt [1-4000], --max-tokens [1-4000]
                        Maximum number of tokens to be generated upon
                        completion
  -tp [0.1-1], --top-p [0.1-1]
                        Sampling threshold during inference time
  -f [0.1-2], --frequency-penalty [0.1-2]
                        Chances of word being repeated
  -p [0.1-2], --presence-frequency [0.1-2]
                        Chances of topic being repeated
  -k KEY, --key KEY     GPT-API key
  -kp path, --key-path path
                        Path to text-file containing GPT-api key
  -ic [cyan|green|yellow|red], --input-color [cyan|green|yellow|red]
                        Font color for inputs
  -oc [cyan|green|yellow|red], --output-color [cyan|green|yellow|red]
                        Font color for outputs
  -bc [blue,magenta,black,reset], --background-color [blue,magenta,black,reset]
                        Console's background-color
  -pc [cyan|green|yellow|red], --prompt-color [cyan|green|yellow|red]
                        Prompt's display color
  --prompt [SETTINGS ...]
                        Customizes the prompt display
  -tm TIMEOUT, --timeout TIMEOUT
                        Request timeout while making request - (Soon)
  -pr PROXY, --proxy PROXY
                        Pivot request through this proxy
  -rc value, --reply-count value
                        Number of responses to be received
  -g 1,4, --gpt 1,4     ChatGPT version to be used
  -sp [Text ...], --system-prompt [Text ...]
                        Text to fine-tune GPT at the start
  -o OUTPUT, --output OUTPUT
                        Filepath for saving the chats - default
                        [/home/smartwa/git/gpt-cli/.chatgpt-history.txt]
  -pp prefix, --prompt-prefix prefix
                        Text to append before saving each prompt - default
                        [>>timestamp]
  -rp prefix, --response-prefix prefix
                        Text to append before saving each response - default
                        [None]
  --disable-stream      Specifies not to stream responses from ChatGPT
  --new-record          Override previous chats under the filepath
  --disable-recording   Disable saving prompts and responses
```

  </details>

> **Note** : **gpt-4** *(model)* supports upto *7000* tokens and others *3000*.

> **Warning** : **gpt-1**  Has issues - *(To be fixed later)*


## Motive
<details>
<summary>
Love for ❤️
</summary>
As a `terminal guy` I used to find it uncomfortable to keep shifting from one window to next in order to access ChatGPT even after trying out the [gpt-login](https://github.com/Simatwa/gpt-login), the rest is [here.](https://github.com/Simatwa/gpt-cli)
</details>

## Contributions

- Anyone is free to [fork](https://github.com/Simatwa/gpt-cli/fork), submit an [issue](https://github.com/Simatwa/gpt-cli/issues) without any **guideline** or submitting a [pull request](https://github.com/Simatwa/gpt-cli/pulls).

### ToDo

- [x] Use dialogue
- [ ] Issue prompt from a file
- [ ] Busy bar

## Acknowledgements

1. [remo7777](https://github.com/remo7777/T-Header)

2. [acheong08](https://github.com/acheong08/ChatGPT)

3. [f](https://github.com/f/awesome-chatgpt-prompts)
