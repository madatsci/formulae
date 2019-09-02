# Formulae

**Nifty precompiled formulae handling**

## Installation

```elixir
def deps do
  [{:formulae, "~> 0.5"}]
end
```

## Using

```elixir
iex|1 ▶ f = Formulae.compile("rem(a, 5) - b == 0")
%Formulae{
  ast: {:==, [line: 1],
   [
     {:-, [line: 1],
      [{:rem, [line: 1], [{:a, [line: 1], nil}, 5]}, {:b, [line: 1], nil}]},
     0
   ]},
  eval: &:"Elixir.Formulae.rem(a, 5) - b == 0".eval/1,
  formula: "rem(a, 5) - b == 0",
  module: :"Elixir.Formulae.rem(a, 5) - b == 0",
  variables: [:a, :b]
}
iex|2 ▶ f.eval.(a: 11, b: 1)
true
iex|3 ▶ f.variables
[:a, :b]
iex|4 ▶ f.module
:"Elixir.Formulae.rem(a, 5) - b == 0"
```

## [Documentation](https://hexdocs.pm/formulae)

