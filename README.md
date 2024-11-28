# Mini Sistema Operacional (MiniSO)

Este projeto consiste na implementação de um Mini Sistema Operacional (MiniSO) básico, permitindo a criação, manipulação e gerenciamento de usuários, arquivos e diretórios. Ele simula algumas funcionalidades de sistemas operacionais reais, como permissões de usuários e gerenciamento de estruturas de arquivos.

---

## 📁 Estrutura dos Arquivos

### `main.go`
Este é o ponto de entrada do sistema. Ele implementa o fluxo principal do programa, incluindo o menu inicial e o loop principal.

- **Funcionalidades principais:**
  - Inicialização do sistema e verificação de usuários cadastrados.
  - Login de usuários existentes.
  - Adição de novos usuários.
  - Acesso ao shell principal, onde comandos podem ser executados.

### `arquivos.go`
Contém funções relacionadas à manipulação de arquivos e diretórios.

- **Principais funções:**
  - `CriarArquivo`: Cria um novo arquivo e registra permissões para o usuário.
  - `ApagarArquivo`: Remove um arquivo, respeitando permissões do usuário.
  - `CriarDiretorio`: Cria um diretório no sistema.
  - `ApagarDiretorio`: Remove diretórios, com a possibilidade de usar a opção `--force`.
  - `ListarDiretorio`: Lista o conteúdo de um diretório, incluindo arquivos e subdiretórios.

### `comandos.go`
Gerencia a interpretação e execução dos comandos fornecidos no shell.

- **Principais funcionalidades:**
  - Processamento de comandos como `criar`, `apagar` e `listar`.
  - Validação de entradas e argumentos fornecidos pelos usuários.
  - Integração com as funções de manipulação de arquivos e diretórios.

### `permissoes.go`
Gerencia as permissões de acesso a arquivos e diretórios.

- **Principais funcionalidades:**
  - `RegistrarPermissao`: Associa um usuário a um caminho.
  - `VerificarPermissao`: Valida se o usuário possui acesso a um recurso.
  - `RemoverPermissao`: Remove permissões associadas a um arquivo ou diretório.
  - `RemoverPermissoesRecursivas`: Remove permissões para todos os subcaminhos de um diretório.

### `usuarios.go`
Gerencia a criação e autenticação de usuários.

- **Principais funcionalidades:**
  - `CriarUsuario`: Adiciona um novo usuário ao sistema.
  - `LoginUsuario`: Permite que um usuário existente faça login.
  - `CarregarUsuarios` e `SalvarUsuarios`: Gerencia o armazenamento de informações de usuários no sistema.
  - `CapturarSenha`: Coleta senhas de maneira segura.

---

## 📜 Menu Inicial

Ao iniciar o programa, o usuário verá o menu principal:


- **Opção 1 - Fazer Login:**
  - Permite que um usuário existente faça login no sistema.
  - Após o login, o shell principal é acessado.

- **Opção 2 - Adicionar Novo Usuário:**
  - Adiciona um novo usuário ao sistema.
  - Exige nome de usuário e senha.

- **Opção 3 - Finalizar Programa:**
  - Encerra a execução do programa.

---

## 🔧 Navegação no Shell

Após o login, o usuário acessa o shell principal, onde pode executar comandos do MiniSO:

### Exemplos de Comandos

1. **Criar um Diretório**
criar diretorio <nomeDiretorio>

Exemplo:
criar diretorio documentos


2. **Criar um Arquivo**
criar arquivo <nomeArquivo>


Exemplo:
criar arquivo documentos/relatorio.txt



3. **Apagar um Arquivo**
apagar arquivo <nomeArquivo>


Exemplo:
apagar arquivo documentos/relatorio.txt



4. **Apagar um Diretório**
apagar diretorio <nomeDiretorio>


Exemplo:
apagar diretorio documentos



- Use a flag `--force` para apagar diretórios não vazios:
  ```
  apagar diretorio documentos --force
  ```

5. **Listar Conteúdo de um Diretório**
listar diretorio <nomeDiretorio>

Exemplo:
listar diretorio documentos

6. **Sair do Shell**
sair

7. **Finalizar o Programa**
finalizar

---

## 🚀 Exemplos de Fluxo de Uso

### Exemplo 1: Criar um Arquivo
1. No menu inicial, escolha "Fazer login".
2. Após o login, execute o comando:
criar arquivo meusDocumentos/nota.txt


3. O arquivo será criado com permissões associadas ao usuário logado.

### Exemplo 2: Apagar um Diretório com Força
1. Após login, use:
apagar diretorio projetos --force


2. O diretório "projetos" e seu conteúdo serão apagados, independentemente de estar vazio.

---

## 🛠️ Requisitos

- **Go:** Certifique-se de que o Go está instalado na máquina.
- **Arquivos Necessários:** O sistema utiliza os arquivos `usuarios.json` e `permissoes.json` para gerenciamento de dados.

---

## 📌 Observações

- Certifique-se de rodar o programa em um ambiente controlado para evitar perda de dados importantes.
- Sempre utilize os comandos de maneira responsável, especialmente ao usar a flag `--force`.

--- 

## 💡 Contribuições

Contribuições para melhorias neste MiniSO são bem-vindas. Sinta-se à vontade para abrir *issues* ou enviar *pull requests*.






