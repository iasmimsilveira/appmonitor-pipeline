# AppMonitor Pipeline

Este repositório simula uma estrutura de pipelines DevOps para monitoração de aplicações web, com foco em boas práticas de integração contínua, segurança e monitoramento automatizado.

---

## Git na Entrega Contínua

O Git é fundamental para versionamento e organização no desenvolvimento contínuo.

- **Branches** permitem separar o desenvolvimento de funcionalidades (ex: `ci/setup`).
- **Tags** são usadas para marcar versões estáveis e liberar releases.
- **Release atual:** `v0.1.0`

---

## Variáveis e Contextos no GitHub Actions

- `env`: Variável local definida no workflow ou job. Exemplo:
  ```yaml
  env:
    APP_ENV: dev
  ```

- `vars`: Variáveis globais definidas nas configurações do repositório.
  Acessadas com `${{ vars.NOME }}`. Exemplo: `SUPPORT_EMAIL`.

- `secrets`: Variáveis sensíveis e criptografadas, acessadas com `${{ secrets.NOME }}`.
  Exemplo: `API_KEY`.

---

## Status do Pipeline

![CI Pipeline](https://github.com/iasmimsilveira/appmonitor-pipeline/actions/workflows/ci.yml/badge.svg)

---

## Logs, Mensagens e Resumos Automatizados

O pipeline está configurado para oferecer diagnósticos eficientes por meio de:

- **Logs de depuração** ativados com `ACTIONS_STEP_DEBUG=true`
- **Mensagens personalizadas** para erro e aviso:
    - `::error::` para erros simulados
    - `::warning::` para alertas importantes
- **Resumo automatizado** (`GITHUB_STEP_SUMMARY`) com:
    - Sistema operacional utilizado (`runner.os`)
    - Branch executada (`github.ref_name`)
    - Link para o artefato gerado

Esses recursos melhoram a **observabilidade**, facilitam a resolução de falhas e garantem transparência no processo de integração contínua.

---