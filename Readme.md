<div align="center">

# Tech Solutions — AD Manager

**Ferramenta gráfica para gerenciamento de usuários no Active Directory via planilha Excel**

![Version](https://img.shields.io/badge/Versão-2.0.0-039BF4?style=for-the-badge)
![Platform](https://img.shields.io/badge/Windows%2010%2B-0078D6?style=for-the-badge&logo=windows&logoColor=white)
![License](https://img.shields.io/badge/Licença-MIT-green?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Estável-brightgreen?style=for-the-badge)

[⬇️ Download](#-download) • [✨ Funcionalidades](#-funcionalidades) • [🚀 Como Usar](#-como-usar) • [📋 Requisitos](#-requisitos) • [🐛 Reportar Bug](#-reportar-problemas)

</div>

---

> **ℹ️ Sobre este repositório**
> Este repositório contém **apenas o instalador e as releases públicas**.
> O código-fonte é mantido em repositório privado.

---

## ⬇️ Download

| Versão | Data | Download |
|--------|------|----------|
| **v2.0.0** ⭐ atual | Mai/2026 | [📦 TechSolutions_ADManager_v2.0.0_Setup.exe](https://github.com/Eduardo-Dev-0/ad-manager-releases/releases/latest) |

> Não é necessário instalar Python. O instalador inclui tudo que é necessário.

---

## 📌 O que é

O **Tech Solutions AD Manager** é uma ferramenta desktop que permite gerenciar usuários do **Active Directory em lote**, importando dados diretamente de uma planilha Excel — sem precisar acessar o ADUC manualmente para cada conta.

---

## ✨ Funcionalidades

**🔌 Conexão com o AD**
Detecção automática do domínio, seleção de OU com busca e movimentação de usuários entre OUs.

**📋 Importação via Planilha Excel**
Suporte a `.xlsx` e `.xls`. Detecta cabeçalho automaticamente. Valida CPF (dígitos verificadores), detecta logins duplicados e notifica erros linha a linha.

**⚙️ Login e Senha Configuráveis**
Monte o formato por blocos: `Primeiro Nome`, `Último Nome`, `CPF (4, 6 ou 11 dígitos)`, `Matrícula`, `Senha Fixa`. Preview em tempo real. Padrão restaurável.

```
Padrão:
  Login → joaosilva1234   (primeiro_nome + ultimo_nome + cpf_4)
  Senha → 12345678900     (cpf_completo)
```

**👥 Operações em Lote**
Checkbox individual por linha + seleção em massa. Operações disponíveis: Verificar, Criar, Ativar, Desativar, Remover, Redefinir Senha e Mover OU — todas atuando apenas nos usuários marcados.

**📊 Relatórios e Auditoria**
Senha inicial visível antes de criar. Exportar relatório `.xlsx`. Log com cores (✔ verde / ⚠ laranja / ✖ vermelho). Exportar log `.txt`. Barra de progresso. Rodapé com contadores em tempo real.

---

## 🖥️ Interface

```
┌─────────────────────────────────────────────────────────────────┐
│  Tech Solutions - Gerenciador AD              ⚙ Configurações   │
├─────────────────────────────────────────────────────────────────┤
│  🔎 Detectar Domínio  │  dominio.local  │  📂 Selecionar OU     │
├─────────────────────────────────────────────────────────────────┤
│  📂 Selecionar Planilha   arquivo.xlsx           📊 Exportar    │
├─────────────────────────────────────────────────────────────────┤
│  ☑ Selecionar Todos    ☐ Desselecionar Todos                    │
├──────┬──────────────┬─────────────┬─────────────┬──────┬───────┤
│  ☑   │ Nome         │ CPF         │ Login       │ Senha│Status │
├──────┼──────────────┼─────────────┼─────────────┼──────┼───────┤
│  ☑   │ João Silva   │ 123.456.789 │ joaosilva12 │ ...  │  ✔    │
│  ☐   │ Maria Souza  │ 987.654.321 │ mariasouza98│ ...  │  ✔    │
├─────────────────────────────────────────────────────────────────┤
│ Verificar │ Criar │ Desativar │ Ativar │ Remover │ 🔑 │ 📁 OU  │
├─────────────────────────────────────────────────────────────────┤
│ ████████████████░░░░  18 / 25                                    │
├─────────────────────────────────────────────────────────────────┤
│ 📋 Log de Operações              💾 Exportar Log   🗑 Limpar    │
│ ✔ Usuário criado: joaosilva1234                                  │
├─────────────────────────────────────────────────────────────────┤
│ Total: 25  │  Selecionados: 18  │  Criados: 17  │  Erros: 1     │
└─────────────────────────────────────────────────────────────────┘
```

---

## 📋 Requisitos

| Item | Detalhe |
|------|---------|
| Sistema Operacional | Windows 10 ou superior |
| Rede | Conectado ao domínio Active Directory |
| Permissões | Criar, ativar, desativar e remover usuários no AD |
| Espaço em disco | ~80 MB |

---

## 🚀 Como Usar

**1.** Baixe e execute o instalador `TechSolutions_ADManager_vX.X.X_Setup.exe`

**2.** Siga o assistente — escolha se quer atalho na área de trabalho

**3.** Abra o **Tech Solutions AD Manager**

**4.** Clique em **🔎 Detectar Domínio**

**5.** Clique em **📂 Selecionar OU** e escolha onde criar os usuários

**6.** Clique em **Selecionar Planilha** e importe seu arquivo Excel

**7.** Marque os usuários com **☑** e clique em **Verificar → Criar**

### Estrutura da Planilha

| Nome        | CPF             | Matrícula |
|-------------|-----------------|-----------|
| João Silva  | 123.456.789-00  | 2024001   |
| Maria Souza | 987.654.321-00  | 2024002   |

- Nome precisa ter ao menos **primeiro e último nome**
- CPF com **11 dígitos válidos** (com ou sem formatação)
- Coluna **Matrícula** é opcional

---

## 🔄 Atualizações

Fique de olho na aba [Releases](https://github.com/Eduardo-Dev-0/ad-manager-releases/releases) para novas versões.
Veja o histórico completo em [CHANGELOG.md](CHANGELOG.md).

---

## 🐛 Reportar Problemas

Abra uma **Issue** neste repositório informando:

- Versão do Windows
- Versão do Windows Server / domínio AD
- Passos para reproduzir o problema
- Print ou mensagem de erro do log

---

## 📄 Licença

MIT License — veja [LICENSE](LICENSE).

---

<div align="center">

Desenvolvido por **Eduardo Gabriel de Meneses — Tech Solutions**

Feito com Dedicação e Python

</div>