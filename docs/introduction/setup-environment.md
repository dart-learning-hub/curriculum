# Setup Completo do Ambiente
## Configuração do dart-learning-hub e Ferramentas

---

## 🛠️ Instalação das Ferramentas Básicas

### 1. Dart SDK

#### Windows
```bash
# Usando Chocolatey
choco install dart-sdk

# Verificar instalação
dart --version
```

#### macOS
```bash
# Usando Homebrew
brew tap dart-lang/dart
brew install dart

# Verificar instalação
dart --version
```

#### Linux
```bash
# Usando apt
sudo apt-get update
sudo apt-get install apt-transport-https
wget -qO- https://dl-ssl.google.com/linux/linux_signing_key.pub | sudo gpg --dearmor -o /usr/share/keyrings/dart.gpg
echo 'deb [signed-by=/usr/share/keyrings/dart.gpg arch=amd64] https://storage.googleapis.com/download.dartlang.org/linux/debian stable main' | sudo tee /etc/apt/sources.list.d/dart_stable.list

sudo apt-get update
sudo apt-get install dart

# Adicionar ao PATH no ~/.bashrc ou ~/.zshrc
export PATH="$PATH:/usr/lib/dart/bin"

# Verificar instalação
dart --version
```

### 2. Flutter SDK

#### Windows
```bash
# 1. Baixar Flutter SDK de https://flutter.dev/docs/get-started/install/windows
# 2. Extrair o arquivo zip
# 3. Adicionar flutter\bin ao PATH do sistema

# Verificar instalação
flutter doctor
```

#### macOS
```bash
# Baixar e extrair Flutter
cd ~/development
git clone https://github.com/flutter/flutter.git -b stable

# Adicionar ao PATH no ~/.zshrc ou ~/.bash_profile
export PATH="$PATH:~/development/flutter/bin"

# Verificar instalação
flutter doctor
```

#### Linux
```bash
# Baixar e extrair Flutter
cd ~/development
git clone https://github.com/flutter/flutter.git -b stable

# Adicionar ao PATH no ~/.bashrc ou ~/.zshrc
export PATH="$PATH:~/development/flutter/bin"

# Verificar instalação
flutter doctor
```

#### Completar Setup do Flutter
```bash
# Aceitar licenças do Android
flutter doctor --android-licenses

# Instalar dependências
flutter precache

# Verificar tudo
flutter doctor -v
```

### 3. Visual Studio Code

#### Instalação
- Baixar de https://code.visualstudio.com/
- Instalar seguindo o assistente

#### Extensões Essenciais
Instalar via linha de comando ou Marketplace:

```bash
# Dart e Flutter
code --install-extension dart-code.dart-code
code --install-extension dart-code.flutter

# Git
code --install-extension eamodio.gitlens
code --install-extension mhutchie.git-graph

# Úteis para desenvolvimento
code --install-extension usernamehw.errorlens
code --install-extension christian-kohler.path-intellisense
code --install-extension esbenp.prettier-vscode
```

#### Configurações Recomendadas (settings.json)
```json
{
  "dart.flutterSdkPath": "/caminho/para/flutter",
  "dart.lineLength": 80,
  "editor.formatOnSave": true,
  "editor.rulers": [80],
  "files.autoSave": "afterDelay",
  "files.autoSaveDelay": 1000,
  "[dart]": {
    "editor.defaultFormatter": "Dart-Code.dart-code",
    "editor.formatOnSave": true,
    "editor.formatOnType": true,
    "editor.rulers": [80],
    "editor.selectionHighlight": false,
    "editor.suggestSelection": "first",
    "editor.tabCompletion": "onlySnippets",
    "editor.wordBasedSuggestions": "off"
  }
}
```

### 4. Claude Code

#### Instalação
```bash
# Instalar Claude Code
npm install -g @anthropic-ai/claude-code

# Ou com yarn
yarn global add @anthropic-ai/claude-code

# Verificar instalação
claude-code --version
```

#### Integração com VS Code
1. Abrir VS Code
2. Pressionar `Ctrl+Shift+P` (ou `Cmd+Shift+P` no macOS)
3. Digitar "Claude Code: Connect"
4. Seguir instruções para autenticação

#### Configuração Inicial
```bash
# Configurar API key (se necessário)
claude-code config set api-key YOUR_API_KEY

# Testar conexão
claude-code test
```

---

## 📁 Estrutura do Repositório GitHub

### Organização: dart-learning-hub

#### Estrutura de Diretórios
```
dart-learning-hub/
│
├── .github/
│   ├── workflows/
│   │   ├── dart-tests.yml
│   │   └── flutter-tests.yml
│   └── ISSUE_TEMPLATE/
│       ├── bug_report.md
│       └── feature_request.md
│
├── modulo-1-dart-fundamentos/
│   ├── semana-1-sintaxe-basica/
│   │   ├── dia-1-2-ambiente-hello-world/
│   │   │   ├── README.md
│   │   │   ├── hello_world/
│   │   │   └── calculadora_terminal/
│   │   ├── dia-3-4-variaveis-tipos/
│   │   │   ├── README.md
│   │   │   └── conversor_unidades/
│   │   └── dia-5-7-operadores-fluxo/
│   │       ├── README.md
│   │       └── jogo_adivinhacao/
│   ├── semana-2-estruturas-funcoes/
│   ├── semana-3-orientacao-objetos/
│   ├── semana-4-assincrono-avancado/
│   └── projeto-final-modulo-1/
│
├── modulo-2-vaden/
│   ├── semana-5-fundamentos/
│   ├── semana-6-avancado/
│   └── projeto-final-modulo-2/
│
├── modulo-3-flutter-fundamentos/
│   ├── semana-7-widgets-basicos/
│   ├── semana-8-interface-interacao/
│   ├── semana-9-gerenciamento-estado/
│   ├── semana-10-persistencia-networking/
│   ├── semana-11-recursos-avancados/
│   └── projeto-final-modulo-3/
│
├── modulo-4-mcp/
│   ├── semana-12-fundamentos-mcp/
│   ├── semana-13-flutter-mcp/
│   └── projeto-final-modulo-4/
│
├── projetos-praticos/
│   ├── calculadora-avancada/
│   ├── gerenciador-tarefas/
│   ├── cliente-api-rest/
│   └── app-completo-final/
│
├── recursos/
│   ├── snippets/
│   │   ├── dart-snippets.json
│   │   └── flutter-snippets.json
│   ├── templates/
│   │   ├── projeto-dart-template/
│   │   └── projeto-flutter-template/
│   └── cheatsheets/
│       ├── dart-cheatsheet.md
│       └── flutter-cheatsheet.md
│
├── documentacao/
│   ├── gitbook/
│   │   ├── SUMMARY.md
│   │   └── book.json
│   └── anotacoes/
│
├── .gitignore
├── README.md
├── LICENSE
└── CONTRIBUTING.md
```

### Criação da Estrutura

#### Script de Inicialização
Criar arquivo `setup-repo.sh`:

```bash
#!/bin/bash

# Criar estrutura de diretórios para dart-learning-hub

echo "Criando estrutura do repositório dart-learning-hub..."

# Módulo 1
mkdir -p modulo-1-dart-fundamentos/semana-{1..4}-{sintaxe-basica,estruturas-funcoes,orientacao-objetos,assincrono-avancado}
mkdir -p modulo-1-dart-fundamentos/projeto-final-modulo-1

# Módulo 2
mkdir -p modulo-2-vaden/semana-{5..6}-{fundamentos,avancado}
mkdir -p modulo-2-vaden/projeto-final-modulo-2

# Módulo 3
mkdir -p modulo-3-flutter-fundamentos/semana-{7..11}-{widgets-basicos,interface-interacao,gerenciamento-estado,persistencia-networking,recursos-avancados}
mkdir -p modulo-3-flutter-fundamentos/projeto-final-modulo-3

# Módulo 4
mkdir -p modulo-4-mcp/semana-{12..13}-{fundamentos-mcp,flutter-mcp}
mkdir -p modulo-4-mcp/projeto-final-modulo-4

# Projetos práticos
mkdir -p projetos-praticos/{calculadora-avancada,gerenciador-tarefas,cliente-api-rest,app-completo-final}

# Recursos
mkdir -p recursos/{snippets,templates,cheatsheets}
mkdir -p recursos/templates/{projeto-dart-template,projeto-flutter-template}

# Documentação
mkdir -p documentacao/{gitbook,anotacoes}

# GitHub
mkdir -p .github/{workflows,ISSUE_TEMPLATE}

echo "Estrutura criada com sucesso!"
```

#### Executar o Script
```bash
# Dar permissão de execução
chmod +x setup-repo.sh

# Executar
./setup-repo.sh
```

### Templates de Arquivos

#### README.md Principal
```markdown
# Dart Learning Hub 🎯

Trilha completa de aprendizado em Dart, Flutter, Vaden e MCP.

## 📚 Sobre o Projeto

Esta é uma trilha de aprendizado estruturada e progressiva que leva você do zero ao desenvolvimento profissional com Dart e Flutter, incluindo o framework Vaden e a integração com Model Context Protocol (MCP).

## 🗂️ Estrutura

- **Módulo 1:** Fundamentos Completos do Dart (4 semanas)
- **Módulo 2:** Desenvolvimento com Vaden (2 semanas)
- **Módulo 3:** Fundamentos Completos do Flutter (5 semanas)
- **Módulo 4:** Model Context Protocol para Dart/Flutter (2 semanas)

## 🚀 Como Usar

1. Clone este repositório
2. Siga a trilha em ordem sequencial
3. Complete todos os projetos práticos
4. Documente seu aprendizado

## 📖 Documentação

A documentação completa está disponível no [GitBook](link-do-seu-gitbook).

## 🤝 Contribuindo

Contribuições são bem-vindas! Veja [CONTRIBUTING.md](CONTRIBUTING.md) para detalhes.

## 📝 Licença

Este projeto está sob a licença MIT. Veja [LICENSE](LICENSE) para mais informações.
```

#### .gitignore
```gitignore
# Dart
.dart_tool/
.packages
build/
pubspec.lock

# Flutter
.flutter-plugins
.flutter-plugins-dependencies

# IDEs
.vscode/
.idea/
*.iml
*.ipr
*.iws

# OS
.DS_Store
Thumbs.db

# Environment
.env
*.env.local

# Build outputs
*.o
*.obj
*.exe
*.dll
*.so
*.dylib

# Test coverage
coverage/
*.lcov

# Logs
*.log
npm-debug.log*
yarn-debug.log*
```

---

## 🔄 Workflow de Desenvolvimento

### 1. Iniciar Nova Semana/Projeto

```bash
# Criar branch para nova semana
git checkout -b semana-1-dia-1-2

# Criar estrutura do projeto
cd modulo-1-dart-fundamentos/semana-1-sintaxe-basica/dia-1-2-ambiente-hello-world
dart create hello_world

# Abrir no VS Code
code .
```

### 2. Desenvolvimento com Claude Code

```bash
# Iniciar sessão com Claude Code
claude-code start

# Durante o desenvolvimento, usar comandos:
# - @claude explique este código
# - @claude como posso melhorar isso?
# - @claude crie testes para esta função
```

### 3. Commit e Push

```bash
# Adicionar mudanças
git add .

# Commit com mensagem descritiva
git commit -m "feat(modulo-1): adiciona projeto hello world e calculadora"

# Push para GitHub
git push origin semana-1-dia-1-2
```

### 4. Documentação

```bash
# Criar README.md para o projeto
# Incluir:
# - Descrição do projeto
# - O que foi aprendido
# - Como executar
# - Capturas de tela (se aplicável)
```

---

## 🎯 Checklist Diário

```markdown
## Checklist de Aprendizado Diário

- [ ] Ler a teoria do dia
- [ ] Assistir/ler recursos complementares
- [ ] Fazer o projeto prático
- [ ] Adicionar comentários explicativos no código
- [ ] Testar o código completamente
- [ ] Fazer commit no GitHub
- [ ] Documentar aprendizado no GitBook
- [ ] Revisar código com Claude Code
```

---

## 📊 GitHub Actions (CI/CD)

### Workflow para Dart (.github/workflows/dart-tests.yml)

```yaml
name: Dart Tests

on:
  push:
    branches: [ main, develop ]
  pull_request:
    branches: [ main, develop ]

jobs:
  test:
    runs-on: ubuntu-latest
    
    steps:
    - uses: actions/checkout@v3
    
    - name: Setup Dart
      uses: dart-lang/setup-dart@v1
      with:
        sdk: stable
    
    - name: Install dependencies
      run: dart pub get
      working-directory: ./modulo-1-dart-fundamentos
    
    - name: Run tests
      run: dart test
      working-directory: ./modulo-1-dart-fundamentos
    
    - name: Analyze code
      run: dart analyze
      working-directory: ./modulo-1-dart-fundamentos
```

### Workflow para Flutter (.github/workflows/flutter-tests.yml)

```yaml
name: Flutter Tests

on:
  push:
    branches: [ main, develop ]
    paths:
      - 'modulo-3-flutter-fundamentos/**'
      - 'modulo-4-mcp/**'
  pull_request:
    branches: [ main, develop ]

jobs:
  test:
    runs-on: ubuntu-latest
    
    steps:
    - uses: actions/checkout@v3
    
    - name: Setup Flutter
      uses: subosito/flutter-action@v2
      with:
        flutter-version: 'stable'
    
    - name: Install dependencies
      run: flutter pub get
      working-directory: ./modulo-3-flutter-fundamentos
    
    - name: Run tests
      run: flutter test
      working-directory: ./modulo-3-flutter-fundamentos
    
    - name: Analyze code
      run: flutter analyze
      working-directory: ./modulo-3-flutter-fundamentos
```

---

## 🎓 Próximos Passos

1. **Criar repositório no GitHub:**
   ```bash
   gh repo create dart-learning-hub --public
   ```

2. **Clonar e inicializar:**
   ```bash
   git clone https://github.com/seu-usuario/dart-learning-hub.git
   cd dart-learning-hub
   ./setup-repo.sh
   ```

3. **Configurar GitBook** (ver documento GitBook Setup)

4. **Começar Módulo 1, Semana 1, Dia 1!**

---

**Ambiente configurado! Hora de codar! 🚀**