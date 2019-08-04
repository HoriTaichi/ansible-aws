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


## ansible-playbookで実行

```
ansible-playbook -i inventory/practice playbooks/practice.yml
```

