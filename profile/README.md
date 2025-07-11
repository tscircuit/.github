## tscircuit - Create Electronics with Typescript

tscircuit code turns into real electronics that you can preview and order

- [Star our GitHub repo!](https://github.com/tscircuit/tscircuit) [![Github Badge](https://img.shields.io/github/stars/tscircuit/tscircuit?style=social)](https://github.com/tscircuit/tscircuit)

```tsx
import { USBC } from "@tsci/seveibar.smd-usb-c"

export default () => {
  return (
    <board width="12mm" height="30mm">
      <USBC
        connections={{
          GND: "net.GND",
          VBUS: "net.VBUS"
        }}
      />
      <led
        name="LED"
        supplierPartNumbers={{
          jlcpcb: ["965799"],
        }}
        color="red"
        footprint="0603"
        pcbY={12}
        schY={2}
      />
      <button pin2=".R1 > .pos" pin3="net.VBUS" schY={-2} />
      <resistor name="R1" footprint="0603" resistance="1k" />

      <trace from=".R1 > .neg" to=".LED .pos" />
      <trace from=".LED .neg" to="net.GND" />
    </board>
  )
}
```
