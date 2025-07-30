# Delphi Snippets for VS Code

Uma coleção abrangente de snippets para desenvolvimento em Delphi/Pascal no Visual Studio Code. 
Este pacote de snippets foi criado para acelerar o desenvolvimento e fornecer templates úteis para as principais estruturas e padrões de código em Delphi.

Conheça mais sobre este e outros projetos em [Delphi Clean Code](https://youtube.com/delphicleancode).

## 📋 Índice

- [Instalação](#-instalação)
- [Como Usar](#-como-usar)
- [Snippets Disponíveis](#-snippets-disponíveis)
  - [Estruturas Básicas](#estruturas-básicas)
  - [Tipos de Dados](#tipos-de-dados)s
  - [Estruturas de Código](#estruturas-de-código)
  - [Controle de Fluxo](#controle-de-fluxo)
  - [Tratamento de Exceções](#tratamento-de-exceções)
  - [Recursos Avançados](#recursos-avançados)
  - [Acesso a Dados e APIs](#acesso-a-dados-e-apis)
- [Contribuindo](#-contribuindo)
- [Licença](#-licença)

## 🚀 Instalação

### Método 1: Instalação Manual

1. Copie o arquivo `delphi.snippets` para o diretório de snippets do VS Code:
   - **Windows**: `%APPDATA%\Code\User\snippets\`
   - **macOS**: `~/Library/Application Support/Code/User/snippets/`
   - **Linux**: `~/.config/Code/User/snippets/`

2. Reinicie o VS Code ou recarregue a janela (`Ctrl+Shift+P` → "Developer: Reload Window")

### Método 2: Via Command Palette

1. Abra o VS Code
2. Pressione `Ctrl+Shift+P` (Windows/Linux) ou `Cmd+Shift+P` (macOS)
3. Digite "Preferences: Configure User Snippets"
4. Selecione "pascal" ou "delphi"
5. Cole o conteúdo do arquivo `delphi.snippets`

## 📖 Como Usar

1. Abra um arquivo `.pas` no VS Code
2. Digite o prefixo do snippet desejado (ex: `delphiclass`)
3. Pressione `Tab` para expandir o snippet
4. Use `Tab` para navegar entre os placeholders e personalize o código
5. Pressione `Esc` quando terminar de editar

## 📚 Snippets Disponíveis

### Estruturas Básicas

| Prefixo | Descrição |
|---------|-----------|
| `delphibase` | Programa básico Delphi |
| `delphiunit` | Unit básica |
| `delphiform` | Formulário VCL |
| `delphidatamodule` | DataModule |

### Tipos de Dados

| Prefixo | Descrição |
|---------|-----------|
| `delphiclass` | Classe completa com properties |
| `delphiinterface` | Interface |
| `delphirecord` | Record moderno |
| `delphienum` | Enumeração |
| `delphiset` | Conjunto (set) |
| `delphiarray` | Array estático |
| `delphidynarray` | Array dinâmico |

### Estruturas de Código

| Prefixo | Descrição |
|---------|-----------|
| `delphiproc` | Procedure |
| `delphifunc` | Function |
| `delphiconstructor` | Constructor |
| `delphidestructor` | Destructor |
| `delphiprop` | Property com get/set |
| `delphipropro` | Property somente leitura |
| `delphievent` | Event handler |

### Controle de Fluxo

| Prefixo | Descrição |
|---------|-----------|
| `delphiif` | If-then-else |
| `delphicase` | Case statement |
| `delphifor` | For loop |
| `delphiforin` | For-in loop |
| `delphiwhile` | While loop |
| `delphirepeat` | Repeat-until loop |

### Tratamento de Exceções

| Prefixo | Descrição |
|---------|-----------|
| `delphitryexcept` | Try-except |
| `delphitryfinally` | Try-finally |
| `delphiexception` | Exceção customizada |

### Recursos Avançados

| Prefixo | Descrição |
|---------|-----------|
| `delphigeneric` | Classe genérica |
| `delphisingleton` | Padrão Singleton |
| `delphithread` | Thread |

### Acesso a Dados e APIs

| Prefixo | Descrição |
|---------|-----------|
| `delphiquery` | Consulta FireDAC |
| `delphirest` | Cliente REST |
| `delphijson` | Parsing JSON |
| `delphifile` | Operações com arquivos |

## 💡 Exemplos de Uso

### Criando uma Classe

Digite `delphiclass` e pressione Tab:

```pascal
type
  TMinhaClasse = class(TObject)
  private
    FField: Tipo;
    procedure SetField(const Value: Tipo);
  public
    constructor Create;
    destructor Destroy; override;
    property Field: Tipo read FField write SetField;
    // outros métodos
  end;
```

### Implementando um Try-Except

Digite `delphitryexcept` e pressione Tab:

```pascal
try
  // código que pode gerar exceção
except
  on E: Exception do
  begin
    // tratamento da exceção
  end;
end;
```

### Criando uma Consulta de Banco

Digite `delphiquery` e pressione Tab:

```pascal
var
  Query: TFDQuery;
begin
  Query := TFDQuery.Create(nil);
  try
    Query.Connection := Connection;
    Query.SQL.Text := 'SELECT * FROM tabela';
    Query.Open;
    // processar dados
  finally
    Query.Free;
  end;
end;
```

## 🎯 Recursos dos Snippets

- **Placeholders numerados**: Navegação fácil com Tab
- **Valores padrão inteligentes**: Nomes de variáveis e tipos sugeridos
- **Estruturas completas**: Código que segue boas práticas
- **Comentários em português**: Facilita o entendimento
- **Compatibilidade**: Funciona com Delphi moderno (10.x+)

## 🔧 Configuração Adicional

### Habilitando Sugestões de Snippets

Adicione ao seu `settings.json` do VS Code:

```json
{
  "editor.snippetSuggestions": "top",
  "editor.suggest.snippetsPreventQuickSuggestions": false,
  "[pascal]": {
    "editor.quickSuggestions": {
      "other": true,
      "comments": false,
      "strings": false
    }
  }
}
```

### Extensões Recomendadas

- **OmniPascal**: Suporte completo para Pascal/Delphi
- **Pascal**: Syntax highlighting para Pascal
- **Delphi LSP**: Language Server Protocol para Delphi

## 🤝 Contribuindo

Contribuições são bem-vindas! Para adicionar novos snippets ou melhorar os existentes:

1. Faça um fork do projeto
2. Crie uma branch para sua feature (`git checkout -b feature/novo-snippet`)
3. Adicione seus snippets seguindo o padrão existente
4. Teste os snippets no VS Code
5. Commit suas mudanças (`git commit -am 'Adiciona snippet para...'`)
6. Push para a branch (`git push origin feature/novo-snippet`)
7. Abra um Pull Request

### Padrões para Novos Snippets

- **Prefixo**: Sempre comece com `delphi` seguido de uma palavra descritiva
- **Descrição**: Clara e em português
- **Placeholders**: Use numeração sequencial (`${1}`, `${2}`, etc.)
- **Comentários**: Inclua comentários explicativos quando apropriado
- **Boas práticas**: Siga as convenções padrão do Delphi

## 📄 Licença

Este projeto está licenciado sob a MIT License - veja o arquivo [LICENSE](LICENSE) para detalhes.

## 🙏 Agradecimentos

- Comunidade @DelphiCleanCode
- Inovefast Tecnologia www.inovefast.com.br

## 📞 Suporte

Se você encontrar problemas ou tiver sugestões:

1. Abra uma [issue](https://github.com/delphicleancode/delphi-vscode-snippet/issues)
2. Descreva o problema ou sugestão detalhadamente
3. Inclua exemplos quando possível

---

**Desenvolvido com ❤️ para a comunidade Delphi**

> 💡 **Dica**: Para uma experiência ainda melhor, configure o VS Code com as extensões recomendadas e personalize os atalhos de teclado conforme sua preferência.
