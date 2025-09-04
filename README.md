# Nessus pro功能介紹
Nessus Professional 是目前最廣泛使用的弱點掃描工具之一，無論是資安工程師、系統管理員，甚至是顧問，都能透過它快速發現環境中的漏洞與弱點。

---
##  Plugin Detail Locale（語言設定）

Nessus 介面永遠是英文，但你可以在 **About → Plugin Detail Locale** 設定漏洞報告語言：

* 支援 English / 繁體中文 / 簡體中文 / 日文 …
* 影響範圍：Plugin 描述、報告輸出內容
* 不影響：Nessus 管理介面（仍是英文）

---

##  左側選單功能介紹

Nessus Pro 的操作介面雖然固定為英文，但分類清楚，以下是主要功能：
![https://ithelp.ithome.com.tw/upload/images/20250904/20171891HJOKkJuwtY.png](https://ithelp.ithome.com.tw/upload/images/20250904/20171891HJOKkJuwtY.png)

### **Folders**

* **My Scans**
  顯示使用者自己建立的掃描，包含掃描狀態、歷史結果。
  適合日常檢查與追蹤。
    1.   +New Scan![https://ithelp.ithome.com.tw/upload/images/20250904/201718919LjFLIgAk0.png](https://ithelp.ithome.com.tw/upload/images/20250904/201718919LjFLIgAk0.png)
    2.   Scan Template>這裡的Template最下面會解釋到，那這邊我先選Basic Network Scan![https://ithelp.ithome.com.tw/upload/images/20250904/201718911zAtRigZaK.png](https://ithelp.ithome.com.tw/upload/images/20250904/201718911zAtRigZaK.png)
    3.   General Setting![https://ithelp.ithome.com.tw/upload/images/20250904/201718918o8mZnYvcT.png](https://ithelp.ithome.com.tw/upload/images/20250904/201718918o8mZnYvcT.png)
    4.  掃描結果![https://ithelp.ithome.com.tw/upload/images/20250904/20171891AYj5RESDEd.png](https://ithelp.ithome.com.tw/upload/images/20250904/20171891AYj5RESDEd.png)
    >剩下就是準備漫長的修補吧
   
    
  
* **All Scans**
  顯示所有使用者建立的掃描（若有多人共享環境）。
  方便集中管理與跨部門稽核。

* **Trash**
  刪除的掃描會先暫存在這裡，可選擇還原或永久刪除。

---

### **Resources**

* **Policies**
  用來建立與管理 **自訂掃描策略**。
  一旦定義完成，就能反覆套用，適合週期性掃描或公司內部規範。

* **Plugin Rules**
  管理 Nessus 外掛 (Plugins) 的行為，例如：

  * 忽略特定外掛（處理誤報）
  * 調整外掛的嚴重度標籤
  * 停用不必要的檢查

* **Customized Reports**
  自訂報告輸出格式，支援 PDF、CSV、HTML。
  可以根據稽核或客戶需求調整內容，例如是否顯示 Plugin 詳細描述。

* **Terrascan**
  對 **Terraform 檔案 (IaC)** 進行檢查，找出雲端資源設定錯誤與弱點。
  特別適合 DevSecOps 環境，在 CI/CD 階段就能把錯誤攔下來。

---

##  Policies 與 My Scans 的差別

* **從 My Scans 建立**
  適合臨時掃描，直接選擇內建範本（如 Basic Network Scan），調整參數後立即使用。

* **在 Policies 建立**
  適合標準化、長期掃描，可完整自訂 Plugin、Port、認證方式。
  建立好的 Policy 可以被多次套用，減少重複設定。

 簡單說：

* **臨時測試 → My Scans**
* **定期掃描、多人共用 → Policies**

---

##  Policy Templates 功能分類

進入 **Policies → Policy Templates**，可以看到以下幾大類別：

###  Discovery（資產探索）

* **Host Discovery**
  掃描存活主機及其開放 Port。
* **Ping-Only Discovery**
  僅透過 Ping 偵測存活主機，流量極低，適合快速盤點。

---

###  Vulnerabilities（漏洞檢測）

* **Basic Network Scan**
  最常用的掃描，檢查全系統漏洞，適用於大部分情境。
* **Credential Validation**
  驗證登入憑證（Windows/SSH）是否可用。
* **Advanced Scan**
  完全自訂 Plugin、Port、憑證，適合有特定需求的掃描。
* **Advanced Dynamic Scan**
  動態挑選 Plugin，減少不必要的檢查。
* **Malware Scan**
  專門檢測 Windows/Unix 惡意程式。
* **Web Application Tests**
  偵測 Web 應用程式漏洞，例如 SQL Injection、XSS。
* **Credentialed Patch Audit**
  登入系統後，檢查 OS/軟體是否缺少安全更新。
* **Active Directory Starter Scan**
  找出 AD 環境中的錯誤配置與風險。
* **Find AI**
  偵測 AI/ML 相關的應用漏洞。
* **Remote Monitoring and Management**
  檢測遠端監控工具 (RMM) 的安全問題。

---

###  Compliance（合規檢查）

* **Audit Cloud Infrastructure**
  審核 AWS/Azure/GCP 等雲端環境設定。
* **Internal PCI Network Scan**
  針對 PCI DSS 內部稽核設計，檢查支付環境安全。
* **MDM Config Audit**
  檢查 Mobile Device Management 設定。
* **Offline Config Audit**
  分析匯出的設備設定檔（例如 Cisco Router）。
* **PCI Quarterly External Scan**
  符合 PCI 規範的季度外部掃描。
* **Policy Compliance Auditing**
  檢查系統設定是否符合基準（如 CIS Benchmark）。
* **SCAP and OVAL Auditing**
  依照 SCAP/OVAL 標準稽核，常用於政府/金融業。

---



>Nessus Pro 不只是漏洞掃描器，它提供了：

* **Discovery** → 幫助資產盤點
* **Vulnerabilities** → 找出系統與應用弱點
* **Compliance** → 滿足法規與稽核需求
* **Policies** → 建立標準化掃描模板
* **Plugin Rules & Reports** → 調整輸出、減少誤報
* **Terrascan** → DevSecOps 雲端安全檢查

無論是臨時測試還是定期稽核，Nessus Pro 都能提供完整支援。


