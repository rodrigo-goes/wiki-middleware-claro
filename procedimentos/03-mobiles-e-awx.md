# Gestão de Ambientes Mobiles, AWX e Infraestrutura

## 1. Ordem de Reinício de Máquinas Mobiles
As máquinas possuem 4 tipos (`SEC`, `ONL`, `APP`, `WEB`).
- **Para baixar (Shutdown):** Podem ser derrubadas juntas.
- **Para subir (Startup):** Respeite estritamente a sequência, aguardando subir uma por uma:
  1. `sec`
  2. `onl`
  3. `app`
  4. `web`

## 2. Utilização do AWX (Automação Ansible)
- **Link do AWX (Mobiles):** `http://brux1705:8080/#/Home` (Usuário: `clarotest` / Senha: `c1ar0#t3st`)
- **Atenção aos IDs de Ambiente:**
  - Environment ID = `1` reinicia o **Mobile 10**.
  - Environment ID = `2` reinicia o **Mobile 1**.
  - Para o **Mobile 9**, informar ID `9`.
- **Passos no AWX:** Ir em *Resources > Templates > Restart Test Environment*, informar o ID do ambiente e lançar (*Launch*).