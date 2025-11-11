# Open Source UI cookbook

1. Open web UI
- [official page](https://docs.openwebui.com/)
- [github](https://github.com/open-webui/open-webui)
- 사용
```bash
docker pull ghcr.io/open-webui/open-webui:main

docker run -d -p 3000:8080 -v open-webui:/app/backend/data --name open-webui ghcr.io/open-webui/open-webui:main
```
