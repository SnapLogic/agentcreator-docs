# MCP Invoke

The MCP Invoke Snap is a Snap to perform operations such as calling a tool, listing resources, and reading resources to get results on an MCP server.

![MCP Invoke screenshot](../img/mcp-invoke.png){ align=left }

## Prerequisites

* A valid <a href="https://snaplogic.github.io/agentcreator-docs/snaps/mcp-sse-account/ ">MCP SSE Account</a> with required fields provided.

## Snap views
<table>
    <tr>
        <th>View</th>
        <th>Description</th>
        <th>Examples of upstream and downstream snaps</th>
    </tr>
    <tr>
        <td>Input</td>
        <td>The Snap supports a maximum of one document input view.</td>
        <td><ul><li><a href="https://docs-snaplogic.atlassian.net/wiki/spaces/SD/pages/1438286/Mapper">Mapper</a></li></ul></td>
    </tr>
    <tr>
        <td>Output</td>
        <td>This Snap supports exactly two document output views.<br/><ul><li>The First view is a passthrough of the input document for further processing downstream</li><li>The second output view is the actual agent visualizer log that is being visualized</li></ul></td>
         <td><ul><li><a href="https://docs.snaplogic.com/snaps/snaps-machine-learning/sp-openai-llm/snap-openai-function-result-generator.html">OpenAI Function Result Generator</a></li><li><a href="https://docs.snaplogic.com/snaps/snaps-machine-learning/sp-azure-openai-llm/snap-azure-openai-function-result-generator.html">Azure OpenAI Function Result Generator</a></li><li><a href="https://docs.snaplogic.com/snaps/snaps-machine-learning/sp-google-genai-llm/snap-gg-frg.html">Google GenAI Function Result Generator</a></li><li><a href="https://docs.snaplogic.com/snaps/snaps-machine-learning/sp-amazon-bedrock-llm/snap-ab-capi-function-result-generator.html">Amazon Bedrock Function Result Generator</a></li></ul></td>
    </tr>
    <tr>
        <td>Error</td>
        <td colspan="2">Error handling is a generic way to handle errors without losing data or failing the Snap execution. You can handle the errors that the Snap might encounter when running the pipeline by choosing on eof the following options from the When errors occur list under the Views tab. The available options are:<ul><li>Stop Pipeline Execution Stops the current pipeline execution when an error occurs.</li><li>Discard Error Data and Continue Ignores the error, discards that record, and continues with the remaining records.</li><li>Route Error Data to Error View Routes the error data to an error view without stopping the Snap execution.</li></ul>Learn more about <a href="https://docs-snaplogic.atlassian.net/wiki/spaces/SD/pages/81526859">Error handling in Pipelines</a>.</td>
    </tr>
</table>

## Snap settings

!!! example "Legend:"

    * Expression icon(![Expression Toggle](../img/expression_toggle.svg){: style="height:16px"}): Allows using JavaScript syntax to access SnapLogic Expressions to set field values dynamicall (if enabled). If disabled, you can provide a static value. [Learn more](https://docs-snaplogic.atlassian.net/wiki/spaces/SD/pages/1438042/Understanding+Expressions+in+SnapLogic).
    * SnapGPT (![SnapGPT Icon](../img/snapgpt_logo.svg){: style="height:16px"}): Generates SnapLogic Expressions based on natural language using SnapGPT. [Learn more](https://d14w8g1erguuat.cloudfront.net/rvw-jb-stage-202506-draft1/snapgpt/snapgpt-generate-expressions-mapper-snap.html).
    * Suggestion icon (![Suggest Icon](../img/suggest_icon.svg){: style="height:16px"}): Populates a list of values dynamically based on your Snap configuration. You can select only one attribute at a time using the icon. Type into the field if it supports a comma-separated list of values.
    * Upload (![Upload Icon](../img/upload_icon.webp){: style="height:16px"}): Uploads files. [Learn more](https://docs-snaplogic.atlassian.net/wiki/spaces/SD/pages/1439404).

| Field / Field set | Type | Description |
| ----------------- | ---- | ----------- |
| Label | String | Required. Specify a unique name for the Snap. Modify this to be more appropriate, esepcially if more than one of the same Snaps is in the pipeline.<br/>Default value: MCP Invoke<br/>Example: Firecrawl MCP Server |
| Operation | String/Expression | Required. Specify the operation to perform for the current input. Operation can be one of `tools/call`, `resources/read`, or `resources/list`. The operation is provided within the `sl_metadata` if used with the <a href="https://snaplogic.github.io/agentcreator-docs/snaps/mcp-function-generator/">MCP Function Generator</a> Snap.<br/>Default value: `tools/call` |
| Tool Name | String/Expression | The name of the tool to be called. Enabled if the "Operation" is `tools/call` or is an expression.<br/>Example: `$function.name` |
| Parameters | String/Expression | The "tool call" or "read resource" parameters to be used for the operation. Enabled if the "Operation" is `tools/call`, `resources/read`, or is an expression.<br/> Example: `$function.json_arguments` |