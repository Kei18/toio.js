# toio.js@Raspberry Pi

Library for controlling toio&trade;Core Cube using Node.js.

## :computer: Getting Started

### Prerequisites

- **Node.js** >= 10
- This library depends on [@abandonware/noble](https://github.com/abandonware/noble).
  - As far as I confirmed, additional libraries are not required.

### Installation

Install toio.js using `yarn`.
If `yarn` command is not existed, type `npm install -g yarn` to install.

```bash
yarn install
yarn build
```

### Usage

Here is a quick example to get you started.

```js
const { NearestScanner } = require('@toio/scanner')

async function main() {
  // start a scanner to find the nearest cube
  const cube = await new NearestScanner().start()

  // connect to the cube
  await cube.connect()

  // move the cube
  cube.move(100, 100, 1000)
  //         |    |     `--- duration [ms]
  //         |    `--------- right motor speed
  //         `-------------- left motor speed
}

main()
```

## :memo: Documentation

- [API reference document](https://toio.github.io/toio.js/)
- [toio&trade;Core Cube technical specification](https://toio.github.io/toio-spec/)

## :white_check_mark: Verified Environment

### Linux

Raspbian GNU/Linux 9.11 on Model B+

## :package: Packages

| Package name  | Readme                                 | Description          |
| ------------- | -------------------------------------- | -------------------- |
| @toio/scanner | [packages/scanner](./packages/scanner) | Cube scanner         |
| @toio/cube    | [packages/cube](./packages/cube)       | Cube BLE API wrapper |

## :video_game: Example

### How to play sample application

```sh
sudo yarn example:<name of example>                  # start sample application (see below)
```

**Do not forget `sudo`**

### List of sample application

| Name & Source                                   | Command                         | #cubes | Mat | Description                     |
| ----------------------------------------------- | ------------------------------- | ------ | --- | ------------------------------- |
| [id-reader](./examples/id-reader)               | `yarn example:id-reader`        | 1      | Yes | read & show toio ID information |
| [keyboard-control](./examples/keyboard-control) | `yarn example:keyboard-control` | 1      | No  | move a cube with ↑↓←→           |
| [chase](./examples/chase)                       | `yarn example:chase`            | 2      | Yes | a cube chase another one        |


## Note

- This repo is for research use
