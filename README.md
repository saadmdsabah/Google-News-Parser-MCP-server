# Google News Parser (FastMCP Server)

**Status:** Live & Tested  
**Protocol:** [FastMCP](https://fastmcp.dev/)  
**Authentication:** None

This project provides a simple, lightweight [FastMCP](https://fastmcp.dev/) (Model Context Protocol) server that parses the Google News RSS feed. It exposes a single tool, `get_google_news_feed`, to fetch the latest headlines, descriptions, and source metadata.

The server is built using the `fastmcp` library for the MCP implementation and `feedparser` for parsing the RSS feed.

## 🚀 Live Server Endpoint

The MCP server is deployed on FastMCP Cloud and is publicly accessible for immediate use by any MCP-compatible client or AI model.

* **MCP Endpoint URL:** `https://google-news-parser.fastmcp.app/mcp`

## ✅ Server Status & Testing

The endpoint is live and has been fully tested and confirmed working with the following clients and inspectors:

* Cursor.ai (via `mcp.json` context)
* `@modelcontextprotocol/inspector`
* FastMCP's built-in inspector

## 🛠️ Tool Definition

The server exposes the following tool:

### `get_google_news_feed`

* **Description:** Get the latest headlines and metadata from the Google News RSS feed.
* **Tags:** `google news`, `news feed`, `rss`, `headlines`
* **Arguments:**
    * `max_results` (int, optional): The maximum number of articles to return. **Default: 3**.

---

## 💻 Example Usage

You can interact with this MCP server using any standard HTTP client or a compatible editor like Cursor.ai.

### Using Cursor.ai

To use this tool directly within the Cursor.ai editor, follow these two steps:

1.  **Create `mcp.json`:** In the root of your project folder, create a file named `mcp.json` and add the URL of the server's manifest.

    **`mcp.json`**
    ```json
      {
          "mcpServers": {
              "google-news-parse": {
                  "url": "https://google-news-parser.fastmcp.app/mcp"
              }
          }
      }
    ```

2.  **Prompt the Chat:** Cursor will automatically detect the file and load the tool. You can now just ask the AI to use it in plain English.

    > **User Prompt:**
    >
    > Hey, can you get me the top 2 headlines from Google News using the `get_google_news_feed` tool?

Cursor will then execute the tool against your live server and return the results directly in the chat.
    print(f"\nAn error occurred: {e}")
