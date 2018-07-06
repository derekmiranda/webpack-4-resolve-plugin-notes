# Webpack 4 Resolve Plugin Notes

## Motivations

It's been frustrating trying to find information on how to write [resolve plugins](https://github.com/webpack/enhanced-resolve#plugins) so I'll be using this repo to compile information I find while reading through Webpack source code or finding random tidbits about the resolve plugin API.

### Next Steps

- figure out which hooks correspond to which parts of the resolution pipeline
- find hooks around alias resolution

## Resolution Flowchart

![Resolution Flowchart Image](https://user-images.githubusercontent.com/3408176/29152880-8a996b38-7d4f-11e7-913f-38fc90a2b4f5.png)

## Sources

[Great overview of resolution pipeline + more info on API](https://github.com/webpack/webpack.js.org/issues/1458#issuecomment-330445790)
