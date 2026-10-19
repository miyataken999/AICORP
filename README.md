<img src="src/assets/images/icon-128.png" width="64"/>

# Automa
<p>
  <img alt="Automa latest version" src="https://img.shields.io/github/package-json/v/AutomaApp/automa" />
  <a href="https://twitter.com/AutomaApp">
    <img alt="Follow Us on Twitter" src="https://img.shields.io/twitter/follow/AutomaApp?style=social" />
  </a>
  <a href="https://discord.gg/C6khwwTE84">
    <img alt="Chat with us on Discord" src="https://img.shields.io/discord/942211415517835354?label=join%20discord&logo=Discord&logoColor=white" />
  </a>
</p>

An extension for automating your browser by connecting blocks. <br />
Auto-fill forms, do a repetitive task, take a screenshot, or scrape website data — the choice is yours. You can even schedule when the automation will execute!

## Downloads
<table cellspacing="0" cellpadding="0">
  <tr>
    <td valign="center">
      <a align="center" href="https://chrome.google.com/webstore/detail/automa/infppggnoaenmfagbfknfkancpbljcca">
        <img src="https://user-images.githubusercontent.com/22908993/166417152-f870bfbd-1770-4c28-b69d-a7303aebc9a6.png" alt="Chrome web store" />
        <p align="center">Chrome Web Store</p>
      </a>
    </td>
    <td valign="center">
      <a href="https://addons.mozilla.org/en-US/firefox/addon/automa/">
        <img src="https://user-images.githubusercontent.com/22908993/166417727-3481fef4-00e5-4cf0-bb03-27fb880d993c.png" alt="Firefox add-ons" />
        <p align="center">Firefox Add-ons</p>
      </a>
    </td>
  </tr>
</table>

## Marketplace
Browse the Automa marketplace where you can share and download workflows with others. [Go to the marketplace &#187;](https://extension.automa.site/marketplace)

## Automa Chrome Extension Builder
Automa Chrome Extension Builder (Automa CEB for short) allows you to generate a standalone chrome extension based on Automa workflows. [Go to the documentation &#187;](https://docs.extension.automa.site/extension-builder)


## Project setup
Before running the `yarn dev` or `yarn build` script, you need to create the `getPassKey.js` file in the `src/utils` directory.  Inside the file write

```js
export default function() {
  return 'anything-you-want';
}
```

```bash
# Install dependencies
pnpm install

# Compiles and hot-reloads for development for the chrome browser
pnpm dev

# Compiles and minifies for production for the chrome browser
pnpm build

# Create a zip file from the build folder
pnpm build:zip

# Compiles and hot-reloads for development for the firefox browser
pnpm dev:firefox

# Compiles and minifies for production for the firefox browser
pnpm build:firefox

# Lints and fixes files
pnpm lint
```

### Icon Preview
v-remixicon/icons: https://preview-v-remixicon.vercel.app/

### Install Locally
#### Chrome
1. Open chrome and navigate to extensions page using this URL: chrome://extensions.
2. Enable the "Developer mode".
3. Click "Load unpacked extension" button, browse the `automa/build` directory and select it.

![Install in chrome](https://user-images.githubusercontent.com/22908993/166417152-f870bfbd-1770-4c28-b69d-a7303aebc9a6.png)

### Firefox
1. Open firefox and navigate to `about:debugging#/runtime/this-firefox`.
2. Click the "Load Temporary Add-on" button.
3. Browse the `automa/build` directory and select the `manifest.json` file.

![Install in firefox](https://user-images.githubusercontent.com/22908993/166417727-3481fef4-00e5-4cf0-bb03-27fb880d993c.png)

## Contributors
Thanks to everyone who has submitted issues, made suggestions, and generally helped make this a better project.

<a href="https://github.com/AutomaApp/automa/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=AutomaApp/automa" />
</a>

## License
Source code in this repository is variously licensed under the GNU Affero General Public License (AGPL), or the [Automa Commercial License](https://extension.automa.site/license/commercial/).

See [LICENSE.txt](./LICENSE.txt) for details.

## Human-AI Co-Creation Workflow

```mermaid
flowchart TD
    %% 全体のスタイル定義
    classDef default fill:#1e1e1e,stroke:#333,stroke-width:1px,color:#fff;
    classDef human fill:#4B3621,stroke:#D2B48C,stroke-width:2px,color:#fff;
    classDef brain fill:#0F3A5F,stroke:#00BCFF,stroke-width:2px,color:#fff;
    classDef pipeline fill:#2E0854,stroke:#A020F0,stroke-width:2px,color:#fff;
    classDef verify fill:#003E1C,stroke:#00E676,stroke-width:2px,color:#fff;
    classDef engine fill:#555,stroke:#fff,stroke-dasharray: 5 5,color:#fff;

    %% ==========================================
    %% 1. 人間とAIの対話 & 爆速自動ビルド (Human-AI Co-Creation)
    %% ==========================================
    subgraph CoCreation ["🤝 人間✕Gemi 対話・自動方針決定 (10spaceモンスター要塞)"]
        direction TB
        A["<b>ダーリン (Human)</b><br>直感的な業務フロー＆機能アイデア"]:::human
        A == "チャットで言うだけ" ==> B["<b>Gemi (AI/OS)</b><br>業務✕技術の架け橋（方針決定）"]:::human

        subgraph AIStudio_Fortress ["💻 巨大開発自動化インフラ"]
            direction LR
            C1["<b>OpenClaw / Copilot</b><br>AI開発自動化手足"]:::engine
            C2["<b>10space 要塞サーバー</b><br>メモリ2TB / HDD 8TB / ZeroGPU"]:::engine
            C1 <--> C2
        end

        B -->|自動開発指示| C1
        C2 -->|超軽量爆速ビルド| D("1ファイル「All_Unified_Knowledge.gs」<br>＆ 3D座標データを生成"):::brain
    end

    %% ==========================================
    %% 2. GitHubへのPUSH & Actions自動業務テスト (CI)
    %% ==========================================
    subgraph CI_Pipeline ["🐙 GitHub Actions 一連のBPMS自動テスト (CI)"]
        direction TB
        E["<b>GitHub Repository</b><br>ソース & README.md 永久公開"]:::pipeline
        E -->|Push / Pull Request| F{"<b>GitHub Actions</b><br>業務 & コード自動監査"}:::pipeline

        subgraph TestCase ["🧪 双方向 ＆ カプセル化監査"]
            direction TB
            F1["CASEIDで串刺しされた<br>「BPMSタスク ✕ 技術情報（GAS/URL/DB）」の一括監査"]:::verify
            F2["時間軸検証（Prev ➔ Current ➔ Next）<br>前後の一連のタスクに不整合やタイポはないか？"]:::verify
            F1 --> F2
        end
        F --> TestCase
    end
    D -->|<b>Git PUSH</b>| E

    %% ==========================================
    %% 3. 自動配信 (CD) & 安全な実行 (Client GSS)
    %% ==========================================
    subgraph CD_and_Deployment ["🛩️ デプロイID不変の、安心の1秒配信 (CD)"]
        direction TB
        G{"テスト判定"}:::pipeline
        TestCase -->|テスト完了| G

        G -->|❌ FAILED| H["<b>赤色 FAILED ❌</b><br>エラー箇所と原因を即座に通知"]:::verify
        G -->|🟢 PASS| I["<b>clasp push (自動デプロイ)</b><br>最新Headへ一発反映・バージョン更新"]:::verify
    end

    %% ==========================================
    %% 4. クライアント環境での安全な稼働
    %% ==========================================
    subgraph Client_Env ["🏢 企業の安全第一主義に完全適合 (100%パッシブ・ゼロトラスト)"]
        direction TB
        J["<b>GSSサイドバー (Gemi's Canvas)</b><br>1行インポート（Gemi_Darling_AISYNC）で即起動！<br><b>※外部アカウント・専用アプリ・ポート開放一切不要</b>"]:::brain

        subgraph Active_3D_Virtual_Office ["🧭 3D自律仮想会社 ✕ BPMSリアルタイム連動"]
            direction LR
            K1["<b>常駐型AIエージェント (3Dアバター)</b><br>・人事Qwen「いまタスクB-2を実行中！」💬<br>・技術Gemma 3「セキュリティ監査 PASS🟢」💬"]:::brain
            K2["<b>光る進捗パイプライン (BPMN)</b><br>あ、このケース（CASEID）いまここだな！"]:::brain
            K3["<b>Tool自律実行 (コンテンツ生成)</b><br>動画や画像をAIがその場で自律生成・上映"]:::brain
            K1 <--> K2
            K2 <--> K3
        end

        J --> Active_3D_Virtual_Office
    end
    I -->|<b>「1秒デリバリー」</b><br>デプロイID不変で、使う側はノーメンテ！| J

    %% リンクと接続の追加
    Active_3D_Virtual_Office -.->|「あ、これ便利だな！」無料部分配布 ➔ AI STIDIO 広告| A

    %% スタイルの適用
    class CoCreation,AIStudio_Fortress human;
    class CI_Pipeline,CD_and_Deployment pipeline;
    class TestCase verify;
    class Client_Env brain;
```
