## Ejemplo contrato inteligente

```bash
hlf-saas-cli auth login
```

```bash
hlf-saas-cli dev start --localChaincode="localhost:9999" --chaincode=<usuario>_ejercicio --env-file=.env
```

```bash
hlf-saas-cli dev listen --forward-to=localhost:9999
```

```bash
npm run desarrollo contrato
```

## Probar chaincode

Acceder a [https://hlf-cc-dev.k8s.kfs.es/playground](https://hlf-cc-dev.k8s.kfs.es/playground)

```graphql
mutation initLedger {
  invokeChaincode(
    input: {
      chaincodeName: "<usuario>_ejercicio"
      function: "InitLedger"
      args: []
      transientMap: []
    }
  ) {
    response
    transactionID
    chaincodeStatus
  }
}

mutation queryAsset {
  queryChaincode(
    input: {
      chaincodeName: "<usuario>_ejercicio"
      function: "GetAllAssets"
      args: []
      transientMap: []
    }
  ) {
    response
    chaincodeStatus
  }
}
```
