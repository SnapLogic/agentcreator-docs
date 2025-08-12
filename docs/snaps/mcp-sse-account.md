# MCP SSE Account

Use this account type to connect the MCP Client Snaps to a remote MCP SSE Server. 

![MCP SSE Account screenshot](../img/mcp-sse-account.png){ align=middle }

## Prerequisites

* A valid MCP SSE URI and required header fields if necessary for an MCP Server

## Account settings

!!! example "Legend:"

    * Expression icon(![Expression Toggle](../img/expression_toggle.svg){: style="height:16px"}): Allows using JavaScript syntax to access SnapLogic Expressions to set field values dynamicall (if enabled). If disabled, you can provide a static value. [Learn more](https://docs-snaplogic.atlassian.net/wiki/spaces/SD/pages/1438042/Understanding+Expressions+in+SnapLogic).
    * SnapGPT (![SnapGPT Icon](../img/snapgpt_logo.svg){: style="height:16px"}): Generates SnapLogic Expressions based on natural language using SnapGPT. [Learn more](https://d14w8g1erguuat.cloudfront.net/rvw-jb-stage-202506-draft1/snapgpt/snapgpt-generate-expressions-mapper-snap.html).
    * Suggestion icon (![Suggest Icon](../img/suggest_icon.svg){: style="height:16px"}): Populates a list of values dynamically based on your Snap configuration. You can select only one attribute at a time using the icon. Type into the field if it supports a comma-separated list of values.
    * Upload (![Upload Icon](../img/upload_icon.webp){: style="height:16px"}): Uploads files. [Learn more](https://docs-snaplogic.atlassian.net/wiki/spaces/SD/pages/1439404).

| Field / Field set | Type | Description |
| ----------------- | ---- | ----------- |
| Label | String | Required. Specify a unique name for the Account.<br/>Default value: N/A<br/>Example: DeepWiki MCP Account |
| MCP SSE uri | String/Expression | Required. Specify the URI to the MCP server to connect to. The URI must include the correct `/sse` path as provided by the MCP Server provider. <br/>Example: `https://mcp.deepwiki.com/sse` |
| Additional headers |  |Use this field set to provide header field to use for requests to the MCP Server|
| Header name | String/Expression | The name of the header field |
| Header value | String/Expression | The value of the header field|
| Timeout | Integer/Expression | The number of seconds the request must wait before terminating the request. <br/>Default value: 60|