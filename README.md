# SimpleHttpServer

a simple http server for testing elixir code

## Deprecation Warning!

This project is deprecated. It was originally intended as a lightweight tool for testing HTTP endpoints. We recommend [bypass](https://github.com/PSPDFKit-labs/bypass) instead.

## Installation

```elixir
def deps do
  [{:simple_http_server, github: "wistia/simple_http_server"}]
end
```

## Usage

```ex
{:ok, pid} = SimpleHttpServer.mount(5000, %{
  "/user/#{user_id}" => fn(req) ->
    {200, [], Poison.encode!(%{status: "ok"})}
  end
})

# Call the server on localhost:5000

:ok = SimpleHttpServer.stop(pid)
```
