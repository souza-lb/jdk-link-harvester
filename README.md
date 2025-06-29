# 🚀 JDK Link Harvester - Coletor de Links JDK

**Um script inteligente para coletar e organizar links de binários do JDK diretamente do repositório oficial**  
`v1.0` · `Shell Script` · ⏱️ Atualizado em 29/06/2025

## 🌟 Visão Geral

O **JDK Link Harvester** é um utilitário em shell script que automatiza a busca, filtragem e organização de links para binários do JDK (Java Development Kit) diretamente do repositório oficial. Ideal para:

- Administradores de sistemas Java
- Desenvolvedores que precisam de versões específicas do JDK
- Ambientes com restrição de acesso a repositórios oficiais
- Automação de instalações em múltiplos servidores

## ⚙️ Parâmetros Configuráveis
| Variável         | Valor Padrão                    | Descrição                                  |
|------------------|---------------------------------|--------------------------------------------|
| `BASE_URL`       | `https://jdk.java.net/archive/` | Repositório oficial do JDK                 |
| `EXTENSION`      | `linux-x64_bin.tar.gz`          | Arquitetura e formato do binário           |
| `OUTPUT_FILE`    | `link-jdk.txt`                  | Arquivo de saída com links                 |

## 🛠️ Como Usar

### 📦 Execução Direta via URL
No terminal com sua conta de usuário comum execute:

```bash
wget -qO- https://raw.githubusercontent.com/souza-lb/jdk-link-harvester/main/get-link-jdk | bash
```

### 📥 Clonar e executar via Git
Para personalização e controle total:

```bash
# 1. Clone o repositório
git clone https://github.com/souza-lb/jdk-link-harvester.git

# 2. Acesse o diretório
cd jdk-link-harvester

# 3. Dê permissão de execução
chmod +x get-link-jdk

# 4. Execute o script
./get-link-jdk
```

### ▶️ Execução Básica
```bash
./get-link-jdk
```

### 📝 Saída Esperada
```
🚀 Iniciando busca em: https://jdk.java.net/archive/
🔍 Procurando por arquivos .linux-x64_bin.tar.gz
⏳ Aguarde alguns instantes...
📁 Processando: https://jdk.java.net/archive/
📊 Ordenando por versão e removendo duplicatas...

📋 Lista de links ordenados:
  ✅ https://jdk.java.net/archive/openjdk-21.0.2_linux-x64_bin.tar.gz
  ✅ https://jdk.java.net/archive/openjdk-20.0.1_linux-x64_bin.tar.gz
  ... [outros links]

✅ Busca concluída!
=================================
📦 Arquivos encontrados:    58
🔧 Após remover duplicatas: 55
💾 Links salvos em:         link-jdk.txt
=================================
```

### 🔄 Atualizando Parâmetros
Para buscar outras arquiteturas (ex: macOS):
```bash
# Edite o script e modifique:
EXTENSION="macos-x64_bin.tar.gz"
```

## ⚠️ Dependências

### 📦 Instalação do Curl
O script requer `curl` para funcionar. Instale conforme seu sistema:

| Sistema Operacional      | Comando de Instalação       |
|--------------------------|-----------------------------|
| **Debian/Ubuntu**        | `sudo apt-get install curl` |
| **RHEL/CentOS**          | `sudo yum install curl`     |
| **Arch Linux**           | `sudo pacman -S curl`       |
| **macOS (Homebrew)**     | `brew install curl`         |

## 🧩 Detalhes Técnicos

### 🔍 Algoritmo de Filtragem
1. Coleta todos os links da página principal do repositório JDK
2. Filtra links pela extensão especificada (ex: `.linux-x64_bin.tar.gz`)
3. Extrai versões dos nomes de arquivo (removendo prefixos/sufixos)
4. Remove duplicatas mantendo a versão mais recente

### 📊 Ordenação Inteligente
As versões são processadas em 3 etapas:
```bash
# 1. Extração da versão do nome do arquivo:
"openjdk-21.0.2_linux-x64_bin.tar.gz" → "21.0.2"

# 2. Ordenação semântica por versão:
sort -Vu

# 3. Remoção de duplicatas e reconstrução das URLs
```

### ⚡ Otimizações
- Uso de arquivos temporários (`mktemp`) para processamento eficiente
- Contagem precisa de arquivos válidos vs. duplicados
- Mensagens de status intuitivas com emojis visuais
- Saída formatada para fácil leitura e integração
- Tratamento de erros para dependência do curl

---

## ❤️ Apoie o Projeto

**Dúvidas, sugestões e contribuições?**  
Leonardo Bruno  
souzalb@proton.me  

**Gostou do projeto e quer realizar uma contribuição voluntária?**  
*(Pode ser o valor de uma xícara de café ou chá...) ☕ 🍵*  

Chave PIX:  
`8dcc7e3c-0c6a-4c6f-a4c0-26a5e62686db`  

Ou utilize o QR Code abaixo:  

<p align="center">
  <img src="images/qrcode-pix.png" alt="QR Code PIX" width="200">
</p>

**Você também pode utilizar o PayPal:**  

[![PayPal](https://img.shields.io/badge/Donate-PayPal-00457C?style=for-the-badge&logo=paypal)](https://www.paypal.com/donate/?hosted_button_id=EQVW5QQ7GBGSY)

<p align="center">
  <img src="images/qrcode-paypal.png" alt="QR Code PayPal" width="200">
</p>

**A utilização deste projeto é livre para alterações e adaptações**  
*Desde que feita a devida referência ao repositório original e seu criador.*
