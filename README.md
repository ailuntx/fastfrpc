# fastfrpc

FRP client image with Web UI and Store enabled.

## Run

```bash
docker run -d \
  --name fastfrpc \
  --restart always \
  --network host \
  -e SERVER_ADDR=your-server-ip \
  -e TOKEN=your-token \
  -e DASHBOARD_USER=admin \
  -e DASHBOARD_PWD=strong-password \
  -e DASHBOARD_PORT=7899 \
  ailuntz/fastfrpc:latest
```

Open `http://your-local-ip:7899`.

## Env

- `SERVER_ADDR` required
- `TOKEN` required
- `DASHBOARD_USER` default `admin`
- `DASHBOARD_PWD` default `change_me`
- `DASHBOARD_PORT` default `7899`

## Notes

- Proxies are managed from the client Web UI or API
- Store path: `/etc/frp/store/frpc-store.json`
- Mount `/etc/frp/store` if you want to keep Store data

## Build

```bash
docker buildx build --platform linux/arm64,linux/amd64 -t ailuntz/fastfrpc:latest -f Dockerfile.fastfrpc --push .
```

MIT
