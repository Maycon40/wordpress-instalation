# 🚀 Instalação rápida do WordPress

Este projeto automatiza a instalação e configuração completa do WordPress em um servidor remoto usando Ansible.

Com ele você consegue:

✅ Instalar Apache, PHP e MySQL

✅ Configurar VirtualHost do Apache

✅ Criar banco de dados do WordPress

✅ Baixar e configurar o WordPress automaticamente

✅ Deixar o ambiente pronto para uso em minutos
<br/>
<br/>
<br/>


## 📁 Estrutura do projeto
```path
.
├── group_vars_example/
├── templates/
├── example-hosts
├── provisioning.yml
└── .gitignore
```
<br/>
<br/>

## 📌 Objetivo do projeto

Automatizar totalmente o provisionamento de um servidor WordPress usando boas práticas de infraestrutura como código.
<br/>
<br/>

## ⚠️ Passos obrigatórios antes de rodar

### 1️⃣ Renomear a pasta de variáveis
```shell
mv group_vars_example group_vars
```

<br/>

### 2️⃣ Editar as variáveis de configuração

Edite o seguinte arquivo:
```path
group_vars/wordpress.yml
```


Altere todas as variáveis sensíveis, como:

- usuário do banco
- senha do banco
- nome do banco
- chaves de segurança do wordpress

⚠️ Nunca use as credenciais de exemplo em produção

<br/>

### 3️⃣ Criar o arquivo de inventário do Ansible

Copie o modelo:
```shell
cp example-hosts hosts
```

Agora edite o arquivo hosts informando:

- IP do servidor
- Usuário SSH
- Caminho da chave privada

Exemplo:
```txt
[wordpress]
192.168.1.1 ansible_user=ubuntu ansible_ssh_private_key_file=~/.ssh/id_rsa
```
<br/>
<br/>

## 🔐 Requisitos

Instalar o ansible:

```shell
sudo apt install ansible
```


No servidor remoto:

✔ acesso SSH
✔ sistema Ubuntu/Debian recomendado
<br/>
<br/>
<br/>

## ▶️ Como rodar o projeto

Dentro da pasta do repositório:

```shell
ansible-playbook provisioning.yml -i hosts -K
```

O Ansible irá:

- conectar no servidor
- instalar tudo automaticamente
- configurar o WordPress

<br/>
<br/>

## 🌐 Acessar o WordPress

Após finalizar:

Abra no navegador no seguinte link:

http://IP_DO_SERVIDOR

Você verá a tela de configuração inicial do WordPress.
<br/>
<br/>
<br/>

## 🚨 Avisos importantes

✔ Altere todas as credenciais

✔ Proteja sua chave SSH

✔ Use firewall no servidor
