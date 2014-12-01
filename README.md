pavlov
======

A BDD framework for your Elixir projects.

Simple usage:

```elixir
defmodule OrderSpec do
  use Pavlov.Case, async: true

  describe ".sum" do
    context "When the Order has items" do
      let :order do
        %Order{items: [
          {"burger", 10.0}
          {"fries", 5.2}
        ]}
      end

      it "sums the prices of its items" do
        assert Order.sum(order) == 15.2
      end
    end
  end
end
```

## Included Matchers

### Object equivalence
```elixir
#passes if actual == expected
expect(actual).to eq(expected)
```
