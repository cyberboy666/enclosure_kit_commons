# eurorack_power-adapters

these are small pcb adapters made to power [underscores.shop](https://underscores.shop) circuits (which primarily run on 5v via usb-a) with a eurorack power supply:

there are a few different options depending on your needs:

## eurorack_to_usb_passive

this is the default adapter that comes with our eurorack enclosure kits - it takes 5v from 16pin eurorack header and passes it to the usb-a jack. 

upside is no external components are needed, only note that your eurorack power supply must already output 5v on this header which some do not

![image](https://github.com/user-attachments/assets/959ed1b9-3eaf-42f9-9d98-d2d8fad1ee92)

### BOM

part | source
--- | ---
eurorack_to_usb_passive pcb | fab'd from gerber `eurorack_to_usb_passive_mk_i.zip`
USB Type A Connector | [tayda](https://www.taydaelectronics.com/usb-type-a-female-connector.html)
16pin box header | [tayda](https://www.taydaelectronics.com/16-pin-box-header-connector-2-54mm.html)


## eurorack_to_usb_7805

this adapter uses 7805 linear regulator to take 12v from the 10pin eurorack header and convert to 5v (1.5A) over usb-a

upside is will work with any eurorack supply and uses cheap and common parts. downside is linear regulators are not so efficent and loose some energy to heat

![image](https://github.com/user-attachments/assets/e02aa661-dfe5-49bb-84fd-9aeefbdf5543)

### BOM

part | source
--- | ---
eurorack_to_usb_7805 pcb | fab'd from gerber `eurorack_to_usb_7805_mk_i.zip`
USB Type A Connector | [tayda](https://www.taydaelectronics.com/usb-type-a-female-connector.html)
10pin box header | [tayda](https://www.taydaelectronics.com/10-pin-box-header-connector-2-54mm.html)
L7805 to-220 | [tayda](https://www.taydaelectronics.com/lm7805-l7805-7805-voltage-regulator-ic-5v-1-5a.html)
c1 - 0.33u | [tayda](https://www.taydaelectronics.com/10-x-0-33uf-50v-ceramic-disc-capacitor-pkg-of-10.html)
c2 - 0.1u | [tayda](https://www.taydaelectronics.com/a-553-0-1uf-50v-ceramic-disc-capacitor-pkg-of-10.html)


## eurorack_to_usb_MP1584EN

this adapter uses an active switching step-down module to take 12v from 10pin eurorack header down to 5v (3A) over usb-a

upside is it is efficient step down without creating too much heat. downside is requires specific module sourced and costs slightly more

![image](https://github.com/user-attachments/assets/1c95465b-4a31-4a2f-9b69-961f464d493a)

![image](https://github.com/user-attachments/assets/aeb3cb3f-bbd9-4554-ae5e-917bd406b3cf)

part | source
--- | ---
eurorack_to_usb_MP1584EN pcb | fab'd from gerber `eurorack_to_usb_MP1584EN_mk_i.zip`
USB Type A Connector | [tayda](https://www.taydaelectronics.com/usb-type-a-female-connector.html)
10pin box header | [tayda](https://www.taydaelectronics.com/10-pin-box-header-connector-2-54mm.html)
MP1584EN 3A Step-down 5v | [aliexpress](https://www.aliexpress.com/p/trade/confirm.html?pdp_ext_f=%7B"sku_id":"12000035437063793"%7D)
c1 220u | [tayda](https://www.taydaelectronics.com/220uf-16v-105c-radial-electrolytic-capacitor-6x11mm.html)


# adapting underscores circuits for eurorack

many underscores circuits take 5v from a [horizontal mounted dc barrel jack](https://www.taydaelectronics.com/dc-power-jack-2-1mm-barrel-type-pcb-mount.html) which is good for standalone circuits powered from side. however for eurorack mounted circuits it can be easier to plug in power from behind. in this case we can use a [vertical dc socket](https://www.taydaelectronics.com/dc-power-jack-2-1mm-round-type-panel-mount-1.html) instead. for these sockets the longer pin is GND which goes closest to the edge of pcb.

![Screenshot from 2025-04-29 11-19-55](https://github.com/user-attachments/assets/82d0b8c7-bea6-45b9-add2-a17368e392b7)

![image](https://github.com/user-attachments/assets/59a664b5-bc0c-46ae-96ac-6fa047308fff)


