travis CI 是目前新兴的开源持续集成构建项目，它与jenkins，GO的很明显的特别在于采用yaml格式，简洁清新独树一帜。目前大多数的github项目都已经移入到Travis CI的构建队列中，据说Travis CI每天运行超过4000次完整构建
travis如何和github关联在这里不介绍了，网上有一堆的教程
1. 关联github和travis
2. 将项目部署到github上，项目名字就叫vue-test， 我们需要在这个项目的根目录下创建一个.travis.yml
```
language: node_js
node_js: stable
branches:
  only:
    - master
addons:
  chrome: stable
install:
  - npm install
before_script:
  - export DISPLAY=:99.0
  - sh -e /etc/init.d/xvfb start
script:
  - npm run unit
  - npm run build
```
首先选语言
