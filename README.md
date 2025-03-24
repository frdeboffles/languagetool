# LanguageTool Docker Setup

This repository provides a convenient Dockerfile and instructions to quickly set up and run [LanguageTool](https://languagetool.org/), an open-source grammar, style, and spell checker.

## Quick Start

To get started with LanguageTool using Docker:

1. Clone this repository:

```sh
git clone https://github.com/frdeboffles/languagetool.git
cd languagetool
```

2. Download and extract ngrams:

```sh
curl -O https://languagetool.org/download/ngram-data/ngrams-en-20150817.zip
mkdir -p ngrams
(cd ngrams && unzip ../ngrams-en-20150817.zip)
rm -f ngrams-en-20150817.zip
```

3. Run LanguageTool as a Docker daemon:

```sh
docker compose up -d
docker compose logs -f
```

LanguageTool will be available at [http://localhost:6123](http://localhost:6123).

## Chrome Extention

See [https://languagetool.org/chrome](https://languagetool.org/chrome)

In the extension **_settings_** -> **_Advanced settings (only for professional users)_**

Under **_LanguageTool server:_**, select **_Other server—requires LanguageTool server running there_** and enter the following address in the text input:

```
http://localhost:6123/v2
```

## About LanguageTool

LanguageTool helps you check grammar, spelling, and style errors in over 20 languages. For more information, visit:

- [LanguageTool Official Site](https://languagetool.org/)
- [GitHub Repository](https://github.com/languagetool-org/languagetool)
- [LanguageTool Documentation](https://dev.languagetool.org/)

## Acknowledgments

This setup uses the Docker image [`silviof/docker-languagetool:latest`](https://hub.docker.com/r/silviof/docker-languagetool) as a base image.

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.
