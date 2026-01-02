# Network Load Tester/DDOS Tool

## Disclaimer

**WARNING**: This tool is for educational purposes only. It is intended to demonstrate network programming concepts and multi-threading in Python. Use only on systems you own or have explicit written permission to test. Unauthorized use of this tool against systems you do not own or have permission to test is illegal and unethical. The author is not responsible for any misuse of this tool.

## Overview

This Python script is a simple network load tester that simulates multiple clients connecting to a server and sending HTTP requests. It is designed to help understand how servers handle concurrent connections and can be used for legitimate load testing in controlled environments.

## Features

- Multi-threaded client simulation
- Configurable target IP and port
- Configurable number of threads and requests per thread
- Basic error handling

## Code Explanation

The script uses the `socket` and `threading` modules to create multiple threads that each send a fixed number of HTTP GET requests to a target server.

### Key Variables

- `target_ip`: The IP address of the server to test (default: 127.0.0.1)
- `target_port`: The port of the server (default: 80)
- `requests_per_thread`: The number of requests each thread will send (default: 1000)

### The `attack` Function

Each thread runs the `attack` function, which:
1. Creates a TCP socket.
2. Connects to the target server.
3. Sends an HTTP GET request.
4. Closes the socket.

If an error occurs (such as a connection error), the error is printed and the thread stops.

### Thread Creation

The script creates 100 threads, each running the `attack` function. After starting all threads, the main thread waits for all to complete.

## Usage

1. Ensure you have Python 3.x installed.
2. Clone this repository.
3. Update the `target_ip` and `target_port` to point to your test server (only if you have permission).
4. Run the script:
