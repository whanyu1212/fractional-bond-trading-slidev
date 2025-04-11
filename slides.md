---
# You can also start simply with 'default'
theme: default
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://images.unsplash.com/photo-1639322537231-2f206e06af84?fm=jpg&q=60&w=3000&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTV8fGJsb2NrY2hhaW58ZW58MHx8MHx8fDA%3D
# some information about your slides (markdown enabled)
title: Fractional Bond Trading Sharing
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# apply unocss classes to the current slide
class: text-center
# https://sli.dev/features/drawing
drawings:
  persist: false
# slide transition: https://sli.dev/guide/animations.html#slide-transitions
transition: slide-left
# enable MDC Syntax: https://sli.dev/features/mdc
hideInToc: true 
mdc: true
# open graph
# seoMeta:
#  ogImage: https://cover.sli.dev
---

# BondChain

## A Blockchain-Based Platform for Fractional Bond Trading

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Press Space for next page <carbon:arrow-right class="inline"/>
  </span>
</div>

<div class="abs-br m-6 flex gap-2">
  <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon:edit />
  </button>
  <a href="https://github.com/slidevjs/slidev" target="_blank" alt="GitHub" title="Open in GitHub"
    class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

<br>

<style>
h1 {
  background: none;
  background-image: none;
  color: white;
  -webkit-text-fill-color: white;
  -moz-text-fill-color: white;
}
</style>

---
layout: default
hideInToc: true
transition: fade-out
---


# Table of contents

<Toc maxDepth="1"></Toc>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

---
transition: fade-out
---

# Motivation

There are long standing barriers for retail investors to enter the bond market

<div
  v-if="$slidev.nav.currentPage === 3"
  v-motion
  :initial="{ x: -100, opacity: 0}"
  :enter="{ x: 0, opacity: 1, scale: 1, transition: { delay: 100, duration: 1300 } }"
>

- 💰 High minimum investment
- 🏢 Fragmented Secondary Market and Low Liquidity
- ⏱️ Complex Intermediation and Prolonged Settlement Times
- 🔍 Opaque Processes and Elevated Counterparty Risks


<br>
<br>

How about we make the bond divisible using <span class="text-blue-500 font">Blockchain technology</span> <img class="inline h-5 w-5 align-middle" src="https://upload.wikimedia.org/wikipedia/commons/thumb/6/6f/Ethereum-icon-purple.svg/1200px-Ethereum-icon-purple.svg.png" alt="Ethereum"/>? [OCBC's use case](https://www.ocbc.com/group/media/release/2025/ocbc-is-first-bank-in-singapore-to-avail-bespoke-tokenised-bonds-via-asset-tokenisation-platform)

</div>

<!--
You can have `style` tag in markdown to override the style for the current page.
Learn more: https://sli.dev/features/slide-scope-style
-->

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
Here is another comment.
-->

---
transition: slide-up
---

# Addressing the Inefficiencies
using a two-fold approach

<div class="flex gap-4">
  <div 
    class="flex-1"
    v-motion
    :initial="{ x: -100, opacity: 0 }"
    :enter="{ x: 0, opacity: 1, transition: { delay: 300, duration: 800 } }"
  >
    <!-- Left content -->
    <u>Tokenization & Fractional Ownership</u>
    <br>
    <br>
    <div>
    Converts bond into digital tokens that can be fractionally owned, significantly lowering capital barrier
    </div>
  </div>
  <div 
    class="flex-1"
    v-motion
    :initial="{ x: 100, opacity: 0 }"
    :enter="{ x: 0, opacity: 1, transition: { delay: 1000, duration: 800 } }"
  >
    <!-- Right content -->
    <u>Automated & Semi-Decentralised Trading</u>
    <br>
    <br>
    <div>
    Reduces reliance on intermediaries, delivering near-instant transaction settlement
    </div>
  </div>
</div>

<div 
  class="mt-8 flex justify-center"
  v-motion
  :initial="{ y: 50, opacity: 0 }"
  :enter="{ y: 0, opacity: 1, transition: { delay: 1700, duration: 800 } }"
>
  <img src="https://cdn-icons-png.flaticon.com/512/2165/2165640.png" alt="Bond tokenization concept" class="w-1/4 rounded-lg shadow-md" />
</div>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

---
transition: fade-out
---

# Architecture & User Journey

<div class="flex flex-col h-full">
  <!-- Top half with system architecture -->
  <div class="flex-1"
    v-motion
    :initial="{ opacity: 0 }"
    :enter="{ opacity: 1, transition: { duration: 800 } }">

```mermaid
flowchart LR
    subgraph Client["Client Side"]
        UI[Next.js Frontend]
        EJS[Ethers.js and Thirdweb]
        UI <--> EJS
    end

    subgraph Blockchain["Ethereum Network"]
        subgraph Contracts["Smart Contracts"]
            BF[BondFactory]
            TB[TokenizedBond]
            BM[BondMarketPlace]
            MS[MockStableCoin]
            
            BF -->|Creates| TB
            TB -->|Lists on| BM
            TB -->|Uses| MS
            BM -->|Interacts| TB
        end
    end

    User["User/Wallet (MetaMask)"]
    User -->|Connect/Actions| UI
    UI -->|Show Data| User
    UI -->|Prepare Tx| EJS
    User <-->|Sign/Confirm| EJS
    EJS -->|Submit| Blockchain
    Blockchain -->|Result| EJS
    EJS -->|Update| UI

    %% Styling
    classDef client fill:#e6f3ff,stroke:#333,stroke-width:2px
    classDef contracts fill:#f5f5f5,stroke:#333,stroke-width:2px
    classDef user fill:#f9f,stroke:#333,stroke-width:2px
    
    class UI,EJS client
    class BF,TB,BM,MS contracts
    class User user

    %% Container Styling
    style Client fill:#f5f9ff,stroke:#333,stroke-width:2px
    style Blockchain fill:#fff5f5,stroke:#333,stroke-width:2px
    style Contracts fill:#f5f5f5,stroke:#333,stroke-width:2px
```
  </div> <!-- Bottom half with workflow --> <div class="flex-1 mt-8" v-motion :initial="{ y: 80, opacity: 0 }" :enter="{ y: 0, opacity: 1, transition: { delay: 600, duration: 1000 } }">

```mermaid
flowchart LR
    subgraph Platform["<font size=6>User Journey</font>"]
        direction LR
        subgraph "System Deployment"
            D1[Admin] -->|Deploys| D2["Core Contracts
            1. MockStableCoin
            2. BondFactory
            3. BondMarketplace"]
            D2 -->|Creates| D3["Bond Instance
            • Set Parameters
            • Fund Contract"]
            D3 <-->|Lists/Updates| D4[Initial and Continuous Offerings]
        end

        subgraph "Investment"
            A[Investor] -->|Browses| B[Bond Marketplace]
            B -->|Reviews| C["Bond Details
            • Price
            • Coupon Rate
            • Maturity Date"]
            C -->|Approves| E["Stablecoin Spend
            to TokenizedBond"]
            E -->|Executes| F[Purchase via
            Marketplace]
        end

        subgraph "Holding Period"
            F -->|Holds| G[Position]
            G -->|Regular| H[Claim Coupons]
            G -->|Optional| I[Secondary Market]
            
            I -->|Trade| J["P2P Exchange
            1. Approve Tokens
            2. Set Price
            3. Execute"]
            
            I -->|Gift| K["Gift Transfer
            1. Approve Tokens
            2. Execute"]
        end

        subgraph "Maturity"
            H & J & K -->|Until| N[Bond Matures]
            N -->|Redeem| P[Final Payment]
        end
    end

    D4 --> B

    style A fill:#f9f,stroke:#333,stroke-width:2px
    style D1 fill:#f9f,stroke:#333,stroke-width:2px
    style N fill:#bbf,stroke:#333,stroke-width:2px
    style P fill:#bfb,stroke:#333,stroke-width:2px
    
    classDef optional fill:#f96,stroke:#333,stroke-width:1px
    class I,J,K optional
    classDef deployment fill:#e6fff2,stroke:#333,stroke-width:1px
    class D1,D2,D3,D4 deployment

    %% Remove coloring from Platform wrapper
    style Platform fill:none
```

</div> 
</div> <style> h1 { background-color: #2B90B6; background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%); background-size: 100%; -webkit-background-clip: text; -moz-background-clip: text; -webkit-text-fill-color: transparent; -moz-text-fill-color: transparent; } </style>


---
transition: fade-in
---

# Smart Contracts Overview

<div class="flex flex-col h-full">
  <!-- Top half with contract descriptions -->
  <div class="flex-1.1 mb-1"
    v-motion
    :initial="{ opacity: 0, y: -50 }"
    :enter="{ opacity: 1, y: 0, transition: { duration: 1000 } }">

  - `TokenizedBond`: Core asset representation of fractional ownership
  - `BondFactory`: Contract that manages the lifecycle of TokenizedBond instances
  - `BondMarketPlace`: Contract that acts as the unified interface and central hub for users to interact with bond offerings
  - `MockStableCoin`: Contract that simulates a designated payment and settlement currency in a test environment
  </div>

  <br>
  <br>
  <!-- Bottom half with class diagram -->
  <div class="flex-1.4"
    v-motion
    :initial="{ opacity: 0 }"
    :enter="{ opacity: 1, transition: { delay: 600, duration: 800 } }">

```mermaid
classDiagram
    direction LR

    class BondFactory {
        <<Contract>>
        +createTokenizedBond(...) address
        +bondIdToAddress : mapping (uint256 => address)
        +getLatestBond() address
        +getBondDetailsByAddress(address) BondDetails
    }

    class TokenizedBond {
        <<Contract>>
        +ERC20 Functions
        +stablecoin : IERC20
        +purchaseBondFor(address, uint256)
        +claimCouponFor(address)
        +redeemFor(address)
    }

    class BondMarketPlace {
        <<Contract>>
        +bondListings : mapping
        +listBond(uint256, address, uint256)
        +purchaseBond(uint256, uint256)
        +exchangeBonds(...)
    }

    class MockStableCoin {
        <<Contract>>
        +ERC20 Functions
        +mint(address, uint256)
    }

    BondFactory "1" --* "*" TokenizedBond : Creates Instances
    BondMarketPlace ..> BondFactory : Finds Bond Address
    BondMarketPlace "1" --* "*" TokenizedBond : Delegates Actions To
    TokenizedBond "1" --> "1" MockStableCoin : Uses For Payments
```
</div> </div> <style> h1 { background-color: #2B90B6; background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%); background-size: 100%; -webkit-background-clip: text; -moz-background-clip: text; -webkit-text-fill-color: transparent; -moz-text-fill-color: transparent; } h3 { margin-bottom: 0.5rem; } </style>

---
transition: fade-in
---

# Sample Transactions & Logs
Most of the records are valid and immutable on Sepolia

<div 
  class="grid grid-cols-2 gap-2 h-[90%]"
  v-motion
  :initial="{ opacity: 0 }"
  :enter="{ opacity: 1, transition: { duration: 500 } }"
>
  <!-- Left section with animation -->
  <div 
    class="border rounded-lg border-gray-200 bg-gray-50 p-4 overflow-auto"
    v-motion
    :initial="{ x: -50, opacity: 0 }"
    :enter="{ x: 0, opacity: 1, transition: { delay: 300, duration: 800 } }"
  >
    <h3 
      class="text-blue-500 mb-2"
      v-motion
      :initial="{ opacity: 0 }"
      :enter="{ opacity: 1, transition: { delay: 600, duration: 300 } }"
    >
      Purchase Transaction
    </h3>
    <img 
      src="./imgs/1744307788040.jpg"
      v-motion
      :initial="{ scale: 0.9, opacity: 0 }"
      :enter="{ scale: 1, opacity: 1, transition: { delay: 800, duration: 500 } }"
    />
  </div>

  <!-- Right section with animation -->
  <div 
    class="border rounded-lg border-gray-200 bg-gray-50 p-4 overflow-auto"
    v-motion
    :initial="{ x: 50, opacity: 0 }"
    :enter="{ x: 0, opacity: 1, transition: { delay: 500, duration: 800 } }"
  >
    <h3 
      class="text-blue-500 mb-2"
      v-motion
      :initial="{ opacity: 0 }"
      :enter="{ opacity: 1, transition: { delay: 800, duration: 300 } }"
    >
      Coupon Claim Event
    </h3>
    <img 
      src="./imgs/1744308191443.jpg"
      v-motion
      :initial="{ scale: 0.9, opacity: 0 }"
      :enter="{ scale: 1, opacity: 1, transition: { delay: 1000, duration: 500 } }"
    />
  </div>
</div>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
h3 {
  font-size: 1.25rem;
  font-weight: 500;
}
</style>


---
transition: slide-down
---

# Frontend

<div grid="~ cols-2 gap-4">
  <!-- Left column - text content -->
  <div
    v-motion
    :initial="{ opacity: 0, x: -50 }"
    :enter="{ opacity: 1, x: 0, transition: { duration: 800 } }"
  >
    <h3 class="text-blue-500 mb-4">Onboarding & Unified Dashboard</h3>
      <div>
        🚀 Benefits are clearly communicated on the landing page
        <br>
        <br>
        📝 User-friendly form to create an account with ease
        <br>
        <br>
        🔑 Flexible sign-in and authentication options
        <br>
        <br>
        📊 Unified dashboard: View balances, manage bonds
    </div>
    <div class="mt-4 w-full flex justify-center"
    v-motion
    :initial="{ opacity: 0, y: 20 }"
    :enter="{ opacity: 1, y: 0, transition: { delay: 500, duration: 700 } }"
  >
    <img src="./imgs/1744336015296.jpg" alt="Unified dashboard" class="rounded-lg shadow-xl w-4/5" />
  </div>
  </div>

  <!-- Right column - image -->
<div 
  class="flex flex-col items-center justify-between h-full"
  v-motion
  :initial="{ opacity: 0, scale: 0.9 }"
  :enter="{ opacity: 1, scale: 1, transition: { delay: 900, duration: 500 } }"
>
  <!-- Top image -->
  <div class="mb-4 w-full flex">
    <img src="./imgs/1744332282267.jpg" alt="Onboarding" class="rounded-lg shadow-xl w-4/5" />
  </div>
    
  </div>
  
  <!-- Bottom image -->

</div>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
h3 {
  font-size: 1.25rem;
  font-weight: 500;
}
</style>


---
transition: fade-out
hideInToc: true 
---

# Frontend (2)

<div class="flex flex-col h-[90%]">
  <!-- Top half - text content -->
  <div
    class="flex-1 mb-8"
    v-motion
    :initial="{ opacity: 0 }"
    :enter="{ opacity: 1, transition: { duration: 1000 } }"
  >
    <h3 class="text-blue-500 mb-4">Bond Marketplace Features</h3>
    📊 Latest bond listings: Status, price, and issuer info
    <br>
    <br>
    🔍 Searchable interface: Easy navigation by bond index
    <br>
    <br>
    📝 "View Details" drill down
  </div>

  <!-- Bottom half - image -->
  <div 
    class="flex-1 flex items-center justify-center"
    v-motion
    :initial="{ opacity: 0, y: 50 }"
    :enter="{ opacity: 1, y: 0, transition: { delay: 900, duration: 800 } }"
  >
    <img src="./imgs/1744334121226.jpg" alt="Frontend Screenshot" class="w-2/3 rounded-lg shadow-xl w-3/5 border-2 border-gray-200" />
  </div>
</div>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
h3 {
  font-size: 1.25rem;
  font-weight: 500;
}
</style>


---
transition: slide-up
hideInToc: true 
---

# Frontend (3)

<div class="grid grid-cols-2 gap-4 h-[90%]">
  <!-- Left half - Primary Market -->
  <div class="flex flex-col h-full">
    <h3 
      class="text-blue-500 mb-3"
      v-motion
      :initial="{ opacity: 0, y: -20 }"
      :enter="{ opacity: 1, y: 0, transition: { duration: 800 } }"
    >
      Primary Market Actions
    </h3>
    <img 
      src="./imgs/1744334556596.jpg" 
      alt="Primary market interface" 
      class="w-2/3 rounded-lg shadow-md mt-2" 
      v-motion
      :initial="{ opacity: 0, scale: 0.9 }"
      :enter="{ opacity: 1, scale: 1, transition: { delay: 400, duration: 600 } }"
    />
  </div>

  <!-- Right half - Secondary Market -->
  <div class="flex flex-col h-full">
    <h3 
      class="text-green-500 mb-3"
      v-motion
      :initial="{ opacity: 0, y: -20 }"
      :enter="{ opacity: 1, y: 0, transition: { delay: 200, duration: 800 } }"
    >
    </h3>
    <img 
      src="./imgs/1744334611427.jpg" 
      alt="Secondary market interface" 
      class="w-full rounded-lg shadow-md mt-2" 
      v-motion
      :initial="{ opacity: 0, scale: 0.9 }"
      :enter="{ opacity: 1, scale: 1, transition: { delay: 600, duration: 600 } }"
    />
  </div>
</div>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
h3 {
  font-size: 1.25rem;
  font-weight: 600;
}
</style>

---
transition: slide-up
hideInToc: true 
---

# Frontend (4)

<div class="grid grid-cols-2 gap-6 h-[90%]">
  <!-- Left half - Bond Purchase -->
  <div class="flex flex-col h-full">
    <h3 
      class="text-blue-500 mb-3"
      v-motion
      :initial="{ opacity: 0, y: -20 }"
      :enter="{ opacity: 1, y: 0, transition: { duration: 800 } }"
    >
      Secondary Market Actions (P2P)
    </h3>
        <div>
        🤝 Peer-to-peer trading without intermediaries
        <br>
        <br>
        💰 Set your own price and trade quantity
        <br>
        <br>
        ⚡ Near-instant settlement on the blockchain
        <br>
        <br>
        🔒 Secure transactions with full transparency
        </div>
  </div>

  <!-- Right half - Bond Management -->
  <div 
    class="flex flex-col h-full items-center justify-center"
    v-motion
    :initial="{ opacity: 0, scale: 0.9 }"
    :enter="{ opacity: 1, scale: 1, transition: { delay: 1000, duration: 700 } }"
  >
    <img src="./imgs/1744335353059.jpg" alt="P2P Trading Interface" class="w-2/3 rounded-lg shadow-md border-2 border-gray-200" />
  </div>
</div>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
h3 {
  font-size: 1.25rem;
  font-weight: 600;
}
</style>

---
transition: fade-in
---

# Sepolia Deployment
Code snippet and actual contract addresses

<div class="grid grid-cols-2 gap-4 mt-2">
  <!-- Left side - image -->
  <div
    class="flex flex-col items-start"  v-motion
    :initial="{ opacity: 0, x: -50 }"
    :enter="{ opacity: 1, x: 0, transition: { duration: 800 } }"
  >
    <img
      src="./imgs/1744337534249.jpg"
      alt="Sepolia Deployment"
      class="rounded-lg shadow-xl border-2 border-gray-200 w-2/3"
    />
  </div>

  <!-- Right side - text content -->
  <div
  v-motion
  :initial="{ opacity: 0, x: 50 }"
  :enter="{ opacity: 1, x: 0, transition: { delay: 300, duration: 800 } }"
>
  <h3 class="text-blue-500 mb-4">Live on Ethereum Testnet</h3>

  <ul class="list-disc list-inside mb-4 ml-1">
    <li>
      BondFactory:
      <a href="https://sepolia.etherscan.io/address/0x8f0CEd3a1a468d9A4968879F918Bcfb18DA8dc24" target="_blank" rel="noopener noreferrer" class="text-green-600 hover:text-green-400 underline">
        <code>0x8f0...c24</code>
      </a>
    </li>
    <br>
    <br>
    <li>
      BondMarketplace:
      <a href="https://sepolia.etherscan.io/address/0xF66B3B3F6DdD8260B47eE1b00e7ab0e81965Bfd7" target="_blank" rel="noopener noreferrer" class="text-green-600 hover:text-green-400 underline">
        <code>0xF66...fd7</code>
      </a>
    </li>
    <br>
    <br>
    <li>
      MockStableCoin:
      <a href="https://sepolia.etherscan.io/address/0x9A1ac536dCFa4ddf7a219AcF70F9CFd25660eFFf
Decimals
" target="_blank" rel="noopener noreferrer" class="text-green-600 hover:text-green-400 underline">
        <code>0x9A1a...FFf</code>
      </a>
    </li>
    <br>
    <br>
    <li>
      Sample bond address:
      <a href="https://sepolia.etherscan.io/address/0x853EbE377ce1820e834412b96F0c4C4B230df4A6" target="_blank" rel="noopener noreferrer" class="text-green-600 hover:text-green-400 underline">
        <code>0x853...4A6</code>
      </a>
    </li>
  </ul>


</div>
 
</div>


<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
h3 {
  font-size: 1.25rem;
  font-weight: 500;
}
</style>

---
transition: fade-in
---
# Challenges & Future Work

<div class="grid grid-cols-2 gap-6">
  <!-- Left half - Challenges -->
<div
  v-motion
  :initial="{ opacity: 0, x: -50 }"
  :enter="{ opacity: 1, x: 0, transition: { duration: 800 } }"
>
  <h3 
    class="text-red-500 mb-4"
    v-motion
    :initial="{ opacity: 0, y: -20 }"
    :enter="{ opacity: 1, y: 0, transition: { delay: 200, duration: 500 } }"
  >
    Conceptual and Technical Challenges
  </h3>
  
  <div class="space-y-4">
  <!-- Item 1 -->
  <div class="flex items-start">
    <div class="flex-shrink-0 h-6 w-6 rounded-full bg-red-100 flex items-center justify-center text-red-500 mr-3">
      <carbon:warning class="text-sm" />
    </div>
    <div>
      Limited domain knowledge on Blockchain applications in general
      <div class="ml-9 mt-1 text-sm opacity-80"> 
        - Ended up becoming a showcase of coding instead of building actual useful and realistic product
      </div>
    </div>
  </div>

  <!-- Item 2 -->
  <div class="flex items-start">
    <div class="flex-shrink-0 h-6 w-6 rounded-full bg-red-100 flex items-center justify-center text-red-500 mr-3">
      <carbon:warning class="text-sm" />
    </div>
    <div>
      Limited experience with smart contracts and frontend development 
      <div class="ml-9 mt-1 text-sm opacity-80"> 
        - Impacting choices around design patterns and gas cost implications
      </div>
    </div>
  </div>
  <img src="./imgs/1744340734606.jpg" alt="roadmap" class="w-4/5" />
</div>
</div>
  
<!-- Right half - Future Work -->
<div
  v-motion
  :initial="{ opacity: 0, x: 50 }"
  :enter="{ opacity: 1, x: 0, transition: { delay: 400, duration: 800 } }"
>
  <h3
    class="text-blue-500 mb-4"
    v-motion
    :initial="{ opacity: 0, y: -20 }"
    :enter="{ opacity: 1, y: 0, transition: { delay: 600, duration: 500 } }"
  >
    Future Roadmap
  </h3>

  <!-- This goes inside the right-hand column's div -->
  <div class="space-y-4">
    <div class="flex items-start">
      <div class="flex-shrink-0 h-6 w-6 rounded-full bg-blue-100 flex items-center justify-center text-blue-500 mr-3">
        <carbon:rocket class="text-sm" />
      </div>
      <div>
        Fetching of realistic pricing data
        <div class="ml-9 mt-1 text-sm opacity-80">
          - Current model violates real world market dynamics
        </div>
      </div>
    </div>
    <div class="flex items-start">
      <div class="flex-shrink-0 h-6 w-6 rounded-full bg-blue-100 flex items-center justify-center text-blue-500 mr-3">
         <carbon:tool-kit class="text-sm" />
      </div>
      <div>
        Depositing function in exchange for equivalent value of stablecoins
        <div class="ml-9 mt-1 text-sm opacity-80">
          - Current implementations did not consider asset conversion mechanics
        </div>
      </div>
    </div>
    <div class="flex items-start">
      <div class="flex-shrink-0 h-6 w-6 rounded-full bg-blue-100 flex items-center justify-center text-blue-500 mr-3">
         <carbon:test-tool class="text-sm" />
      </div>
      <div>
        Potential rebalancing API
        <div class="ml-9 mt-1 text-sm opacity-80">
          - Compute and recommend optimal bond portfolio compositions based on diverse investment objectives
        </div>
      </div>
    </div>
    <div class="flex items-start">
      <div class="flex-shrink-0 h-6 w-6 rounded-full bg-blue-100 flex items-center justify-center text-blue-500 mr-3">
         <carbon:development class="text-sm" />
      </div>
      <div>
        Adopt a more TDD driven approach
        <div class="ml-9 mt-1 text-sm opacity-80">
          - Improve code quality and enable safer refactoring through more thorough testing
        </div>
      </div>
    </div>


  </div> 

</div>
</div>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
h3 {
  font-size: 1.25rem;
  font-weight: 600;
}
</style>


---
transition: fade-in
---

# Learning Outcomes

<div
  class="flex flex-col max-w-4xl mx-auto"
  v-motion
  :initial="{ opacity: 0, y: 20 }"
  :enter="{ opacity: 1, y: 0, transition: { duration: 800 } }"
>
  <div class="space-y-6 mt-4">
    <div class="flex items-start"> 
      <div class="h-8 w-8 rounded-full bg-purple-500 flex items-center justify-center text-white mr-4 flex-shrink-0 shadow-md">
        <carbon:idea class="text-lg" />
      </div>
      <div> 
        <div class="font-medium text-lg">Importance of adopting a user-centric design</div>
        <div class="mt-2 text-sm opacity-80 ml-2">
          - Clarify contract interactions, required parameters, and potential state conflicts before extensive coding
        </div>
      </div>
    </div>
    <div class="flex items-start"> 
      <div class="h-8 w-8 rounded-full bg-purple-500 flex items-center justify-center text-white mr-4 flex-shrink-0 shadow-md">
        <carbon:chip class="text-lg" /> 
      </div>
      <div>
        <div class="font-medium text-lg">Better understanding of ERC-20 standard</div>
        <div class="mt-2 text-sm opacity-80 ml-2">
          - Allowance, Approval, Ownership related properties
        </div>
      </div>
    </div>
     <div class="flex items-start"> 
    <div class="h-8 w-8 rounded-full bg-blue-500 flex items-center justify-center text-white mr-4 flex-shrink-0 shadow-md">
      <carbon:connect class="text-lg" />
    </div>
    <div> 
      <div class="font-medium text-lg">Eliminating development silos</div>
      <div class="mt-2 text-sm opacity-80 ml-2">
        - Frontend and smart contract developers need consistent communication
      </div>
      <div class="mt-1 text-sm opacity-80 ml-2">
        - Early alignment on interfaces avoids incompatible implementations
      </div>
      <div class="mt-1 text-sm opacity-80 ml-2">
        - Shared understanding of state transitions prevents integration issues
      </div>
    </div>
  </div>
  <div class="flex items-start"> 
  <div class="h-8 w-8 rounded-full bg-green-500 flex items-center justify-center text-white mr-4 flex-shrink-0 shadow-md">
    <carbon:blockchain class="text-lg" />
  </div>
  <div> 
    <div class="font-medium text-lg">Blockchain-specific programming mindset</div>
    <div class="mt-2 text-sm opacity-80 ml-2">
      - Considering state management carefully as all changes are permanent
    </div>
    <div class="mt-1 text-sm opacity-80 ml-2">
      - Optimizing for gas costs to ensure economic viability of transactions
    </div>
    <div class="mt-1 text-sm opacity-80 ml-2">
      - Planning for immutability and designing upgrade patterns when needed
    </div>
  </div>
</div>

  </div>
</div>

<style>
/* Your existing style block - no changes needed here */
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>


---
transition: slide-up
class: text-center pt-10
---

# Demo

<div class="mt-12 grid grid-cols-2 gap-8">
  <div class="flex flex-col items-center">
    <div class="mb-3 text-lg font-medium">Smart Contracts</div>
    <a 
      href="https://sepolia.etherscan.io/address/0x8f0CEd3a1a468d9A4968879F918Bcfb18DA8dc24"
      target="_blank" 
      class="px-5 py-3 bg-blue-50 hover:bg-blue-100 text-blue-700 rounded-lg transition-colors flex items-center border border-blue-200"
    >
      <carbon:code class="mr-2" /> View on Etherscan
    </a>
  </div>
  
  <div class="flex flex-col items-center">
    <div class="mb-3 text-lg font-medium">Source Code</div>
    <a 
      href="https://github.com/whanyu1212/fractional-bond-trading" 
      target="_blank" 
      class="px-5 py-3 bg-blue-50 hover:bg-blue-100 text-blue-700 rounded-lg transition-colors flex items-center border border-blue-200"
    >
      <carbon-logo-github class="mr-2" /> View Repository
    </a>
  </div>
</div>

<div class="mt-10 text-sm opacity-70">
  <div class="flex justify-center items-center">
    <carbon:information class="mr-2" />
    <span>This project is a prototype for demonstration purposes</span>
  </div>
</div>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
  font-size: 3rem !important; /* Reduced from 3.5rem */
  margin-bottom: 0.5rem;
}
</style>

<PoweredBySlidev mt-10 />
