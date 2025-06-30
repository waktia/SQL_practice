## 🔧 前提テーブル構成

この問題集では、以下の2つのテーブルを使用します。
DB2を使用を前提としております。

問題の区分は下記のとおりです
ジャンル1（001–020）: 基本SELECT文の書き方と条件抽出

ジャンル2（021–040）: 集計関数とGROUP BYでの集計分析

ジャンル3（041–060）: サブクエリとJOINで複雑データ抽出

ジャンル4（061–080）: CASE, COALESCE, ROW_NUMBERなど応用クエリ

ジャンル5（081–100）: INSERT・UPDATE・DELETEのデータ操作


table構成は下記のとおりです
### 🟦 EMPLOYEES（社員テーブル）

| カラム名       | 型          | 説明                       |
|----------------|-------------|----------------------------|
| ID             | INTEGER     | 社員ID（主キー）          |
| NAME           | VARCHAR(50) | 氏名                       |
| AGE            | INTEGER     | 年齢                       |
| DEPARTMENT_ID  | INTEGER     | 部署ID（外部キー）        |
| SALARY         | INTEGER     | 給与（単位：円）          |
| HIREDATE       | DATE        | 入社日                     |
| RETIRE_DATE    | DATE        | 退職日（NULL可）          |
| PHONE          | VARCHAR(20) | 電話番号（NULL可）        |

```sql
CREATE TABLE EMPLOYEES (
  ID INTEGER NOT NULL PRIMARY KEY,
  NAME VARCHAR(50) NOT NULL,
  AGE INTEGER,
  DEPARTMENT_ID INTEGER NOT NULL,
  SALARY INTEGER,
  HIREDATE DATE,
  RETIRE_DATE DATE,
  PHONE VARCHAR(20),
  FOREIGN KEY (DEPARTMENT_ID) REFERENCES DEPARTMENTS (DEPARTMENT_ID)
);

| カラム名           | 型           | 説明        |
| -------------- | ----------- | --------- |
| DEPARTMENT\_ID | INTEGER     | 部署ID（主キー） |
| DEPT\_NAME     | VARCHAR(50) | 部署名       |


CREATE TABLE DEPARTMENTS (DEPARTMENT_ID INTEGER NOT NULL PRIMARY KEY, DEPT_NAME VARCHAR(50) NOT NULL)
