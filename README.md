# Blockchain interview homework

### 1/ Simple Signing & Verification api server using `secp256k1`
#### REQUIREMENTS
- The server provides 2 endpoints for Signing and Verifying:
- Use curve `secp256k1`
- Signing:
  - Input `privateKey` and `message`
  - Output string `signature`
  - Example:
    ```
    // Input 
    privateKey: b12dbc163d7935fba5ba11aba0691a11b2f6a2235c1ffa51718955e2e1da6249
    message: hello_world

    // Output: 
    3045022100e9116623942dbd89f1a37aa3e00ba5efda72ea28b7eb28a09f4739fcdad2c34e02204decb0dc4a5b59da7aa995b34d5e06cf3fe5dc85845719edf11e9e79d5792e59
    ```
- Verifying:
  - Input `message`, `signature` from the signing's output and `publicKey`
  - Output `true | false` indicate whether the `signature` is valid or not
  - Example:
    ```
    // Input
    message: hello_world
    signature: 3045022100e9116623942dbd89f1a37aa3e00ba5efda72ea28b7eb28a09f4739fcdad2c34e02204decb0dc4a5b59da7aa995b34d5e06cf3fe5dc85845719edf11e9e79d5792e59
    publicKey: 04b0c4047cd4e6f28593cff46cd99ad1ba9f65388dd7a641c50e34c0d5fbc4c0fdc6a827a966691c0e18dd0347464df79f623d9d86e2e566aeb25abf1da8c6f9a8
 
    // Output
    true
    ```

<br/>

### 2/ Parse an ERC20 (Ethereum's token standard) transaction
#### REQUIREMENTS
- The application can be a CLI (read input from command line) or an API server
- Input: an ethereum transaction hash. Examples: 
  - `0x3f9b5c3ba9f52a5876205a23359b3909b2ff61ec7b395688c32a5025efe9c306`
  - `0x6cdb1d1d2828afe634323331e73c65b9d67b2fd1b71c95b3ff4597ec588c09b2`
- Output: formated data from transaction's raw data. Examples
  ```
  // For transaction hash: 0x3f9b5c3ba9f52a5876205a23359b3909b2ff61ec7b395688c32a5025efe9c306
  // Output
  {
    transfers: [{
      from: '0xc2273e233bbaa8ea4651f43cbaa2ef464030aa66',
      to: '0x94f652d16928c760dc93a6c8b6d09b3859599730',
      amount: '1000000000000000000',
    }]
    hash: '0x3f9b5c3ba9f52a5876205a23359b3909b2ff61ec7b395688c32a5025efe9c306',
    blockHeight: 9460026
    contractAddress: '0x17a6cf4893f5c709c88f98c757d6361f1685a2f8',
  }
  ```
- You can not using any processed data from api service such as Etherscan.

#### MATERIALS
- To query a transaction's raw data, use [infura.io](https://infura.io/). Register an account and get the api for mainnet. With an Infura API, you can interact with the ETH node through:
  - [Web3](https://web3js.readthedocs.io/en/v1.4.0/web3-eth.html)
  - Manually send RPC requests to the API. You can read the ETH RPC spec [here](https://eth.wiki/json-rpc/API#json-rpc-methods)
- To check a transaction, use [Etherscan](https://etherscan.io/)


**For any questions, please submit an issue*
