# 概要
yarn package を利用するための手順です。  
yarnは、node modules を利用するためのマネージャーとして利用されます。  
yarnのインストールには、typeormのインストールも含まれます。   
- [typeorm](https://github.com/latonaio/typeorm)

# how to setup
セットアップのためのコマンドは、yarn-install.yaml 内にあります。

```
- name: install yarn
  become: yes
  shell:
    cmd: "npm install --global yarn"
    chdir: "{{ work_dir }}/UI/xxxxxxxx"

- name: yarn install
  become: yes
  shell:
    cmd: yarn install
    chdir: "{{ work_dir }}/UI/xxxxxxxx"

- name: make .yarnrc in xxxxxxxx
  copy:
    dest: "{{ work_dir }}/UI/xxxxxxxx/.yarnrc"
    content: network-timeout 600000
```

