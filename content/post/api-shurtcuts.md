---
title: "MisskeyのAPIをAppleのショートカットアプリから使う"
date: 2023-08-17T18:15:51+09:00

tags: ["tips"]
author: "Soli"

draft: false
---

## APIについて

Misskeyでは多様なAPIが用意されており、これを活用することで様々なアプリケーションを作ることや、プログラムからPolestarにアクセスすることが可能になります。  
どのようなエンドポイントが用意されているかについては、[Misskey Hub](https://misskey-hub.net/docs/api/endpoints.html)をご覧ください。

このページでは、APIの基本的な利用方法と、Appleのショートカットアプリによる活用法をご紹介します。

## 基本的な利用方法

APIを利用する前に、トークンを発行する必要があります。

1. APIを使うときは、まずPolestarにてトークンを発行する必要があります。まずは、[Polestar](https://mi.soli0222.com)にアクセスしましょう。
2. 続いて、設定を開きます。
 ![1786](https://media.soli0222.com/polestar/b3b09f4f-b5de-4aef-8e5e-24b1e77bce09.jpeg)

3. 一番下までスクロールして、APIを選択します。
 ![1787](https://media.soli0222.com/polestar/f0352df9-67dc-4305-bd48-8698207f9825.png)

4. トークンの発行を選択します。
 ![1788](https://media.soli0222.com/polestar/ee334d48-70bc-4b8f-9ec3-62923d8c3da5.png)

5. トークンの名前を決めます。どのアプリケーションに使っているトークンなのかわかりやすい名前が好ましいです。ここでは``psr-hub``とします。
 ![1790](https://media.soli0222.com/polestar/9540f610-e008-4aba-acc8-37a74bfd576f.png)

6. トークンに権限を与えます。セキュリティの観点から、与える権限は最小限にしましょう。ここでは、ノートの作成と削除のみ許可します。
 ![1791](https://media.soli0222.com/polestar/1f7bc404-8a2e-4c97-b075-621825cc41f2.png)

7. 右上のチェックマークを選択すると、トークンが発行されます。このトークンはこの画面でしか表示されないので、どこかにメモしておきましょう。また、このトークンを人に知られてしまうと悪用されかねませんので、管理は厳重にしましょう。
 ![1792](https://media.soli0222.com/polestar/36f9a5f0-516d-4307-996d-1d8297d30d8f.png)

これでトークンの発行は完了です。このトークンを利用することで、外部のアプリケーションからPolestarに対してなんらかのアクションを起こすことができます。

## Appleショートカットアプリによる活用

エンドポイントを叩く際、一般的にはPCのターミナルや、プログラム内でWebリクエストを行いますが、より簡単かつ身近な方法としてAppleショートカットアプリを用いる手法が存在します。

ここでは、Appleショートカットアプリで任意のノートを作成するショートカットを作成していきます。

1. ショートカットアプリを開き、右上のプラスを押して新規のショートカットを作成します。
![00B6](https://media.soli0222.com/polestar/6eef95de-3e33-4136-8007-2a4a0aeafdfb.jpeg)

2. 右上、完了の隣の矢印をタップして名称を変更します。なんでも大丈夫です。
![1794](https://media.soli0222.com/polestar/9e45c1b2-2c8f-41bc-8489-54f69ed5e977.png)

3. 下の検索欄をタップします。
![1795](https://media.soli0222.com/polestar/2ff24b0e-8327-4695-be28-72e17ba6d508.png)

4. ``テキスト``と入力し、「テキスト」を選択します。
![1797](https://media.soli0222.com/polestar/3438bbe3-7a20-4f5a-bd22-160ac07ddb5c.png)

5. すると、テキストブロックが表示されるので、ここにトークンをコピペします。入力が終わったらキーボードの完了を押します。
![1798](https://media.soli0222.com/polestar/b218de7e-38ad-406a-a212-adfd056362a1.png)

6. もう一度検索欄をタップし、``URL``と入力して「URL」を選択します。
![1799](https://media.soli0222.com/polestar/ed92ced4-97d1-4588-982b-dde9d99c394f.png)

7. URLブロックには``https://mi.soli0222.com/api/notes/create``と入力します。
![1800](https://media.soli0222.com/polestar/73a45c93-c076-41a6-9cb8-b5bf9152d473.png)

8. 再び検索欄をタップし、``URL``と入力して「URLの内容を取得」を選択します。
![1801](https://media.soli0222.com/polestar/36cdb9c9-c14a-4040-b236-3b7406b1d23a.png)

9. 生成されたブロックの矢印を押して、中身を展開した後、「GET」の部分をタップして「POST」に変更します。
![1802](https://media.soli0222.com/polestar/f3fe0f41-09db-4a5d-9a6a-6dabf3d621d2.png)

10. 「本文を要求」の部分で新規フィールドを追加します。
![1803](https://media.soli0222.com/polestar/632948b3-8e41-4377-b422-fda7431394eb.png)

11. キーを``i``とし、テキストを「変数のテキスト」にします。
![1804](https://media.soli0222.com/polestar/35ba8560-1406-4780-87a2-4ca6dc9f6510.png)

12. もう一度新規フィールドを追加します。
![1805](https://media.soli0222.com/polestar/cfa02d77-4a43-4c9f-8745-44c0dc05c0aa.png)

13. キーを``text``とし、テキストを任意の文言にします。ここでは``:oyasumisskey:``とします。
![1807](https://media.soli0222.com/polestar/35ff485e-21c8-4cf0-be13-6ba232966312.png)

14. 正しく動作するか確認します。左下の再生ボタンを押しましょう。
![1808](https://media.soli0222.com/polestar/19b1fcd4-4ada-45bf-8256-ba9c640be335.png)

15. プライバシーダイアログが初回の動作のみ表示されます。許可を押しましょう。
![1809](https://media.soli0222.com/polestar/c346b119-58f0-4148-ab30-72a8c14c14bb.png)

16. [Polestar](htttps://mi.soli0222.com)を開いて、正しくノートされていれば完成です！

以上
