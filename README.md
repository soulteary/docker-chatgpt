# Docker ChatGPT

One-click local version of ChatGPT, allowing access to various data sources and non-OpenAI models.

## Screenshots

<img src=".github/screenshots/let-coding.png" width="80%">

Conversation with the image.

<img src=".github/screenshots/conversation-with-image.png" width="80%">

Conversation with the plugin.

<img src=".github/screenshots/conversation-with-plugin.png" width="80%">

Customize the Model Switcher.

<img src=".github/screenshots/model-switcher.png" width="80%">

App Settings.

<img src=".github/screenshots/settings.png" width="80%">

## Key features

- Privacy is in your hands, no stats report.
- Client is Blazing fast.
- Allow you add any custom data source, data types.
- Consistent with the official function interaction.

<img src=".github/screenshots/perf.png" width="50%">

## Quick Overview

1. Download the project.

```bash
# download the latest version
git clone https://github.com/soulteary/docker-chatgpt.git
# or use zipball
wget https://github.com/soulteary/docker-chatgpt/archive/refs/heads/main.zip
```

2. Use docker to launch the project.

```bash
docker compose up
# or run in the daemon mode
docker compose up -d
```

Open your browser, visit `http://localhost:8090`, and enjoy.

## How to Upgrade

**The Client will be updated along with the project to keep it consistent with the officially supported functions.**

You can update the project by updating the mirror version used in this repository.

```bash
# version in the docker-compose.yml file
docker pull soulteary/chatgpt
```

**Backend services will continue to complete and support new data source types.**

You can download the latest version of the automatically built image by using the following command:

```bash
docker pull soulteary/sparrow
# or use the latest version
docker pull soulteary/sparrow:v0.6.0
```

Welcome to submit your code in the project to support your data type.

## Customize

As an early version, you can directly use it to access the OpenAI API and get the same front-end experience as the official one.

In configuration file [docker-compose.yml](./docker-compose.yml), you can find configuration information suitable for you.


For more advanced usage, and previous practices, such as searching various vertical websites through it, using MidJoruney to draw pictures, you can refer to the video in the [sparrow project documentation](https://github.com/soulteary/sparrow).

## About Private

The project **does not need** to connect to **any external network** except for the backend service address that will be connected in the configuration.

You can prohibit the privacy leakage you are worried about by setting firewall rules or cloud server export access rules.

This does not affect the use of the program as it does not require an additional network connection.

## Credits

- Backend: ChatGPT Style client-compatible Backend Server, open source implementation. [soulteary/sparrow](https://github.com/soulteary/sparrow)

## License

[WTFPL license](./LICENSE)
