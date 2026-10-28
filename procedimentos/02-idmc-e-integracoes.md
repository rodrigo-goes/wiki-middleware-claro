# Tarefas IDMC, Fluxos e Integrações

## 1. Links Úteis do IDMC
- **Console IDMC:** [https://na1.dm-us.informaticacloud.com/cloudshell/showProducts](https://na1.dm-us.informaticacloud.com/cloudshell/showProducts)

## 2. Padrões de Taskflows (Faturadores e Projetos)
- **Opção Data Integration:** Vá em *Explore* para buscar os fluxos.
- **Projeto Pré-Pago / Pós-Pago / IOT:**
  - Envio: `tkf-di-202410-sinc-nfcom-prepago-envio` (para planta 5, adicionar sufixo `-5`).
  - Retorno: `tkf-di-202410-sinc-nfcom-prepago-retorno`.
- **Projeto Arbor:**
  - Envio: `tkf-di-202508-sinc-nfcom-arbor-envio`
  - Retorno: `tkf-di-202508-sinc-nfcom-arbor-retorno` (Sempre confirmar ciclo e base).
- **Projeto SAP / SAP Hana:**
  - Envio/Retorno padrão e versão `-hana` (execução 1 vez por mês, sem parâmetros).
- **Fluxo SFC / Co-Billing (NetSMS):**
  - Executar script de extração prévia no servidor `brux2577` ou `brux2579` (`reuse_sftp_mainframe.sh`).
  - Copiar para `/home/grafana/nfcom_sfc/` no servidor `brux2344`.
  - Executar script de manipulação e disparar taskflow no IDMC: `tkf-di-202501-sinc-nfcom-sfc-envio` e `tkf-di-202501-sinc-nfcom-sfc-retorno`.
- **Combo Multi / Mobile PET (Planta 5):**
  - Taskflows: `tkf-di-202509-sinc-nfcom-combomulti-envio` / `retorno` (usar opção sem `sit7`).