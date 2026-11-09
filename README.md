# goda-pm-ext-lazy.vim

The lazy loading of [goda-pm.vim](https://github.com/Shougo/goda-pm.vim), as
dpp-ext-lazy: the plugins with `on_*` keys (`on_cmd`, `on_ft`, `on_map`,
`on_event`, `on_func`, `on_lua`, `on_path`, `on_root`, `on_if`,
`on_source`, ...) are loaded when they are needed.

It has Vim script, which the startup script of goda-pm.vim calls: it must
be in `'runtimepath'` (a plugin that is not lazy; when the state is made the
first time, add it in your vimrc as goda.vim).

## Usage

Give the plugins to `lazy.MakeState()` in the configuration of goda-pm.vim,
and return what it gives:

```go
import "github.com/Shougo/goda-pm-ext-lazy.vim/ext/lazy"

r, err := lazy.MakeState(ctx, c.Host, plugins)
if err != nil {
	return nil, err
}
return &pm.ConfigReturn{Plugins: r.Plugins, StateLines: r.StateLines}, nil
```

See `:help goda-pm-ext-lazy`.
