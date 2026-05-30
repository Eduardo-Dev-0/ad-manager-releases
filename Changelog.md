# Changelog

Todas as mudanças notáveis deste projeto serão documentadas aqui.

O formato segue [Keep a Changelog](https://keepachangelog.com/pt-BR/1.0.0/),
e este projeto adere ao [Versionamento Semântico](https://semver.org/lang/pt-BR/).

---
## [2.1.0] — 2026-05-30

### Corrigido
- CPF com zeros à esquerda sendo cortado ao ler planilha Excel
- Senha inicial sempre exibida com 11 dígitos completos
- Ferramenta travando (Não está respondendo) ao redefinir senha em lote
- Treeview retornando valores numéricos — forçada conversão para string

### Adicionado
- Ícones de status na coluna: 🟠 Carregado · 🟡 Disponível · ✅ Criado · 🔵 Já existe · ❌ Erro
- Spinner animado no rodapé durante operações (⠋ Verificando... · ⠙ Criando...)
- Rodapé com contadores por status: ✅ Criados · 🔵 Já existe · ❌ Erros
- Scrollbar vertical na tabela de usuários
- Fonte maior na tabela (Arial 11) com altura de linha aumentada
- Opções de reset de senha: CPF padrão · Senha padrão com forçar troca · Senha manual
- Opção nas Configurações para forçar troca de senha no próximo login
- Validação de 11 dígitos bloqueando criação de usuário com CPF inválido
- Função formatar_cpf garantindo exibição 000.000.000-00 em toda a interface
- Log detalhado passo a passo durante criação de usuários

### Alterado
- Linhas carregadas da planilha agora exibidas em preto (melhor contraste)
- Amarelo reservado apenas para usuários disponíveis para criar
- Função criar() completamente reescrita com tratamento de erros por etapa

## [2.0.0] — 2026-05-04

### Adicionado
- Configurador de formato de login por blocos (primeiro nome, último nome, CPF, matrícula, separadores)
- Configurador de formato de senha por blocos (CPF, nome, senha fixa customizável)
- Preview em tempo real do login e senha na janela de configurações
- Coluna "Senha Inicial" visível na tabela antes de criar os usuários
- Suporte a coluna "Matrícula" na planilha como bloco opcional de login
- Validação matemática de CPF com dígitos verificadores
- Detecção de logins duplicados dentro da própria planilha antes de ir ao AD
- Redefinição de senha em lote sem precisar recriar a conta
- Movimentação de usuários entre OUs diretamente pela ferramenta
- Barra de progresso visível durante todas as operações em lote
- Rodapé com contador em tempo real (Total / Selecionados / Criados / Erros)
- Log com cores por tipo de mensagem (verde, laranja, vermelho, branco)
- Exportação do log em `.txt` com data e hora no nome do arquivo
- Exportação de relatório pós-operação em `.xlsx` (Nome, Login, Senha, Status)

### Alterado
- Operações em lote agora atuam apenas nos usuários com checkbox marcado
- Refatoração da função `_acao_em_lote` para eliminar duplicação entre desativar/ativar/remover
- Função `criar` agora usa a senha gerada pela configuração em vez do CPF hardcoded
- Paleta de cores atualizada para o azul elétrico `#039BF4` extraído do ícone oficial

---

## [1.1.0] — 2026-03-20

### Adicionado
- Detecção automática do domínio AD via `socket.getfqdn()`
- Janela de seleção de OU com listagem dinâmica e campo de busca
- Checkbox individual por linha na tabela para seleção granular
- Botões de seleção/desmarcação em massa
- Validação de planilha com notificação linha a linha de erros
- Botão para limpar o log de operações
- Suporte a colunas Nome e CPF com detecção automática de cabeçalho

### Alterado
- Domínio e OU deixaram de ser hardcoded no código
- Nome do projeto alterado de "Digital College" para "Tech Solutions"
- Paleta visual migrada de vermelho para azul

---

## [1.0.0] — 2026-03-10

### Adicionado
- Interface gráfica com CustomTkinter (tema escuro)
- Importação de planilha Excel com preview em tabela
- Detecção automática do cabeçalho da planilha
- Geração de login no formato `primeironome + ultimonome + cpf4`
- Verificação de existência de usuários no AD
- Criação de usuários em lote
- Ativação e desativação de usuários
- Remoção de usuários com confirmação
- Log de operações em tempo real
- Suporte a geração de executável via PyInstaller