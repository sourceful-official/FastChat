# Sourceful Readme

Instructions for how to run locally:

1. If you are running on Mac:

```bash
brew install rust cmake
```

2. Install Package

```bash
pip3 install --upgrade pip  # enable PEP 660 support
pip3 install -e ".[model_worker,webui]"
```

3. Update the api_endpoints.json file

   - cp api_endpoints.json.example api_endpoints.json
   - Replace the api_key placeholder with the Gateway api_key (available in 1Password).

4. Run the controller
   The controller is needed to load up the Model config that we want to test

```
python3 -m fastchat.serve.controller --host 0.0.0.0 --port 21001
```

5. Run the Web UI

```
python3 -m fastchat.serve.gradio_web_server_multi --register-api-endpoint-file api_endpoints.json
```

6. Visit the local URL to access.
