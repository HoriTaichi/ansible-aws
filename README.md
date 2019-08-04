# ansible-aws

## サーバ要件

Ansible2.8ではPython 2（バージョン2.7）またはPython 3（バージョン3.5以降）がインストールされているどのマシンからでも実行できます。

## Ansibleインストール

mac環境で確認してるので、その内容を記載します.

```
sudo pip install ansible
```

バージョン確認はこちら
```
ansible --version
```

## 疎通確認

```
ansible practice_server -i inventory/practice -m setup
```

## EC2に入って、EPELレポジトリを有効にする
```
ssh -F ssh_config aws
sudo amazon-linux-extras install -y epel
```

## EC2に入って、amzn-mainリポジトリの優先度を下げる
```
sudo vim /etc/yum.repos.d/amzn2-core.repo
-priority=10
+priority=99
```
参考URL:https://blog.adachin.me/archives/9596


## Amazon Console画面からセキュリティーグループの設定を行う

[インバウンド] -> [編集] -> タイプHTTPの設定を行う

## ansible-playbookで実行
差分確認
```
ansible-playbook -i inventory/practice playbooks/practice.yml --diff
```

実行
```
ansible-playbook -i inventory/practice playbooks/practice.yml
```

