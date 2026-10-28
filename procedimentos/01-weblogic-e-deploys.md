# Procedimentos WebLogic & Deploys

## 1. Limpeza de Cache e Reinício de Servidores
Sempre que fizer o `shutdown` ("baixar") de um servidor WebLogic, faça a limpeza de cache antes de subir novamente:
1. O diretório padrão fica em: `/opt/middleware/Weblogic12/Oracle_Home/user_projects/domains/<dominio>`
2. Acesse o diretório do servidor correspondente (ex: `managed_server8002`) e renomeie a pasta (ex: `_old`).
3. Suba o servidor pelo WebLogic. Ele recriará a pasta automaticamente. Após confirmar que subiu, remova a pasta renomeada.
4. **ATENÇÃO:** Nunca dê shutdown na máquina `AdminServer` (`admin`), pois ela gerencia os demais servidores.

## 2. Passo a Passo para Deploy no WebLogic
1. Parar a aplicação no WebLogic.
2. Ir no diretório da aplicação, mover o pacote `.ear`/`.war` atual para backup (ex: `_data_numerodachange`) e copiar o pacote novo.
3. **Limpeza de cache obrigatória** (nunca pular esta etapa para evitar subir arquivos antigos).
4. No console do WebLogic (Opção **Implantações/Deployments**):
   - Remover a aplicação antiga.
   - Clicar em **Instalar**, informar o caminho do pacote novo.
   - Selecionar a opção **Install this deployment as an application**, avançar até o final (*Next, Next, Finish*).
   - Se o status estiver como `PREPARADO`, apenas clique em iniciar. Se estiver como `ADMIN`, vá em *Bloquear, Editar*, selecione a aplicação, clique em *Atualizar* e salve as alterações.

## 3. Tratativa para Máquina Trava no Linux
Execute o comando:
`kill -9 -1`

Em seguida, suba o WebLogic e o NodeManager utilizando nohup e &:
`nohup ./startWeblogic.sh &`
Acompanhe os logs com: `tail -f nohup.out`