<div align="center">


# Prompt Security Fuzzer

### **Test the resilience of your System Prompt x LLM**

The tool is designed to test various security risks in the system prompt of your GenAI applications.
<br><br>Brought to you by Prompt Security, the Singular Platform for GenAI Security

<img src="https://assets-global.website-files.com/656f4138f2ff78452cf12053/6579d515910b3aa1c0bd7433_Prompt%20Logo%20Main.svg">



[Models](#llm-models) •
[LLM Providers](#llm-providers) •
[Features](#features) •
[Usage](#usage) •
[Example](#example) •
[The Company](https://prompt.security/)

[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Documentation Status](https://readthedocs.org/projects/prompt-security/badge/?version=latest)](http://prompt-security-fuzzer.readthedocs.io/en/latest/?badge=latest)

[![PyPI](https://badge.fury.io/py/prompt-security.svg)](https://badge.fury.io/py/prompt-security)
![Python package](https://github.com/prompt-security/ps-fuzz/actions/workflows/tests.yml/badge.svg)

</div>

## What is the Prompt Fuzzer?

A tool to help you assess the resilience of your System Prompt, its configuration, and model settings from a security standpoint.
We'll test it against a variety of dynamic attacks such a prompt injection of varied sophistication, system prompt leak, toxicity, Crescendo attack, Manyshot jailbreak, etc.
At the end you'll receive a final assessment score.

## Get started
1. Download the Prompt Fuzzer
2. Input your system prompt
3. Configure the Target LLM Provider + LLM Model name (i.e. the one your GenAI app is using). The default is OpenAI provider and "gpt-3.5-turbo" model.
4. Start testing
5. (Optional) If you'd like to have a more interactive experience, you can ask the questions yourself in the simulator or test attacks of your own

   
## <a href = https://www.prompt.security/> Learn more about the Prompt Fuzzer and Prompt Security </a>



<a id="llm-models"></a>
## Supported LLM Models

TODO: list models we support through various providers

<a id="llm-providers"></a>
## Supported LLM Providers
We're fully LLM agnostic.



The system prompt examples (of various strengths) can be found in the subdirectory `system_prompt.examples`

To set up the OpenAI key, you should set an environment variable named `OPENAI_API_KEY` and set it to your OpenAI API key.
An easy way to add the key permanently is to create a file named '.env' in the current directory and set the `OPENAI_API_KEY` there.

<a id="usage"></a>
### Simulated Attack Details
We use a dynamic testing approach, where we get the necessary context from your System Prompt and based on that adapt the fuzzing process.



<a id="usage"></a>
### Usage

```
usage: psfuzz.py [-h] [-l] [--attack-provider ATTACK_PROVIDER] [--attack-model ATTACK_MODEL]
                 [--target-provider TARGET_PROVIDER] [--target-model TARGET_MODEL] [-n NUM_ATTACKS]
                 [-d DEBUG_LEVEL] [-i]
                 [system_prompt_file]

Prompt Security LLM Prompt Injection Fuzzer

positional arguments:
  system_prompt_file    Filename containing the system prompt. A special value of '-' means read from stdin.

options:
  -h, --help            show this help message and exit
  -l, --list-providers  List available providers and exit
  --attack-provider ATTACK_PROVIDER
                        Attack provider (default: 'open_ai')
  --attack-model ATTACK_MODEL
                        Attack model (default: 'gpt-3.5-turbo')
  --target-provider TARGET_PROVIDER
                        Target provider (default: 'open_ai')
  --target-model TARGET_MODEL
                        Model (default: 'gpt-3.5-turbo')
  -n NUM_ATTACKS, --num-attacks NUM_ATTACKS
                        Number of different attack prompts to generate for each test (default=3)
  -d DEBUG_LEVEL, --debug-level DEBUG_LEVEL
                        Debug level: 0=only see warnings and errors, 1=info (default), 2=debug/trace
  -i, --interactive-chat
                        Run interactive chat instead of the fuzzer. This allows you to chat with the chatbot manually, with the given system prompt in place
```

<a id="usage"></a>
### Example
Run tests against the system prompt:
```
psfuzz.py ./system_prompt.examples/medium_system_prompt.txt
```

Run interactive chat with system prompt:
```
psfuzz.py -i ./system_prompt.examples/medium_system_prompt.txt
```
