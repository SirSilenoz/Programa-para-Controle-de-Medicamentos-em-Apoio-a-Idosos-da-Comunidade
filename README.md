# Cuidar — Controle de Medicamentos para Casas de Apoio a Idosos

Projeto de Extensão Universitária desenvolvido no **Centro Universitário Internacional UNINTER — Escola Superior Politécnica (ESP)**, no âmbito da disciplina *Atividade Extensionista II: Tecnologia Aplicada à Inclusão Digital — Projeto*, do curso **CST em Análise e Desenvolvimento de Sistemas**.

**Autor:** João Pedro do Vale de Almeida — RU 5195747
**ODS:** 03 — Saúde e bem-estar
**Setor de aplicação:** casas de apoio a idosos na cidade de Salvador (BA)

---

## O problema

O cuidado com a medicação de idosos em casas de apoio costuma esbarrar em alguns desafios recorrentes, especialmente em instituições com poucos funcionários e troca de plantão frequente:

- **Falta de rastro entre turnos** — quando um cuidador não sabe, com certeza, se a dose das 8h já foi administrada pelo colega do turno anterior, o risco é tanto esquecer a dose quanto duplicá-la.
- **Esquecimento do horário exato**, em meio à rotina de vários moradores com medicações diferentes.
- **Dificuldade para ler bulas e rótulos**, sobretudo por parte de idosos com baixa visão que tentam administrar o próprio remédio.
- **Confusão ao lidar com múltiplos medicamentos** por morador, cada um com dosagem e horário próprios.

O ponto mais crítico não é só lembrar o horário — é a **falta de um registro visível e confiável**, compartilhado entre quem cuida do mesmo morador em turnos diferentes.

## A solução

Aplicação web de página única, que funciona em celular ou computador e organiza a rotina de medicação da casa de apoio.

### Funcionalidades

- **Painel "Agora"** — mostra, em destaque, os medicamentos que precisam ser dados no momento e os que estão atrasados.
- **Agenda do dia por período** — manhã, tarde e noite, com contagem de quantas doses já foram registradas.
- **Registro de administração com responsável** — ao marcar uma dose como dada, o sistema grava a hora real e o nome de quem administrou, resolvendo a falta de rastro entre turnos.
- **Desfazer registro** — corrige lançamentos feitos por engano.
- **Cadastro de moradores** — nome, quarto e observações de saúde (alergias, restrições).
- **Cadastro de medicamentos** — nome, dosagem, um ou vários horários e orientação de uso.
- **Histórico auditável** — todas as administrações, com horário previsto, horário real, medicamento e responsável, além da contagem de doses fora do horário.

### Acessibilidade

O público-alvo inclui pessoas idosas e cuidadores com pouca familiaridade digital. As decisões de interface partiram disso:

- Tipografia **Atkinson Hyperlegible**, desenvolvida pelo Braille Institute para leitores com baixa visão.
- Botão de **aumento de fonte** em três níveis, sem sair da tela.
- **Modo claro e escuro**, respeitando também a preferência do sistema operacional.
- Alvos de toque com no mínimo 44–52 px de altura.
- Cores de status com contraste alto, sempre acompanhadas de texto ("atrasado", "para agora"), nunca dependendo só da cor.
- Foco de teclado visível e redução de movimento respeitada.
- Vocabulário direto, sem jargão técnico: "Marcar como dado", e não "Registrar ocorrência de administração".

## Tecnologias

| Item | Escolha | Motivo |
|---|---|---|
| Linguagens | HTML5, CSS3, JavaScript (ES5+) | Sem dependências externas |
| Armazenamento | `localStorage` do navegador | Funciona sem internet e sem servidor |
| Hospedagem | GitHub Pages | Gratuita, adequada ao contexto das casas de apoio |
| Arquivo único | `index.html` | Pode ser copiado para um pendrive e aberto direto |

Não há framework, build ou banco de dados externo. A escolha foi deliberada: casas de apoio costumam não ter infraestrutura de TI nem orçamento para servidor, e a conexão de internet pode ser instável.

## Como executar

**Opção 1 — direto no navegador**
Baixe o arquivo `index.html` e abra com um duplo clique.

**Opção 2 — servidor local**
```bash
git clone https://github.com/SEU-USUARIO/cuidar-medicamentos.git
cd cuidar-medicamentos
python3 -m http.server 8000
```
Acesse `http://localhost:8000`.

**Opção 3 — GitHub Pages**
No repositório: *Settings → Pages → Source: Deploy from a branch → main → / (root)*.

Na primeira execução, o botão **"Carregar dados de exemplo"** popula o sistema com três moradores fictícios para demonstração.

## Estrutura

```
cuidar-medicamentos/
├── index.html      # aplicação completa (interface, estilos e lógica)
└── README.md
```

## Privacidade

Os dados ficam armazenados apenas no navegador do próprio aparelho. Nada é enviado para servidores externos e não há coleta de informação. Os nomes usados na demonstração são fictícios.

## Limitações conhecidas

- Os dados ficam salvos apenas no navegador do aparelho usado; não há sincronização automática entre aparelhos diferentes.
- Não há controle de acesso por usuário.
- Não emite notificações quando o aplicativo está fechado (exigiria um app nativo ou service worker com push).

## Aviso

Esta ferramenta organiza horários e registra administrações. **Não substitui prescrição, orientação médica ou farmacêutica.**

## Licença

MIT.
