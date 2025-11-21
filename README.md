# ManiaFun_ABI

**Upgradeability**

The contracts are upgradeable via a UUPS (Universal Upgradeable Proxy Standard) proxy pattern.

Key integration considerations:
- **Always interact with the proxy address** - The proxy address remains constant across upgrades, while the implementation contract may change
- **ABI stability** - While we maintain backward compatibility where possible, monitor our upgrade announcements as new versions may introduce additional methods or events
- **Event sourcing** - All events are emitted from the proxy address, not the implementation
- **Proxy address**: `[0x553d338C59A7F15fBb30F97100ED0aa750e5d358]`
- **Current implementation**: `[0xaBC43669AcB55D32d9C2B9Fd9ABFCC5B6F04E525]` (for reference only - do not hardcode)

For upgrade notifications contact: t.me/kdotTrades on Telegram.

    "abi": [
        {
            "type": "constructor",
            "inputs": [],
            "stateMutability": "nonpayable"
        },
        {
            "type": "receive",
            "stateMutability": "payable"
        },
        {
            "type": "function",
            "name": "UPGRADE_INTERFACE_VERSION",
            "inputs": [],
            "outputs": [
                {
                    "name": "",
                    "type": "string",
                    "internalType": "string"
                }
            ],
            "stateMutability": "view"
        },
        {
            "type": "function",
            "name": "bondingCurves",
            "inputs": [
                {
                    "name": "mint",
                    "type": "address",
                    "internalType": "address"
                }
            ],
            "outputs": [
                {
                    "name": "virtualTokenReserves",
                    "type": "uint256",
                    "internalType": "uint256"
                },
                {
                    "name": "virtualEthReserves",
                    "type": "uint64",
                    "internalType": "uint64"
                },
                {
                    "name": "realTokenReserves",
                    "type": "uint256",
                    "internalType": "uint256"
                },
                {
                    "name": "realEthReserves",
                    "type": "uint64",
                    "internalType": "uint64"
                },
                {
                    "name": "tokenTotalSupply",
                    "type": "uint256",
                    "internalType": "uint256"
                },
                {
                    "name": "complete",
                    "type": "bool",
                    "internalType": "bool"
                },
                {
                    "name": "trackVolume",
                    "type": "bool",
                    "internalType": "bool"
                }
            ],
            "stateMutability": "view"
        },
        {
            "type": "function",
            "name": "buy",
            "inputs": [
                {
                    "name": "token",
                    "type": "address",
                    "internalType": "address"
                },
                {
                    "name": "amount",
                    "type": "uint256",
                    "internalType": "uint256"
                },
                {
                    "name": "maxEthCost",
                    "type": "uint64",
                    "internalType": "uint64"
                }
            ],
            "outputs": [],
            "stateMutability": "payable"
        },
        {
            "type": "function",
            "name": "create",
            "inputs": [
                {
                    "name": "name",
                    "type": "string",
                    "internalType": "string"
                },
                {
                    "name": "symbol",
                    "type": "string",
                    "internalType": "string"
                },
                {
                    "name": "uri",
                    "type": "string",
                    "internalType": "string"
                },
                {
                    "name": "creator",
                    "type": "address",
                    "internalType": "address"
                }
            ],
            "outputs": [
                {
                    "name": "token",
                    "type": "address",
                    "internalType": "address"
                }
            ],
            "stateMutability": "nonpayable"
        },
        {
            "type": "function",
            "name": "getBondingCurve",
            "inputs": [
                {
                    "name": "token",
                    "type": "address",
                    "internalType": "address"
                }
            ],
            "outputs": [
                {
                    "name": "curve",
                    "type": "tuple",
                    "internalType": "struct ManiaFactoryUpgradeable.BondingCurve",
                    "components": [
                        {
                            "name": "virtualTokenReserves",
                            "type": "uint256",
                            "internalType": "uint256"
                        },
                        {
                            "name": "virtualEthReserves",
                            "type": "uint64",
                            "internalType": "uint64"
                        },
                        {
                            "name": "realTokenReserves",
                            "type": "uint256",
                            "internalType": "uint256"
                        },
                        {
                            "name": "realEthReserves",
                            "type": "uint64",
                            "internalType": "uint64"
                        },
                        {
                            "name": "tokenTotalSupply",
                            "type": "uint256",
                            "internalType": "uint256"
                        },
                        {
                            "name": "complete",
                            "type": "bool",
                            "internalType": "bool"
                        },
                        {
                            "name": "trackVolume",
                            "type": "bool",
                            "internalType": "bool"
                        }
                    ]
                }
            ],
            "stateMutability": "view"
        },
        {
            "type": "function",
            "name": "getBuyQuote",
            "inputs": [
                {
                    "name": "token",
                    "type": "address",
                    "internalType": "address"
                },
                {
                    "name": "ethAmount",
                    "type": "uint64",
                    "internalType": "uint64"
                }
            ],
            "outputs": [
                {
                    "name": "tokenAmount",
                    "type": "uint256",
                    "internalType": "uint256"
                }
            ],
            "stateMutability": "view"
        },
        {
            "type": "function",
            "name": "getFee",
            "inputs": [
                {
                    "name": "amount",
                    "type": "uint64",
                    "internalType": "uint64"
                }
            ],
            "outputs": [
                {
                    "name": "fee",
                    "type": "uint128",
                    "internalType": "uint128"
                }
            ],
            "stateMutability": "view"
        },
        {
            "type": "function",
            "name": "getSellQuote",
            "inputs": [
                {
                    "name": "token",
                    "type": "address",
                    "internalType": "address"
                },
                {
                    "name": "amount",
                    "type": "uint256",
                    "internalType": "uint256"
                }
            ],
            "outputs": [
                {
                    "name": "ethOutput",
                    "type": "uint128",
                    "internalType": "uint128"
                }
            ],
            "stateMutability": "view"
        },
        {
            "type": "function",
            "name": "global",
            "inputs": [],
            "outputs": [
                {
                    "name": "initialized",
                    "type": "bool",
                    "internalType": "bool"
                },
                {
                    "name": "authority",
                    "type": "address",
                    "internalType": "address"
                },
                {
                    "name": "feeRecipient",
                    "type": "address",
                    "internalType": "address"
                },
                {
                    "name": "initialVirtualTokenReserves",
                    "type": "uint256",
                    "internalType": "uint256"
                },
                {
                    "name": "initialVirtualEthReserves",
                    "type": "uint64",
                    "internalType": "uint64"
                },
                {
                    "name": "initialRealTokenReserves",
                    "type": "uint256",
                    "internalType": "uint256"
                },
                {
                    "name": "tokenTotalSupply",
                    "type": "uint256",
                    "internalType": "uint256"
                },
                {
                    "name": "feeBasisPoints",
                    "type": "uint64",
                    "internalType": "uint64"
                },
                {
                    "name": "withdrawAuthority",
                    "type": "address",
                    "internalType": "address"
                },
                {
                    "name": "enableMigrate",
                    "type": "bool",
                    "internalType": "bool"
                },
                {
                    "name": "poolMigrationFee",
                    "type": "uint64",
                    "internalType": "uint64"
                },
                {
                    "name": "creatorFee",
                    "type": "uint64",
                    "internalType": "uint64"
                }
            ],
            "stateMutability": "view"
        },
        {
            "type": "function",
            "name": "initialize",
            "inputs": [],
            "outputs": [],
            "stateMutability": "nonpayable"
        },
        {
            "type": "function",
            "name": "lastWithdrawTimestamp",
            "inputs": [],
            "outputs": [
                {
                    "name": "",
                    "type": "uint64",
                    "internalType": "uint64"
                }
            ],
            "stateMutability": "view"
        },
        {
            "type": "function",
            "name": "migrate",
            "inputs": [
                {
                    "name": "token",
                    "type": "address",
                    "internalType": "address"
                },
                {
                    "name": "pool",
                    "type": "address",
                    "internalType": "address"
                }
            ],
            "outputs": [],
            "stateMutability": "nonpayable"
        },
        {
            "type": "function",
            "name": "proxiableUUID",
            "inputs": [],
            "outputs": [
                {
                    "name": "",
                    "type": "bytes32",
                    "internalType": "bytes32"
                }
            ],
            "stateMutability": "view"
        },
        {
            "type": "function",
            "name": "sell",
            "inputs": [
                {
                    "name": "token",
                    "type": "address",
                    "internalType": "address"
                },
                {
                    "name": "amount",
                    "type": "uint256",
                    "internalType": "uint256"
                },
                {
                    "name": "minEthOutput",
                    "type": "uint64",
                    "internalType": "uint64"
                }
            ],
            "outputs": [],
            "stateMutability": "nonpayable"
        },
        {
            "type": "function",
            "name": "setParams",
            "inputs": [
                {
                    "name": "params",
                    "type": "tuple",
                    "internalType": "struct ManiaFactoryUpgradeable.SetParamsInput",
                    "components": [
                        {
                            "name": "initialVirtualTokenReserves",
                            "type": "uint256",
                            "internalType": "uint256"
                        },
                        {
                            "name": "initialVirtualEthReserves",
                            "type": "uint64",
                            "internalType": "uint64"
                        },
                        {
                            "name": "initialRealTokenReserves",
                            "type": "uint256",
                            "internalType": "uint256"
                        },
                        {
                            "name": "tokenTotalSupply",
                            "type": "uint256",
                            "internalType": "uint256"
                        },
                        {
                            "name": "feeBasisPoints",
                            "type": "uint64",
                            "internalType": "uint64"
                        },
                        {
                            "name": "withdrawAuthority",
                            "type": "address",
                            "internalType": "address"
                        },
                        {
                            "name": "enableMigrate",
                            "type": "bool",
                            "internalType": "bool"
                        },
                        {
                            "name": "poolMigrationFee",
                            "type": "uint64",
                            "internalType": "uint64"
                        },
                        {
                            "name": "creatorFee",
                            "type": "uint64",
                            "internalType": "uint64"
                        },
                        {
                            "name": "feeRecipient",
                            "type": "address",
                            "internalType": "address"
                        }
                    ]
                }
            ],
            "outputs": [],
            "stateMutability": "nonpayable"
        },
        {
            "type": "function",
            "name": "setTrackVolume",
            "inputs": [
                {
                    "name": "token",
                    "type": "address",
                    "internalType": "address"
                },
                {
                    "name": "enabled",
                    "type": "bool",
                    "internalType": "bool"
                }
            ],
            "outputs": [],
            "stateMutability": "nonpayable"
        },
        {
            "type": "function",
            "name": "updateFeeRecipient",
            "inputs": [
                {
                    "name": "newFeeRecipient",
                    "type": "address",
                    "internalType": "address"
                }
            ],
            "outputs": [],
            "stateMutability": "nonpayable"
        },
        {
            "type": "function",
            "name": "updateGlobalAuthority",
            "inputs": [
                {
                    "name": "newAuthority",
                    "type": "address",
                    "internalType": "address"
                }
            ],
            "outputs": [],
            "stateMutability": "nonpayable"
        },
        {
            "type": "function",
            "name": "upgradeToAndCall",
            "inputs": [
                {
                    "name": "newImplementation",
                    "type": "address",
                    "internalType": "address"
                },
                {
                    "name": "data",
                    "type": "bytes",
                    "internalType": "bytes"
                }
            ],
            "outputs": [],
            "stateMutability": "payable"
        },
        {
            "type": "function",
            "name": "userVolume",
            "inputs": [
                {
                    "name": "user",
                    "type": "address",
                    "internalType": "address"
                }
            ],
            "outputs": [
                {
                    "name": "volume",
                    "type": "uint256",
                    "internalType": "uint256"
                }
            ],
            "stateMutability": "view"
        },
        {
            "type": "function",
            "name": "withdraw",
            "inputs": [
                {
                    "name": "token",
                    "type": "address",
                    "internalType": "address"
                }
            ],
            "outputs": [],
            "stateMutability": "nonpayable"
        },
        {
            "type": "event",
            "name": "CompleteEvent",
            "inputs": [
                {
                    "name": "user",
                    "type": "address",
                    "indexed": true,
                    "internalType": "address"
                },
                {
                    "name": "mint",
                    "type": "address",
                    "indexed": true,
                    "internalType": "address"
                },
                {
                    "name": "timestamp",
                    "type": "uint256",
                    "indexed": false,
                    "internalType": "uint256"
                }
            ],
            "anonymous": false
        },
        {
            "type": "event",
            "name": "CompleteManiaAmmMigrationEvent",
            "inputs": [
                {
                    "name": "user",
                    "type": "address",
                    "indexed": true,
                    "internalType": "address"
                },
                {
                    "name": "mint",
                    "type": "address",
                    "indexed": true,
                    "internalType": "address"
                },
                {
                    "name": "mintAmount",
                    "type": "uint64",
                    "indexed": false,
                    "internalType": "uint64"
                },
                {
                    "name": "ethAmount",
                    "type": "uint64",
                    "indexed": false,
                    "internalType": "uint64"
                },
                {
                    "name": "poolMigrationFee",
                    "type": "uint64",
                    "indexed": false,
                    "internalType": "uint64"
                },
                {
                    "name": "timestamp",
                    "type": "uint256",
                    "indexed": false,
                    "internalType": "uint256"
                },
                {
                    "name": "pool",
                    "type": "address",
                    "indexed": true,
                    "internalType": "address"
                }
            ],
            "anonymous": false
        },
        {
            "type": "event",
            "name": "CreateEvent",
            "inputs": [
                {
                    "name": "name",
                    "type": "string",
                    "indexed": false,
                    "internalType": "string"
                },
                {
                    "name": "symbol",
                    "type": "string",
                    "indexed": false,
                    "internalType": "string"
                },
                {
                    "name": "uri",
                    "type": "string",
                    "indexed": false,
                    "internalType": "string"
                },
                {
                    "name": "mint",
                    "type": "address",
                    "indexed": true,
                    "internalType": "address"
                },
                {
                    "name": "user",
                    "type": "address",
                    "indexed": true,
                    "internalType": "address"
                },
                {
                    "name": "creator",
                    "type": "address",
                    "indexed": true,
                    "internalType": "address"
                },
                {
                    "name": "timestamp",
                    "type": "uint256",
                    "indexed": false,
                    "internalType": "uint256"
                }
            ],
            "anonymous": false
        },
        {
            "type": "event",
            "name": "Initialized",
            "inputs": [
                {
                    "name": "version",
                    "type": "uint64",
                    "indexed": false,
                    "internalType": "uint64"
                }
            ],
            "anonymous": false
        },
        {
            "type": "event",
            "name": "SetParamsEvent",
            "inputs": [
                {
                    "name": "initialVirtualTokenReserves",
                    "type": "uint256",
                    "indexed": false,
                    "internalType": "uint256"
                },
                {
                    "name": "initialVirtualEthReserves",
                    "type": "uint64",
                    "indexed": false,
                    "internalType": "uint64"
                },
                {
                    "name": "initialRealTokenReserves",
                    "type": "uint256",
                    "indexed": false,
                    "internalType": "uint256"
                },
                {
                    "name": "finalRealEthReserves",
                    "type": "uint64",
                    "indexed": false,
                    "internalType": "uint64"
                },
                {
                    "name": "tokenTotalSupply",
                    "type": "uint256",
                    "indexed": false,
                    "internalType": "uint256"
                },
                {
                    "name": "feeBasisPoints",
                    "type": "uint64",
                    "indexed": false,
                    "internalType": "uint64"
                },
                {
                    "name": "withdrawAuthority",
                    "type": "address",
                    "indexed": false,
                    "internalType": "address"
                },
                {
                    "name": "enableMigrate",
                    "type": "bool",
                    "indexed": false,
                    "internalType": "bool"
                },
                {
                    "name": "poolMigrationFee",
                    "type": "uint64",
                    "indexed": false,
                    "internalType": "uint64"
                },
                {
                    "name": "creatorFee",
                    "type": "uint64",
                    "indexed": false,
                    "internalType": "uint64"
                },
                {
                    "name": "feeRecipient",
                    "type": "address",
                    "indexed": false,
                    "internalType": "address"
                },
                {
                    "name": "timestamp",
                    "type": "uint256",
                    "indexed": false,
                    "internalType": "uint256"
                }
            ],
            "anonymous": false
        },
        {
            "type": "event",
            "name": "TradeEvent",
            "inputs": [
                {
                    "name": "mint",
                    "type": "address",
                    "indexed": true,
                    "internalType": "address"
                },
                {
                    "name": "ethAmount",
                    "type": "uint64",
                    "indexed": false,
                    "internalType": "uint64"
                },
                {
                    "name": "tokenAmount",
                    "type": "uint256",
                    "indexed": false,
                    "internalType": "uint256"
                },
                {
                    "name": "isBuy",
                    "type": "bool",
                    "indexed": false,
                    "internalType": "bool"
                },
                {
                    "name": "user",
                    "type": "address",
                    "indexed": true,
                    "internalType": "address"
                },
                {
                    "name": "timestamp",
                    "type": "uint256",
                    "indexed": false,
                    "internalType": "uint256"
                },
                {
                    "name": "virtualEthReserves",
                    "type": "uint64",
                    "indexed": false,
                    "internalType": "uint64"
                },
                {
                    "name": "virtualTokenReserves",
                    "type": "uint256",
                    "indexed": false,
                    "internalType": "uint256"
                },
                {
                    "name": "realEthReserves",
                    "type": "uint64",
                    "indexed": false,
                    "internalType": "uint64"
                },
                {
                    "name": "realTokenReserves",
                    "type": "uint256",
                    "indexed": false,
                    "internalType": "uint256"
                }
            ],
            "anonymous": false
        },
        {
            "type": "event",
            "name": "UpdateFeeRecipientEvent",
            "inputs": [
                {
                    "name": "authority",
                    "type": "address",
                    "indexed": true,
                    "internalType": "address"
                },
                {
                    "name": "oldFeeRecipient",
                    "type": "address",
                    "indexed": true,
                    "internalType": "address"
                },
                {
                    "name": "newFeeRecipient",
                    "type": "address",
                    "indexed": true,
                    "internalType": "address"
                },
                {
                    "name": "timestamp",
                    "type": "uint256",
                    "indexed": false,
                    "internalType": "uint256"
                }
            ],
            "anonymous": false
        },
        {
            "type": "event",
            "name": "UpdateGlobalAuthorityEvent",
            "inputs": [
                {
                    "name": "authority",
                    "type": "address",
                    "indexed": true,
                    "internalType": "address"
                },
                {
                    "name": "newAuthority",
                    "type": "address",
                    "indexed": true,
                    "internalType": "address"
                },
                {
                    "name": "timestamp",
                    "type": "uint256",
                    "indexed": false,
                    "internalType": "uint256"
                }
            ],
            "anonymous": false
        },
        {
            "type": "event",
            "name": "Upgraded",
            "inputs": [
                {
                    "name": "implementation",
                    "type": "address",
                    "indexed": true,
                    "internalType": "address"
                }
            ],
            "anonymous": false
        },
        {
            "type": "event",
            "name": "VolumeTracked",
            "inputs": [
                {
                    "name": "user",
                    "type": "address",
                    "indexed": true,
                    "internalType": "address"
                },
                {
                    "name": "mint",
                    "type": "address",
                    "indexed": true,
                    "internalType": "address"
                },
                {
                    "name": "volumeAmount",
                    "type": "uint256",
                    "indexed": false,
                    "internalType": "uint256"
                },
                {
                    "name": "totalVolume",
                    "type": "uint256",
                    "indexed": false,
                    "internalType": "uint256"
                },
                {
                    "name": "timestamp",
                    "type": "uint256",
                    "indexed": false,
                    "internalType": "uint256"
                }
            ],
            "anonymous": false
        },
        {
            "type": "error",
            "name": "AddressEmptyCode",
            "inputs": [
                {
                    "name": "target",
                    "type": "address",
                    "internalType": "address"
                }
            ]
        },
        {
            "type": "error",
            "name": "AllFeeRecipientsShouldBeNonZero",
            "inputs": []
        },
        {
            "type": "error",
            "name": "AllZerosWithdrawAuthority",
            "inputs": []
        },
        {
            "type": "error",
            "name": "AlreadyInitialized",
            "inputs": []
        },
        {
            "type": "error",
            "name": "BondingCurveComplete",
            "inputs": []
        },
        {
            "type": "error",
            "name": "BondingCurveNotComplete",
            "inputs": []
        },
        {
            "type": "error",
            "name": "BuyZeroAmount",
            "inputs": []
        },
        {
            "type": "error",
            "name": "CreatorShouldNotBeZero",
            "inputs": []
        },
        {
            "type": "error",
            "name": "DisabledMigrate",
            "inputs": []
        },
        {
            "type": "error",
            "name": "DisabledWithdraw",
            "inputs": []
        },
        {
            "type": "error",
            "name": "DivisionByZero",
            "inputs": []
        },
        {
            "type": "error",
            "name": "ERC1967InvalidImplementation",
            "inputs": [
                {
                    "name": "implementation",
                    "type": "address",
                    "internalType": "address"
                }
            ]
        },
        {
            "type": "error",
            "name": "ERC1967NonPayable",
            "inputs": []
        },
        {
            "type": "error",
            "name": "FailedCall",
            "inputs": []
        },
        {
            "type": "error",
            "name": "FeeBasisPointsGreaterThanMaximum",
            "inputs": []
        },
        {
            "type": "error",
            "name": "InitialRealTokenReservesShouldBeLessThanTokenTotalSupply",
            "inputs": []
        },
        {
            "type": "error",
            "name": "InitialVirtualTokenReservesShouldBeGreaterThanInitialRealTokenReserves",
            "inputs": []
        },
        {
            "type": "error",
            "name": "InvalidInitialization",
            "inputs": []
        },
        {
            "type": "error",
            "name": "NotAuthorized",
            "inputs": []
        },
        {
            "type": "error",
            "name": "NotEnoughRemainingAccounts",
            "inputs": []
        },
        {
            "type": "error",
            "name": "NotEnoughTokensToBuy",
            "inputs": []
        },
        {
            "type": "error",
            "name": "NotEnoughTokensToSell",
            "inputs": []
        },
        {
            "type": "error",
            "name": "NotInitializing",
            "inputs": []
        },
        {
            "type": "error",
            "name": "Overflow",
            "inputs": []
        },
        {
            "type": "error",
            "name": "PoolMigrationFeeShouldBeGreaterThanCreatorFeePlusMaxMigrateFees",
            "inputs": []
        },
        {
            "type": "error",
            "name": "PoolMigrationFeeShouldBeLessThanFinalRealEthReserves",
            "inputs": []
        },
        {
            "type": "error",
            "name": "SafeERC20FailedOperation",
            "inputs": [
                {
                    "name": "token",
                    "type": "address",
                    "internalType": "address"
                }
            ]
        },
        {
            "type": "error",
            "name": "SellZeroAmount",
            "inputs": []
        },
        {
            "type": "error",
            "name": "TooLittleEthReceived",
            "inputs": []
        },
        {
            "type": "error",
            "name": "TooMuchEthRequired",
            "inputs": []
        },
        {
            "type": "error",
            "name": "UUPSUnauthorizedCallContext",
            "inputs": []
        },
        {
            "type": "error",
            "name": "UUPSUnsupportedProxiableUUID",
            "inputs": [
                {
                    "name": "slot",
                    "type": "bytes32",
                    "internalType": "bytes32"
                }
            ]
        },
        {
            "type": "error",
            "name": "UnsortedNotUniqueFeeRecipients",
            "inputs": []
        },
        {
            "type": "error",
            "name": "WithdrawTooFrequent",
            "inputs": []
        }
    ],
