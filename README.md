# 英国国家统计局MCP服务器 

一个用于访问英国国家统计局(ONS) Beta API的模型上下文协议(MCP)服务器，无需API密钥即可获取官方统计数据。
A model Context Protocol (MCP) server for accessing the Beta API of the Office for National Statistics (ONS) in the UK can obtain official statistical data without an API key.## 工具列表 Tool List

本MCP服务封装下列工具，可让模型通过标准化接口调用以下功能。 本MCP服务封装下列工具，可让模型通过标准化接口调用以下功能。

| 工具 Tool   | 描述 Description         |
|-------|--------------------|
| list_datasets | List available ONS datasets with metadata |
| get_dataset | Get detailed information about a specific dataset |
| search_datasets | Search for datasets by name or description |
| get_observation | Get specific data observations with dimension filters |
| get_latest_data | Get the latest available data for a dataset with optional filters |


## 检查服务 ## Inspector

工具在线测试： [https://mcp.xiaobenyang.com/inspector/1777316659346435](https://mcp.xiaobenyang.com/inspector/1777316659346435)

Online Tool test [https://mcp.xiaobenyang.com/inspector/1777316659346435](https://mcp.xiaobenyang.com/inspector/1777316659346435)

## 服务配置 MCP Server Config


> #### 如何获取 XBY-APIKEY ？ How to get XBY-APIKEY ?
> 访问小笨羊科技网站 [https://xiaobenyang.com](https://xiaobenyang.com)，注册用户即可获得APIKEY
> Visit XiaoBenYang website [https://xiaobenyang.com](https://xiaobenyang.com), register and get the APIKEY.

### SSE
```json
{
  "mcpServers": {
    "英国国家统计局MCP服务器": {
      "headers": {
        "XBY-APIKEY": "<YOUR_XBY_APIKEY>"
      },
      "type": "sse",
      "url": "https://mcp.xiaobenyang.com/1777316659346435/sse"
    }
  }
}
```
### STREAMABLE HTTP
```json
{
  "mcpServers": {
    "英国国家统计局MCP服务器": {
      "headers": {
        "XBY-APIKEY": "<YOUR_XBY_APIKEY>"
      },
      "type": "streamable_http",
      "url": "https://mcp.xiaobenyang.com/1777316659346435/mcp"
    }
  }
}
```
### STDIO
```json
{
    "mcpServers": {
        "英国国家统计局MCP服务器": {
          "command": "npx",
          "args": [
            "-y",
            "xiaobenyang-mcp"
          ],
          "env": {
            "XBY_APIKEY": "<YOUR_XBY_APIKEY>",
            "mcpId": "1777316659346435",
          },
          "transport": "stdio"
        }
      }
}

```
