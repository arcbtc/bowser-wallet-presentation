---
marp: true
theme: default
paginate: true
size: 16:9
html: true

style: |
  :root {
    --green: #05c83d;
    --green-bright: #18ef4c;
    --black: #020403;
    --panel: #09100b;
    --panel-light: #0e1711;
    --border: #1f3425;
    --text: #f4f7f4;
    --muted: #849087;
  }

  section {
    background:
      radial-gradient(
        circle at 70% 35%,
        rgba(0, 170, 45, 0.08),
        transparent 38%
      ),
      var(--black);

    color: var(--text);

    font-family:
      "DejaVu Sans Mono",
      "Liberation Mono",
      "Courier New",
      monospace;

    font-size: 28px;
    line-height: 1.25;

    padding: 58px 68px 42px;

    position: relative;
    overflow: hidden;
  }

  /*
   * Green horizontal rule underneath the header,
   * matching the Bowser client aesthetic.
   */
  section::before {
    content: "";
    position: absolute;
    top: 70px;
    left: 0;
    right: 0;
    height: 2px;
    background: var(--green);
    opacity: 0.8;
  }

  /*
   * Small Bowser logo watermark.
   * Uses the standalone transparent logo asset.
   */
  section::after {
    content: "";
    position: absolute;
    top: 8px;
    right: 30px;

    width: 235px;
    height: 56px;

    background-image: url("assets/logo.png");
    background-repeat: no-repeat;
    background-size: contain;
    background-position: center;

    opacity: 0.45;
    pointer-events: none;
  }

  /*
   * Main slide heading.
   */
  h1 {
    color: var(--text);

    font-size: 48px;
    font-weight: 900;

    line-height: 1.02;

    letter-spacing: -2px;

    text-transform: uppercase;

    margin-top: 28px;
    margin-bottom: 13px;
  }

  /*
   * Small green section/kicker heading.
   *
   * We use ## as the first heading on slides
   * for this.
   */
  section > h2:first-child {
    color: var(--green-bright);

    font-size: 18px;
    font-weight: 900;

    letter-spacing: 4px;

    text-transform: uppercase;

    margin-top: 14px;
    margin-bottom: 0;
  }

  /*
   * Standard level-two heading.
   */
  h2 {
    color: var(--green-bright);

    font-size: 30px;
    font-weight: 900;

    margin-top: 15px;
    margin-bottom: 10px;
  }

  h3 {
    color: var(--green-bright);

    font-size: 25px;
    font-weight: 900;

    margin-top: 10px;
    margin-bottom: 8px;
  }

  p {
    margin: 7px 0;
  }

  strong {
    color: var(--green-bright);
  }

  ul {
    margin-top: 8px;
    padding-left: 1.1em;
  }

  li {
    margin: 7px 0;
  }

  li::marker {
    color: var(--green-bright);
  }

  code {
    color: var(--green-bright);
    background: #07100a;

    border: 1px solid var(--border);
    border-radius: 5px;

    padding: 2px 6px;
  }

  /*
   * Text directly underneath the main title
   * acts like a subtitle.
   */
  h1 + p {
    color: var(--muted);
    font-size: 24px;
    max-width: 1050px;
  }

  /*
   * Generic image treatment.
   */
  img {
    border-radius: 0;
  }

  /*
   * Simple image grids.
   *
   * HTML is only being used as a layout container.
   * The actual images remain Markdown.
   */
  .images-3 {
    display: grid;
    grid-template-columns: 0.8fr 1.5fr 0.9fr;
    gap: 20px;

    height: 430px;

    margin-top: 28px;
  }

  .images-3 p,
  .images-4 p,
  .images-2 p {
    margin: 0;
    min-width: 0;
    min-height: 0;
  }

  .images-3 img,
  .images-4 img,
  .images-2 img {
    display: block;

    width: 100%;
    height: 100%;

    object-fit: cover;

  }

  .images-4 {
    display: grid;
    grid-template-columns: 1.35fr 0.8fr 0.8fr 0.8fr;
    gap: 15px;

    height: 390px;

    margin-top: 27px;
  }

  .images-4 img {
    object-fit: contain;
  }

  .images-4 p:first-child img {
    object-fit: contain;
  }

  .images-3 > p:first-child,
  .images-4 p:not(:first-child) {
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .images-3 > p:first-child img,
  .images-4 p:not(:first-child) img {
    width: 100%;
    height: auto;
    aspect-ratio: 1;
    border-radius: 50%;
    object-fit: cover;
  }

  .images-3 .image-stack {
    display: grid;
    grid-template-rows: 1fr 1fr;
    gap: 15px;
    min-width: 0;
    min-height: 0;
  }

  .images-2 {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 25px;

    height: 420px;

    margin-top: 23px;
  }

  .images-2 img {
    object-fit: contain;
  }

  /*
   * Slide 3 hardware layout
   */
  .hardware {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 28px;

    margin-top: 18px;
  }

  .hardware-column {
    min-width: 0;
  }

  .hardware-column ul {
    font-size: 23px;
    margin-bottom: 16px;
  }

  .hardware-column img {
    width: 100%;
    height: 230px;

    object-fit: contain;

  }

  /*
   * Connected / air-gapped comparison.
   */
  .modes {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 24px;

    margin-top: 18px;
  }

  .mode {
    padding: 0;

    min-width: 0;
  }

  .mode h2 {
    font-size: 27px;
    margin-top: 0;
  }

  .mode ul {
    font-size: 18px;
    line-height: 1.18;
    margin-bottom: 15px;
  }

  .mode img {
    display: block;

    width: 100%;
    height: 230px;

    object-fit: contain;

  }

  /*
   * Watch-only client slide.
   */
  .clients {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 25px;

    margin-top: 22px;
  }

  .client {
    min-width: 0;
  }

  .client h2 {
    font-size: 21px;
    letter-spacing: 2px;
  }

  .client img {
    display: block;

    width: 100%;
    height: 390px;

    object-fit: contain;

  }

  /*
   * Closing slide
   */
  section.final {
    display: flex;
    flex-direction: column;

    align-items: center;
    justify-content: center;

    text-align: center;
  }

  section.final::before {
    top: auto;
    bottom: 0;
    height: 8px;
    opacity: 1;
  }

  section.final h2 {
    color: var(--green-bright);

    font-size: 25px;

    letter-spacing: 6px;

    margin: 0 0 26px;
  }

  section.final h1 {
    font-size: 88px;

    line-height: 0.94;

    letter-spacing: -5px;

    margin: 0;

    text-shadow:
      0 0 18px rgba(24, 239, 76, 0.11),
      5px 5px 0 rgba(0, 100, 30, 0.22);
  }

  section::footer {
    color: #59665e;
    font-size: 13px;
  }

  section::pagination {
    color: #526057;
    font-size: 14px;
  }


---

## 2019 // GENESIS

# FROM HACKSPACE TO HARDWARE WALLET (2019)

Stephen Snigirev + uBitcoin + ESP32 + adhoc hackspace at BTCConf.

<div class="images-3">

![Stephan Snigirev](assets/stephen.jpg)

![Bitcoin conference hackspace](assets/hackspace.jpg)

<div class="image-stack">

![Specter Wallet](assets/spector.png)

![ESP32](assets/esp32.jpg)

</div>

</div>

<!--
Back in 2019 Stephan Snigirev, a quantum physicist, had built the great uBitcoin library for Specter Wallet.

I was there retro-fitting arcade machines to accept Bitcoin payments in what later became the BitcoinSwitch project.

We put some tables together and started what became a tradition of hackspaces at Bitcoin conferences.

We realised we could use uBitcoin and the ESP32's excellent TRNG to make very affordable hardware wallets for only a few dollars.

That was great for unbanked regions, great because the hardware could be sourced independently rather than relying on a hardware-wallet supply chain, and great as an educational tool.

We also committed ourselves to nurturing a maker scene and encouraging Bitcoiners to build their own hardware, which was a great success.
-->


---

## 2020 // OPEN HARDWARE

# THE BOWSER WALLET WAS BORN (2020)

Completely FLOSS. Beta & educational to community FLOSS hardware wallet.

<div class="images-4">

![The original Bowser Wallet](assets/bowser-born.jpg)

![Vlad Stan](assets/vlad.png)

![BlackCoffee](assets/blackcoffee.png)

![Yvette](assets/yvette.png)

</div>

<!--
A year later I made Bowser Wallet as a beta and as a fun educational tool.

Through Bowser Wallet I met Vlad Stan, who helped make a client for it.

Vlad is a bitcoinjs maintainer and now works on LNbits.

When Vlad became full-time on LNbits, and being a genius, he rebuilt Bowser into a fantastic hardware wallet.

The name was bad though. We just called it "Hardware Wallet", intending it to be generic enough that people could fork it and use it as a base.

Through hundreds of workshops, people from the LNbits community including BlackCoffee and Yvette taught many people about DIY hardware wallets.

More recently the Coldcard debacle made me realise I needed to give the project more exposure, so I changed the name back to Bowser and started making this tutorial.

Snigirev stepped back from the Bitcoin space, which is a real shame, and went back to building quantum computers.

We stand on the shoulders of giants.

The Bowser Wallet intentionally uses simple and generic hardware that you can source almost anywhere.

You can buy it from our shop, but please don't. Buy it from AliExpress or Amazon.

The security model of Bowser is your keys being kept on a very simple FLOSS stack.

It has no secure element, so physically secure the device. Keep it locked away in a safe with the gold bars.

Secure elements have always been lower on the list in my own security model because I keep my hardware wallets extremely physically secure.
-->


---

## HARDWARE STACK

# ESP32. SIMPLE HARDWARE EXCELLENT ENTROPY.

<div class="hardware">

<div class="hardware-column">

### ESP32 TRNG

- Excellent hardware TRNG
- Entropy gathered from physical component noise
- Massively deployed in IoT hardware
- Cheap and widely available

![ESP32 randomness](assets/random.webp)

</div>

<div class="hardware-column">

### TOUGH/RESILIENT

- ESP32 devices are incredibly durable
- Used for long-running remote sensor projects
- Researchers leave them beside glaciers for years
- Off-the-shelf and easy to source hardware

![Glacier research](assets/glacier.jpg)

</div>

</div>

<!--
ESP32s have an excellent TRNG which gathers entropy from physical component noise in the microcontroller.

That is one reason ESP32s are such a common choice for IoT devices.

They are also incredibly tough.

Researchers leave these kinds of devices beside glaciers for years at a time gathering readings.

For Bowser that combination is ideal: cheap, replaceable, widely available hardware with a hardware entropy source.
-->


---

## BOWSER WALLET // TWO MODES SAME HARDWARE

# CONNECTED OR AIR-GAPPED

<div class="modes">

<div class="mode">

## USB / WEBSERIAL

- Connects via USB to the computer
- Fine for smaller amounts — up to **$10,000s**
- Easy-to-audit code
- **TRNG:** ESP32 hardware randomness
- **TRNG:** lots of physical entropy inputs

![Bowser WebSerial mode](assets/webserial-tdisplay.jpg)

</div>

<div class="mode">

## SD CARD

- Commands passed via simple `.txt` files
- Air-gapped
- Minimal attack vector
- **Dice:** infinitely easy to audit
- **Dice:** fewer steps **SHA256**

![Bowser SD card mode](assets/sd-card-version.png)

</div>

</div>

<!--
Bowser can be used in two main ways.

In WebSerial mode, you connect the wallet directly over USB.

This is convenient and, for me, perfectly reasonable for smaller amounts — up into the tens of thousands of dollars depending on your threat model.

The ESP32 TRNG is one of the world's most widely deployed and tested hardware random-number generators.

More importantly, the implementation is transparent and the code involved is easy to find and inspect.

It also has lots of physical entropy inputs.

For higher security, Bowser can operate using an SD card.

Commands are passed as simple text files, keeping the signing device air-gapped and the attack surface extremely small.

You can also generate entropy using dice.

Dice are almost absurdly easy to audit because you can physically see where the randomness is coming from.

The critical implementation then only needs to call a handful of well-understood functions such as SHA-256 and the required Bitcoin primitives.
-->


---

## WATCH-ONLY CLIENTS

# SIMPLE CLIENTS

<div class="clients">

<div class="client">

## LNBITS EXTENSION

![LNbits Bowser extension](assets/lnbits-extension.png)

</div>

<div class="client">

## BOWSER STANDALONE CLIENT

![Bowser standalone client](assets/bowser-client.png)

</div>

</div>

<!--
The Bowser itself does not need to become a complicated wallet application.

It can remain a very simple signing device while a watch-only client handles balances, addresses, transaction construction and blockchain access.

There is an LNbits extension for people already using the LNbits ecosystem.

There is also a standalone Bowser client which runs as a browser-local watch-only wallet.

The important separation is that the private keys stay on the Bowser hardware.
-->


---

<!-- _class: final -->
<!-- _paginate: false -->

## > BOWSER WALLET

# LET'S BUILD

<!--
Let's build one!
-->
