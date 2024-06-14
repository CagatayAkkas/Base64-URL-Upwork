# Guide

1)Copy Test.sol (https://github.com/CagatayAkkas/Base64-URL-Upwork/blob/main/Test.sol)

2)Paste on RemixIDE

3)Connect your web3 wallet

<img width="2156" alt="image" src="https://github.com/CagatayAkkas/Base64-URL-Upwork/assets/108520279/1fe43948-f523-43ce-80b0-f740079d1982">

4)Select Test.sol

<img width="2084" alt="image" src="https://github.com/CagatayAkkas/Base64-URL-Upwork/assets/108520279/ace51182-a453-46cd-a649-e1d706b8ca93">

5)Deploy the contract.

<img width="2084" alt="image" src="https://github.com/CagatayAkkas/Base64-URL-Upwork/assets/108520279/8e7f0e0e-34b7-4deb-bbc9-a4968073dcbf">

6)Enter the id and URL as your choice and click on transact button.

<img width="1846" alt="image" src="https://github.com/CagatayAkkas/Base64-URL-Upwork/assets/108520279/0d829a18-af33-4ff8-9328-725896161aaf">

7)For decoding, type the id you want to see at "retrieveAndDecodeUrl" function

<img width="1848" alt="image" src="https://github.com/CagatayAkkas/Base64-URL-Upwork/assets/108520279/e7020155-d290-4c63-b227-2a36821424cf">



# Functions
+We are storing our URLs at:
```
mapping(uint256 => string) public encodedUrls;
```

+We are sending the url to the blockchain after encoding with:

```
function storeEncodedUrl(uint256 id, string memory url) public {
        bytes memory bytesUrl = bytes(url);
        string memory encodedUrl = Base64.encode(bytesUrl);
        encodedUrls[id] = encodedUrl;
    }
```

+We are retrieving and decoding the element at the position of "id". 

```
function retrieveAndDecodeUrl(uint256 id) public view returns (string memory) {
        string memory encodedUrl = encodedUrls[id];
        bytes memory decodedBytes = Base64.decode(encodedUrl);
        return string(decodedBytes);
    }
```
