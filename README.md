# 國際音標 /IPA/

配方： ℞ **ipa**

[Rime](https://rime.im) 國際音標輸入方案

通過字母、數字和符號轉寫輸入 [國際音標](https://en.wikipedia.org/wiki/International_Phonetic_Alphabet)。
內含「[X-SAMPA](https://en.wikipedia.org/wiki/X-SAMPA)」及「雲龍國際音標」兩種編碼方式。

授權條款：見 [LICENSE](LICENSE)

## 安裝

與其他依託Rime的輸入法一樣，國際音標是一組獨立發行的「輸入方案」數據包（或稱「配方」）。

安裝適合您的設備及操作系統的 [Rime輸入法](https://rime.im/download) 程序後，請按照以下說明，或借助「東風破」配置管理器，或以手動方式安裝、配置國際音標輸入法。

### 依配方安裝

[東風破](https://github.com/rime/plum) 是以「配方」爲單位，自動化安裝、配置輸入法數據包的工具。

使用該工具，運行環境須具備 `bash`、`curl`、`git` 等命令行程序。
Windows系統請參考下文「在Windows系統使用配置管理器」。

1.  首次使用時，可通過一鍵安裝腳本下載「東風破」（置於當前工作目錄下的`plum`子目錄）及最新的預設方案集（默認配置、拼音輸入方案等）。

    ```bash
    curl -fsSL https://git.io/rime-install | bash
    ```
2.  下一步、安裝「國際音標」輸入方案。

    ``` bash
    cd plum
    bash rime-install ipa
    ```

3.  再一步、根據所需的IPA編碼方式啓用輸入方案。

      - 啓用「X-SAMPA」編碼的IPA輸入方案

       ```bash
       bash rime-install custom:add:schema=ipa_xsampa
       ```

      - 啓用「雲龍IPA」輸入方案

       ```bash
       bash rime-install custom:add:schema=ipa_yunlong
       ```

4.  完成以上步驟之後，[重新部署](https://github.com/rime/home/wiki/CustomizationGuide#%E9%87%8D%E6%96%B0%E4%BD%88%E7%BD%B2%E7%9A%84%E6%93%8D%E4%BD%9C%E6%96%B9%E6%B3%95) Rime輸入法的工作數據，使配置生效。

### 在Windows系統使用配置管理器

「小狼毫」用家可利用內置的 [配置管理器](https://github.com/rime/plum#windows-bootstrap-script) 安裝配方。

1.  通過開始菜單項或右擊輸入法狀態圖標，打開「輸入法設定＼方案選單設定」；
    按下「獲取更多輸入方案」按鈕。

2.  在命令行提示後輸入配方 `ipa` 並回車。
    等待下載配方包、複製文件完成，並重新顯示提示文字。

3.  關閉命令行窗口，回到「輸入法設定＼方案選單設定」介面，勾選國際音標輸入方案。

4.  按下「中」按鈕，部署數據。

若該工具不可用，請參考「手動安裝及配置」。

### 手動安裝及配置

1.  從 [GitHub代碼庫](https://github.com/rime/rime-ipa) 下載全部源碼的ZIP包，或單獨下載所需的YAML文件。

2.  打開Rime輸入法 [用戶文件夾](https://github.com/rime/home/wiki/UserData)，將下載的YAML文件移到此處。

3.  啓用國際音標輸入方案。

    在用戶文件夾創建或編輯文件 `default.custom.yaml`，將所需輸入方案的ID加入「輸入方案列表」配置項：

    ```yaml
    patch:            # 若文件中已有該行，無須重複
      schema_list/+:  # 同上；"/+" 表示追加輸入方案，若無 "/+" 則表示以下列方案替換默認列表
        - schema: ipa_xsampa   # 按需選配
        - schema: ipa_yunlong  # 按需選配
    ```

4.  完成以上步驟之後，[重新部署](https://github.com/rime/home/wiki/CustomizationGuide#%E9%87%8D%E6%96%B0%E4%BD%88%E7%BD%B2%E7%9A%84%E6%93%8D%E4%BD%9C%E6%96%B9%E6%B3%95)Rime輸入法的工作數據，使上述配置改動生效。

## 輸入國際音標

在Rime輸入法中按 `F4` 或 ``Control+` `` 打開 [方案選單](https://github.com/rime/home/wiki/UserGuide#%E4%BD%BF%E7%94%A8%E6%96%B9%E6%A1%88%E9%81%B8%E5%96%AE)，選取國際音標輸入方案，即可輸入對應編碼獲得音標符號。

運指齊按快捷鍵 `Control+Shift+1` 在最近使用的兩個輸入方案（如常用的中文輸入法和國際音標）之間相互切換。
