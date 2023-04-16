# Optimize Time to First Byte

![rw-book-cover](https://web-dev.imgix.net/image/jL3OLOhcWUQDnR4XjewLBx4e3PC3/OBITO4G8MUJMILC7IFE0.jpg?auto=format&fit=max&w=1200&fm=auto)

## Metadata
- Author: [[web.dev]]
- Full Title: Optimize Time to First Byte
- Category: #articles
- URL: https://web.dev/optimize-ttfb/

## Highlights
- 重定向时间的另一个重要来源可能来自 HTTP 到 HTTPS 的重定向。解决此问题的一种方法是使用 `Strict-Transport-Security` 标头 (HSTS)，它将在第一次访问源时强制使用 HTTPS，然后告诉浏览器在以后的访问中立即通过 HTTPS 方案访问源。 ([View Highlight](https://read.readwise.io/read/01gsc9xyhh12nkmmx359kd4y1r))
- **Use a [stale-while-revalidate strategy](https://developer.chrome.com/docs/workbox/caching-strategies-overview/#stale-while-revalidate) for assets.** If an asset is in the service worker cache—be it a document or a resource the document requires—the stale-while-revalidate strategy will service that resource from the cache *first*, then will download that asset in the background and serve it from the cache for future interactions. ([View Highlight](https://read.readwise.io/read/01gsca1zg9zmz49087jz65yce9))
    - Note: 对资源采用 swr 策略
