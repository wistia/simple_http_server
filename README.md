# SimpleHttpServer

a simple http server for testing elixir code

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
