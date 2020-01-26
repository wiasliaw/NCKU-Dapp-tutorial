# Solidity

## Description

Solidity 是一個物件導向的高階語言，專門用於撰寫智能合約。語言設計上受到 C++、Python、Javascript 影響，尤其對於學過 Javascript 的初學者特別好上手。透過 EVM(Ethereum Virtual Machine) 在乙太坊上執行。

## Layout

Solidity 檔案的副檔名為 `.sol`。第一行一定是 `pragma` 開頭，用於告訴編譯器如何編譯原始碼。再來是 `import`，如果需要，可以引入其他 `.sol` 使用。最後是註解 `/.../` 或是 `/*... */`。

```solidity
pragma solidity >=0.4.0 <0.7.0;

import "./OtherSolidity.sol"

// comments
/* comments */
```

## Contract

一個 `.sol` 通常會以 Contract 作為主體，會有

1. State Variable：是合約中的變數，其值會永久存在合約之中。

2. Functions：適合約中可執行的部份。

3. Function Modifiers：可以透過聲明的方式改變 Function 的行為。例如，你可以透過 Modifier 去執行條件檢查，或是聲明 Function 的存取範圍。

```solidity
pragma solidity >=0.4.0 <0.7.0;

contract SimpleStorage{
  uint storeData;
  function set(uint x) public {
    storeData = x;
  }
  function get() public view returns (uint) {
    return storeData;
  }
}
```

## Type

### Value Type

1. Boolean: `true`, `false`

2. Integer
    * `int`: signed integer
    * `uint`: unsigned intetger
    * 可以宣告有幾個 bit ，像是 `uint8`，明示有 8 個 bit；注意只能放 8 的倍數且上限為 256，若沒有宣告澤預設為 256。

3. Address
    * 一個大小為 20 bytes 的值，相當於一個乙太坊的地址大小。
    * member
        * balace: 查詢餘額
        * send
        * transfer
