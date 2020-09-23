使用ethur.js实现钱包功能，前端使用react的semantic-ui框架

1.指定私钥获取钱包
let privateKey1 = '0xd31eb076b4a43e3dcb08750e1a7af93d88a26ec78327feeadfceb21233555594'
let w1 = new ethers.Wallet(privateKey1)

2. 随机创建一个新的钱包
let w2 = ethers.Wallet.createRandom()

3. 给定json文件，生成钱包
ethers.Wallet.fromEncryptedJson(json, password).then(function (wallet) {

});

4. 给定助记词，生成钱包
let mnemonic = 'scout same naive genius cannon maze differ acquire penalty habit surround ice'
let path0 = "m/44'/60'/0'/0/0" //address : 0xd5957914c31e1d785ccc58237d065dd25c61c4d0
let path1 = "m/44'/60'/0'/0/1" //address : 0x18cec83129c0a766012a26863419640cd5f89400
let w4_a = ethers.Wallet.fromMnemonic(mnemonic, path0)

例：shell m / purpose' / coin_type' / account' / change / address_index

pupose ： 44

coin_type：货币类型

Ether: 60
ETC: 61
BCH:145
BitCoin: 0
account: 账户分割符，==有些模糊==

change：

0：表示为外部账户，用于转账
1：辨识为内部账户，用于找零钱（change）
address_index：不同的账户，由0开始递增，==在前一个账户没有交易的情况下，不要允许创建新的账户==

5. 随机创建一个助记词钱包
let randValue = ethers.utils.randomBytes(16)
let w5_mnemonic = ethers.utils.HDNode.entropyToMnemonic(randValue)