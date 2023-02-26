# docker registry

## registry への追加コマンド

- 既存の image をタグ付け

  ```bash
  docker image tag nginx localhost:5000/test
  ```

- タグ付けしたイメージを push

  ```bash
  docker push localhost:5000/test
  ```

  下記のように出力されれば成功

  ```bash
  Using default tag: latest
  The push refers to repository [localhost:5000/test]
  3ea1bc01cbfe: Pushed
  a76121a5b9fd: Pushed
  2df186f5be5c: Pushed
  21a95e83c568: Pushed
  81e05d8cedf6: Pushed
  4695cdfb426a: Pushed
  latest: digest: sha256:7f797701ded5055676d656f11071f84e2888548a2e7ed12a4977c28ef6114b17 size: 1570
  ```

## 確認

- registry 用の UI を追加したほうが良いが、当座は下記でレポジトリの一覧を確認できる

  ```bash
  curl http://localhost:5000/v2/\_catalog
  ```

- イメージごと

  ```bash
  curl http://localhost:5000/v2/test/tags/list
  ```
