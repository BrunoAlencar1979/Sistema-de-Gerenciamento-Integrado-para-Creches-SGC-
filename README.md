# Sistema-de-Gerenciamento-Integrado-para-Creches-SGC-
O Sistema de Gerenciamento Integrado para Creches (SGC) é um software Desktop robusto, desenvolvido em Python (Tkinter) e MySQL, projetado para digitalizar e otimizar as operações diárias de uma instituição de ensino infantil. O foco principal é a segurança, a comunicação transparente e a eficiência administrativa, com módulos dedicados.
## 🚀 Funcionalidades Chave

O sistema opera com três perfis de usuário (Administrador, Professor e Responsável), garantindo segregação de acesso e funcionalidades específicas para cada papel:

| Módulo | Funcionalidades | Perfil(is) |
| :--- | :--- | :--- |
| **Segurança e Acesso** | Login multi-perfil (Admin, Prof, Resp), Hashing de senha (`argon2`). | Todos |
| **Ponto por Geolocation** | Validação de registro de ponto do Funcionário através do cruzamento de **Coordenadas GPS** e **Rede Wi-Fi Segura** (API Flask). | Funcionário (via API) |
| **Comunicação Transparente** | **Agenda Diária** e **Registro de Ocorrências** em tempo real, com visualização imediata pelo Responsável e monitoramento pelo Administrador. | Professor, Responsável, Admin |
| **Gestão Acadêmica** | CRUD completo de Alunos, Turmas, Funcionários e Responsáveis. | Administrador |
| **Controle Financeiro** | Registro de mensalidades, automação de status **'Atrasado'** com base na data de vencimento e baixa de pagamento. | Administrador, Responsável |

## 🛠️ Tecnologias Utilizadas

* **Linguagem:** Python 3.12
* **Interface (Frontend):** Tkinter (`ttk`)
* **Banco de Dados (Backend):** MySQL
* **Segurança / Ponto:** API Flask (Python)
* **Criptografia:** Argon2 (para senhas)
* **Empacotamento:** PyInstaller (para criação do executável `.exe`)

## 🏗️ Arquitetura do Banco de Dados (DER)

O sistema utiliza um banco de dados relacional com 11 tabelas para garantir a integridade e rastreabilidade dos dados.

| Tabela | Função |
| :--- | :--- |
| `Usuarios` | Login e Perfil. |
| `Funcionarios` | Dados pessoais e ligação com Turmas. |
| `Responsaveis` | Dados dos pais/guardiões. |
| `Alunos` | Cadastro central de alunos. |
| `Turmas` | Gestão de turmas e seus professores. |
| `Mensalidades` | Controle de cobranças e pagamentos. |
| `Ocorrencias` | Registro de incidentes (saúde, comportamento). |
| `Agenda_Diaria` | Lançamentos diários (refeições, sono). |
| `Sistema_Config` | Configurações de ponto (Wi-Fi, GPS). |
| `Eventos` | Cadastro de eventos. |
| `Registro_Presenca` | Rastreamento de presença em eventos. |



## 💻 Como Rodar o Projeto

### Pré-requisitos
1.  Python 3.x (Recomendado 3.10+)
2.  Servidor MySQL em execução (localmente ou na nuvem).

### Configuração do Ambiente

1.  **Clone o repositório:**
    ```bash
    git clone [SEU LINK DO REPOSITÓRIO]
    cd programa-creche
    ```
2.  **Instale as dependências:**
    ```bash
    pip install -r requirements.txt
    ```
    *(Crie o arquivo `requirements.txt` listando as bibliotecas: `mysql-connector-python`, `tk`, `argon2-cffi`, `flask`, etc.)*
3.  **Configuração do MySQL:**
    * Crie o banco de dados `creche_db`.
    * Execute os scripts de criação de tabelas (`CREATE TABLE...`).
    * Atualize as credenciais de conexão no arquivo `database.py`.

### Execução

1.  **Inicie a API Flask (Ponto):**
    ```bash
    python api_ponto.py
    ```
2.  **Inicie a Aplicação Desktop (em outra janela do terminal):**
    ```bash
    python main_gui.py
    ```

## 🔑 Acessos de Teste

| Perfil | Email | Senha Padrão |
| :--- | :--- | :--- |
| **Administrador** | `admin@creche.com` | `12345` |
| **Professor** | `cris@creche.com` | `12345` |
| **Responsável** | `irene@creche.com` | `12345` |

---
*Desenvolvido por Bruno de Alencar*
