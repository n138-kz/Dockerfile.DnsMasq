# [Dockerfile.DnsMasq](https://github.com/n138-kz/Dockerfile.DnsMasq)

## Repos Info

<div align="center">

  [![GitHub repo license](https://img.shields.io/github/license/n138-kz/Dockerfile.DnsMasq)](/LICENSE)
  [![GitHub top language](https://img.shields.io/github/languages/top/n138-kz/Dockerfile.DnsMasq)](/../../)
  [![GitHub repo size](https://img.shields.io/github/repo-size/n138-kz/Dockerfile.DnsMasq)](/../../)
  [![GitHub code size in bytes](https://img.shields.io/github/languages/code-size/n138-kz/Dockerfile.DnsMasq)](/../../)

</div>
<div align="center">

  [![GitHub last commit](https://img.shields.io/github/last-commit/n138-kz/Dockerfile.DnsMasq)](/../../commits)
  [![GitHub commit activity](https://img.shields.io/github/commit-activity/w/n138-kz/Dockerfile.DnsMasq)](/../../commits)
  [![GitHub commit activity](https://img.shields.io/github/commit-activity/t/n138-kz/Dockerfile.DnsMasq)](/../../commits)
  [![GitHub language count](https://img.shields.io/github/languages/count/n138-kz/Dockerfile.DnsMasq)](/../../)

</div>
<div align="center">

  [![GitHub issues](https://img.shields.io/github/issues/n138-kz/Dockerfile.DnsMasq)](/../../issues)
  [![GitHub issues closed](https://img.shields.io/github/issues-closed/n138-kz/Dockerfile.DnsMasq)](/../../issues)
  [![GitHub pull requests](https://img.shields.io/github/issues-pr/n138-kz/Dockerfile.DnsMasq)](/../../pulls)
  [![GitHub pull requests closed](https://img.shields.io/github/issues-pr-closed/n138-kz/Dockerfile.DnsMasq)](/../../pulls)

</div>
<div align="center">

  [![](https://img.shields.io/badge/YouTube-FF0000?style=for-the-badge&logo=youtube&logoColor=white)](https://youtube.com/channel/UCOX8Iv1r0V18lbOnohE7lWQ)
  [![](https://img.shields.io/badge/Twitch-6441A5?style=for-the-badge&logo=twitch&logoColor=white)](https://www.twitch.tv/yuukomiya)
  [![](https://img.shields.io/badge/X-000000?style=for-the-badge&logo=x&logoColor=white)](https://x.com/n138kz)
  <br>
  [![](https://img.shields.io/youtube/channel/subscribers/UCOX8Iv1r0V18lbOnohE7lWQ)](https://youtube.com/channel/UCOX8Iv1r0V18lbOnohE7lWQ)
  [![](https://img.shields.io/twitch/status/YuuKomiya)](https://www.twitch.tv/yuukomiya)

</div>

## Dockerfile

./Dockerfile.DnsMasq/orchestra

```sh
docker build --no-cache -t test$(date +%Y%m%d):$(date +%H%M%S) -t test$(date +%Y%m%d) build@engine/
```

---

```sh
yes | docker container prune; docker run -itd -v $(pwd)/config:/etc/dnsmasq.d/ -w /var/tmp -p 127.0.0.1:53:53/udp -p 127.0.0.1:53:53/tcp --name dnsmasq test$(date +%Y%m%d)
```

```sh
docker exec -it dnsmasq bash
```

<details>

  <summary>99-custom-template.conf</summary>
  
  ```conf
  address=/gw1/192.168.0.2
  ptr-record=2.0.168.192.in-addr.arpa,gw1
  address=/gw2/192.168.0.3
  ptr-record=3.0.168.192.in-addr.arpa,gw2
  host-record=gateway,192.168.0.1
  host-record=dns,192.168.0.4
  host-record=dns,192.168.0.5
  ```

</details>


```sh
dig @127.0.0.1 dns
dig @127.0.0.1 -x 192.168.0.4
dig @127.0.0.1 -x 192.168.0.5
```

---

```sh
docker kill dnsmasq; yes | docker container prune
```


## Refs

- [![](https://www.google.com/s2/favicons?size=64&domain=https://github.com)Dockerfile.DnsMasq](https://github.com/n138-kz/Dockerfile.DnsMasq/)

## License

[Copyright (c) 2025 Yuu Komiya (n138), Under MIT License](LICENSE)  
