---
title: Solução de problemas de implantação do Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/5/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: Solucionar problemas de implantação do Cloud Connector Edition.
ms.openlocfilehash: 7a1caea67c5b5899c2dc0909ef771a57c7c50389
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359327"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a>Solução de problemas de implantação do Cloud Connector

> [!Important]
> O Cloud Connector Edition vai retirar 31 de julho de 2021 junto com o Skype for Business online. Depois que sua organização tiver atualizado para o Microsoft Teams, saiba como conectar sua rede de telefonia local ao Microsoft Teams usando o [Roteamento direto](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).
 
Solucionar problemas de implantação do Cloud Connector Edition.
  
Este tópico descreve soluções para problemas comuns com implantações do Cloud Connector Edition. Se você estiver tendo problemas com chamadas de e para a PSTN (rede telefônica pública comutada), você pode investigar seguindo as soluções descritas neste tópico.
  
O Cloud Connector fornece mecanismos internos para resolver automaticamente alguns problemas. Um processo de detecção automática procura possíveis problemas com os dispositivos do Cloud Connector e, se possível, realiza ações corretivas para resolver esses problemas sem a necessidade de intervenção do administrador. O processo de detecção funciona da seguinte maneira:
  
- **Sequência de detecção:** O serviço de gerenciamento do Cloud Connector executa um processo a cada 60 segundos para detectar se um dispositivo está inoperante. No Cloud Connector versão 2,0 e posterior, o processo de detecção usa a opção corpnet do Skype for Business para fazer conexões do PowerShell com as máquinas do Cloud Connector; para versões anteriores a 2,0, o processo de detecção usa a opção de gerenciamento do Cloud Connector.
    
    > [!NOTE]
    > Para que a recuperação automática tenha êxito, deve haver conectividade de rede entre o host e as máquinas virtuais sobre o comutador de rede do host. Certifique-se de verificar a conectividade da rede para garantir que a detecção e a recuperação automáticas possam ser bem-sucedidas. 
  
- **Monitoramento:** Os seguintes serviços são monitorados no Cloud Connector versão 2,0 e posteriores:
    
  - As máquinas virtuais não estão conectadas aos comutadores virtuais corporativos ou de Internet do Cloud Connector
    
  - As máquinas virtuais estão em um status salvo ou parado
    
  - Serviços do servidor de gerenciamento central: réplica, mestre
    
  - Serviços do servidor de mediação: réplica, RTCSRV e MEDSVC
    
  - Serviços do servidor de borda: réplica, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY
    
  - As regras de firewall de entrada estão desabilitadas para o CS RTCSRV no servidor de borda, CS RTCMEDSRV no servidor de mediação
    
    No Cloud Connector versão 1.4.2, apenas os seguintes serviços são monitorados:
    
  - Serviços do servidor de mediação: RTCSRV e MEDSVC
    
  - Serviço do servidor de borda: RTCSRV
    
- **Processo de recuperação:** Se quaisquer serviços monitorados estiverem inativos, um dispositivo é marcado para baixo, e os serviços são interrompidos e marcados manualmente até que todos os problemas possam ser resolvidos. Isso impedirá chamadas de roteamento para um dispositivo que pode causar falhas de chamada.
    
    O serviço de gerenciamento do Cloud Connector repetirá a recuperação automática da seguinte maneira
    
  - O intervalo de repetição inicial é a cada dez segundos com um tempo máximo de intervalo de uma hora.
    
  - Para as três primeiras tentativas de recuperação, o intervalo de tempo é de 10 segundos. A partir da quarta repetição, o tempo do intervalo aumenta em duas vezes o intervalo de tempo anterior. Por exemplo, a quarta tentativa ocorrerá em 20 segundos, o quinto em 40 segundos e assim por diante. 
    
  - Quando o tempo máximo de intervalo de uma hora é atingido, as repetições continuarão uma vez por hora.
    
  - Quando a recuperação é bem-sucedida, as contagens intervalo e repetição são definidas com seus valores iniciais.
    
  - Se o serviço de gerenciamento for reiniciado, as contagens de intervalo e de repetição serão redefinidas para seus valores iniciais.
    
## <a name="troubleshooting"></a>Solução de problemas

Veja a seguir soluções para problemas comumente encontrados:
  
- **Problema: a implantação falha ou para de responder ao executar scripts de implantação. Depois de fazer logon em cada VM, o endereço IP está ausente ou incorreto para a NIC de gerenciamento/interna/externa.**
    
    **Resolução:** Este problema não pode ser resolvido automaticamente. As NICs não podem ser adicionadas às VMs enquanto estiverem em execução. Encerre e remova essas VMs no Gerenciador do Hyper-v e execute os seguintes cmdlets:
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    **Problema: após a instalação do servidor do Active Directory e da floresta, o servidor CMS e/ou o servidor de mediação não ingressaram corretamente no domínio.**
    
    **Resolução:** Para resolver esse problema, siga estas etapas:
    
  - Faça logon no servidor do Active Directory e verifique se o domínio foi criado corretamente.
    
  - Faça logon no CMS/servidor de mediação e verifique se no corpnet NIC um endereço IP válido é atribuído e se o IP estático e o DNS válidos estão configurados como o endereço IP do servidor do AD.
    
  - Faça logon no CMS/servidor de mediação e abra um prompt de comando. Verifique se é possível executar ping no FQDN e no endereço IP do servidor do Active Directory. Se não for possível, pode haver um conflito de endereço IP. Tente atribuir um novo IP para o Active Directory e atualizar o DNS no servidor de CMS/mediação apropriadamente.
    
- **Problema: você recebe a seguinte mensagem de erro, "Remove-VMSwitch: falha ao remover o comutador Ethernet virtual. O ' comutador de gerenciamento do Cloud Connector ' do comutador virtual não pode ser excluído porque está sendo usado pela execução de máquinas virtuais ou atribuído a pools filho.**
    
    **Resolução:** A "opção de gerenciamento do Cloud Connector" não foi excluída após a implantação. Se você acertar este erro, vá para o Gerenciador do Hyper-v e verifique se ainda não há uma máquina virtual conectada a ela. Se houver máquinas virtuais conectadas, desconecte-as e exclua a opção de gerenciamento. Se a opção de gerenciamento ainda não puder ser excluída, reinicie o servidor host e tente novamente.
    
- **Problema: você recebe a seguinte mensagem de erro, "falha do RTCMRAUTH de serviço ao iniciar. Verifique se o serviço não está desabilitado.**
    
    > [!NOTE]
    > Este problema só se aplica às versões do Cloud Connector anteriores à 1.4.2. 
  
    A falha ao iniciar também pode ocorrer porque o servidor front-end foi anteriormente com failover (usando o failover do computador). Se esse for o caso, invoque o failback (usando failback de computador).
    
    **Resolução:** Esse problema ocorre em um servidor de borda quando o certificado de autoridade de certificação raiz ou o certificado de autoridade de certificação intermediário não é confiável para o servidor de borda. Mesmo que o certificado externo possa ser importado, mas a cadeia de certificados seja quebrada. Sob esta condição, o serviço RTCMRAUTH e/ou RTCSRV não pode ser iniciado.
    
    Importe o certificado de autoridade de certificação raiz e todos os certificados de autoridade de certificação intermediários do seu certificado externo manualmente para o servidor de borda e reinicie o servidor de borda. Após ver os serviços RTCMRAUTH e RTCSRV iniciados no servidor de borda, volte ao servidor host, inicie um console do PowerShell como administrador e execute o cmdlet a seguir para mudar para a nova implantação:
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    **Problema: o servidor host foi reiniciado quando as atualizações do Windows foram aplicadas, e as chamadas atendidas pelo servidor estão falhando.**
    
    **Resolução:** Se você implantou um ambiente de alta disponibilidade, a Microsoft fornece um cmdlet para ajudar a mover uma máquina host (instância de implantação) para ou para a topologia atual quando você verifica e instala o Windows Update manualmente. Use as etapas a seguir para fazer isso:
    
1. No servidor host, inicie um console do PowerShell como administrador e execute:
    
   ```powershell
   Enter-CcUpdate
   ```

2. Verifique se há atualizações e instale as que estão disponíveis.
    
3. No console do PowerShell, execute o seguinte cmdlet:
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    **Problema: quando uma chamada é feita de um cliente do Skype for Business usando um número PSTN, a chamada não pode ser escalonada para uma conferência por meio de um convite a outro número PSTN.**
    
    **Resolução:** Para resolver esse problema, confira [definir as configurações do servidor de mediação híbrida online](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).
    
- **Problema: uma mensagem de aviso é exibida sobre o Windows Update quando você está instalando o servidor do Active Directory-"A atualização automática do Windows não está habilitada. Para garantir que sua função ou recurso instalado recentemente seja atualizado automaticamente, ative o Windows Update. "**
    
    **Resolução:** Inicie uma sessão do PowerShell remoto do locatário usando as credenciais de administrador de locatário do Skype for Business e execute o seguinte cmdlet para verificar a configuração do _EnableAutoUpdate_ do seu site:
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    Se  _EnableAutoUpdate_ estiver definido como **true**, você poderá ignorar com segurança essa mensagem de aviso porque o serviço CCEManagement tratará do download e instalando as atualizações do Windows para as máquinas virtuais e o servidor host. Se  _EnableAutoUpdate_ estiver definido como **false**, execute o cmdlet a seguir para defini-lo como **true**.
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    Como alternativa, você pode verificar e instalar as atualizações manualmente. Confira a próxima seção.
    
- **Problema: você recebe uma mensagem de erro: não é possível registrar o dispositivo porque sua entrada/configuração atual \<SiteName\> ou ou \<ApplianceName\> \<Mediation Server FQDN\> \<Mediation Server IP Address\> está em conflito com os dispositivos existentes. Remova o dispositivo de conflito ou atualize as informações de entrada/configuração e registre-se novamente. ' ao executar Register-CcAppliance para registrar o dispositivo atual em modo online.**
    
    **Resolução:** Os valores para \<ApplianceName\> o \<Mediation Server FQDN\> e \<Mediation Server IP Address\> devem ser exclusivos e usados apenas para um registro de dispositivo. Por padrão, \<ApplianceName\> vem do nome do host. \<Mediation Server FQDN\> e \<Mediation Server IP Address\> definido no arquivo ini de configuração.
    
    Por exemplo, usando (Appliancename = MyserverNew, FQDN do servidor de mediação = MS. contoso. com, endereço IP do servidor de mediação = 10.10.10.10) a ser registrado em SiteName = meusite, mas, se houver um dispositivo registrado (Appliance = meuservidor, FQDN do servidor de mediação = MS. contoso. com, endereço IP do servidor de mediação = 10.10.10.10)
    
    Primeiro, verifique o arquivo CloudConnector.ini na seção ApplianceRoot Directory. Você receberá \<SiteName\> \<Mediation Server FQDN\> e os \<Mediation Server IP Address\> valores no arquivo. \<ApplianceName\> é o nome do seu servidor host.
    
    Em segundo lugar, inicie o PowerShell remoto do locatário usando suas credenciais de administrador de locatário do Skype for Business e execute o cmdlet a seguir para verificar os dispositivos registrados.
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    Após identificar os conflitos, você pode atualizar seu arquivo de CloudConnector.ini com informações que correspondam ao dispositivo registrado ou cancelar o registro do dispositivo existente para resolver os conflitos.
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- **Problema: o cmdlet Get-CcRunningVersion retorna um valor vazio se houver um dispositivo implantado em execução no host.**
    
  **Resolução:** Isso pode acontecer quando você atualiza do 1.3.4 ou do 1.3.8 para o 1.4.1. Após a instalação do 1.4.1 de versão com o. msi, você deve executar o `Register-CcAppliance` antes de executar qualquer outro cmdlet. `Register-CcAppliance` migrará o arquivo module.ini do%UserProfile%\CloudConnector para o%ProgramData%\CloudConnector. Se você o tiver perdido, um novo module.ini será criado na pasta%ProgramData%\CloudConnector e substituirá as informações de versão de execução/backup do 1.3.4 ou do 1.3.8.
    
  Compare module.ini arquivos na pasta%UserProfile%\CloudConnector e%ProgramData%\CloudConnector. Se houver diferenças, exclua o arquivo module.ini no%ProgramData%\CloudConnector e execute novamente  `Register-CcAppliance` . Você também pode modificar o arquivo manualmente para a versão correta de execução e backup.
    
- **Problema: depois de executar o cmdlet switch-CcVersion para alternar para uma versão antiga diferente da versão atual do script, não há suporte para alta disponibilidade para esta versão antiga.**
    
    **Resolução:** Por exemplo, você atualizou de 1.4.1 para 1.4.2. Sua versão atual do script, que pode ser determinada executando `Get-CcVersion` o e a versão em execução, que pode ser determinada pela execução  `Get-CcRunningVersion` são ambos 1.4.2. No momento, se você executar `Switch-CcVersion` o para mudar a versão em execução de volta para o 1.4.1, não haverá suporte de alta disponibilidade para essa versão antiga.
    
    Para obter suporte completo à alta disponibilidade, volte para o 1.4.2, de modo que a versão em execução e a versão do script sejam as mesmas. Se você estiver tendo problemas com sua implantação de 1.4.2, desinstale e reinstale-o assim que possível.
    
- **Problema: os certificados da autoridade de certificação ou os certificados internos emitidos para o repositório de gerenciamento central, servidor de mediação e servidor de borda estão prestes a expirar ou estão comprometidos.**
    
    **Resolução:** Os certificados de autoridade de certificação do Skype for Business são válidos por cinco anos. Os certificados internos emitidos para o repositório de gerenciamento central, o servidor de mediação e o servidor de borda são válidos por dois anos.
    
    > [!NOTE]
    > No Cloud Connector versão 2,0 e posterior, o cmdlet Renew-CcServerCertificate mudou para Update-CcServerCertificate e o cmdlet Renew-CcCACertificate mudou para Update-CcCACertificate. 
  
    Se os certificados internos emitidos para o repositório de gerenciamento central, servidor de mediação e servidor de borda estiverem prestes a expirar ou comprometidos, execute o cmdlet Renew-CcServerCertificate ou Update-CcServerCertificate para renovar seus certificados.
    
    Se os certificados da autoridade de certificação estiverem prestes a expirar, execute o cmdlet Renew-CcCACertificate ou Update-CcCACertificate para renovar seus certificados.
    
    **Se os certificados da autoridade de certificação estiverem comprometidos e houver apenas um dispositivo no site,** execute as seguintes etapas:
    
1. Execute o cmdlet Enter-CcUpdate para esvaziar os serviços e colocar o dispositivo no modo de manutenção.
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. Execute os seguintes cmdlets para redefinir e criar novos certificados de autoridade de certificação e todos os certificados de servidor interno:
    
    Para versões do Cloud Connector antes de 2,0:
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    Ou para o Cloud Connector versão 2,0 e posterior:
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. Se o TLS for usado entre o gateway e o servidor de mediação, execute o cmdlet Export-CcRootCertificate do dispositivo e instale o certificado exportado nos seus gateways PSTN. Você também pode ser solicitado a emitir novamente o certificado no seu gateway.

   ```powershell
   Export-CcRootCertificate
   ```

4. Execute o cmdlet Exit-CcUpdate para iniciar os serviços e sair do modo de manutenção.

   ```powershell
   Exit-CcUpdate
   ```


    **Se os certificados da autoridade de certificação estiverem comprometidos e houver vários dispositivos no site,** execute as seguintes etapas sequenciais em cada dispositivo no site.
    
    A Microsoft recomenda que você execute estas etapas durante horários que não sejam de pico.
    
1. No primeiro dispositivo, execute o cmdlet Remove-CcCertificationAuthorityFile para limpar os arquivos de backup da AC no \<SiteRoot\> diretório.

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. Execute o cmdlet Enter-CcUpdate para esvaziar os serviços e colocar cada dispositivo no modo de manutenção.

     ```powershell
     Enter-CcUpdate
     ```
    
3. No primeiro dispositivo, execute os seguintes cmdlets para redefinir e criar novos certificados de autoridade de certificação e todos os certificados de servidor interno:
    
     Para versões do Cloud Connector antes de 2,0:
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     Ou para o Cloud Connector versão 2,0 e posterior:
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. No primeiro dispositivo, execute o cmdlet a seguir para fazer backup dos arquivos da CA na \<SiteRoot\> pasta.
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. Em todos os outros dispositivos do mesmo site, execute os seguintes comandos para consumir os arquivos de backup da CA, para que todos os dispositivos usem o mesmo certificado raiz e, em seguida, solicite novos certificados. 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. Se o TLS for usado entre o gateway e o servidor de mediação, execute o cmdlet Export-CcRootCertificate de qualquer dispositivo no site e, em seguida, instale o certificado exportado para seus gateways PSTN. Você também pode ser solicitado a emitir novamente o certificado no seu gateway.
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. Execute o cmdlet Exit-CcUpdate para iniciar os serviços e sair do modo de manutenção. 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- **Problema: você recebe a seguinte mensagem de erro no log do serviço de gerenciamento do Cloud Connector, "C:\Arquivos de Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService erro: 0: exceção inesperada ao relatar o status para online: System. Management. Automation. CmdletInvocationException: falha de logon para o usuário \<Global Tenant Admin\> . Crie um novo objeto Credential, certificando-se de que você tenha usado o nome de usuário e a senha corretos. ---\>**
    
    **Resolução:** As credenciais de administrador de locatário global do Microsoft 365 ou do Office 365 foram alteradas desde que o dispositivo do Cloud Connector foi registrado. Para atualizar as credenciais armazenadas localmente no dispositivo do Cloud Connector, execute o seguinte no PowerShell do administrador no dispositivo host:
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- **Problema: depois de alterar a senha da conta do servidor host que você usou para a implantação, você recebe a seguinte mensagem de erro: "ConvertTo-SecureString: a chave não é válida para uso no estado especificado." no%ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log ou executando o cmdlet Get-CcCredential.**
    
    **Resolução:** Todas as credenciais do Cloud Connector são armazenadas no seguinte arquivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . XML ". Quando a senha no servidor host for alterada, será necessário atualizar as credenciais armazenadas localmente.
    
    **Se você estiver executando a versão 1.4.2 do Cloud Connector,** regenere todas as senhas do Cloud Connector seguindo estas etapas:
    
  1. Reinicie o servidor host.
    
  2. Exclua o seguinte arquivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . XML ".
    
  3. Inicie um console do PowerShell como administrador e execute "Register-CcAppliance-local" para reinserir as senhas após a descrição. Insira as mesmas senhas que você inseriu anteriormente para a implantação do Cloud Connector.
    
     **Se você estiver executando a versão 2,0 ou posterior do Cloud Connector,** regenere todas as senhas do Cloud Connector seguindo estas etapas:
    
  4. Reinicie o servidor host.
    
  5. Exclua o seguinte arquivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . XML ".
    
  6. Inicie um console do PowerShell como administrador e execute "Register-CcAppliance-local" para reinserir as senhas após a descrição. 
    
     Se o arquivo de senha em cache foi gerado com a versão 1.4.2 do Cloud Connector, use a senha VMAdmin para a senha do CceService quando solicitado. Insira a mesma senha que você inseriu anteriormente para a implantação do Cloud Connector para todas as outras contas.
    
     Se o arquivo de senha em cache foi gerado com a versão 1.4.2 do Cloud Connector e as senhas do DomainAdmin e do VMAdmin forem diferentes, você deverá executar as seguintes etapas:
    
  7. Execute Set-CcCredential-AccountType DomainAdmin da seguinte maneira:
    
  8. Quando for solicitada a credencial antiga da conta, insira a credencial que você usou para a senha do CceService.
    
  9. Quando for solicitada a nova credencial da conta, insira a senha da senha do DomainAdmin usada anteriormente.
    
     Se o arquivo de senha em cache foi gerado com o Cloud Connector versão 2,0 ou posterior, por padrão, VmAdmin e DomainAdmin usam a mesma senha que CceService. Se você alterou as senhas do DomainAdmin e do VMAdmin, deve executar as seguintes etapas:
    
  10. Execute Set-CcCredential-AccountType DomainAdmin da seguinte maneira:
    
       1. Quando for solicitada a credencial antiga da conta, insira a credencial que você usou para a senha do CceService
    
       2. Quando for solicitada a nova credencial da conta, insira a senha da senha do DomainAdmin usada anteriormente.
    
  11. Execute Set-CcCredential-AccountType VmAdmin da seguinte maneira:
    
       1. Quando for solicitada a credencial antiga da conta, insira a credencial que você usou para a senha do CceService
    
       2. Quando for solicitada a nova credencial da conta, insira a senha da senha do VmAdmin usada anteriormente. 
    
- **Problema: com o Cloud Connector versão 2,1 e posterior, ao executar o Register-CcAppliance ou outros cmdlets no dispositivo, você recebe uma mensagem de erro como: "para cada objeto: a propriedade ' Common ' não pode ser encontrada neste objeto. Verifique se a propriedade existe. Em C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 Char: 14 "**
    
    **Resolução:** O Cloud Connector 2,1 e posterior requer o .NET Framework 4.6.1 ou posterior. Atualize o .NET Framework no dispositivo para a versão 4.6.1 ou posterior e execute novamente o (s) cmdlets.

- **Problema: com o Cloud Connector Edition 2,1, ao executar install-CcAppliance, você recebe uma mensagem de erro como: "falha ao instalar nova instância com o erro: não é possível definir" State "porque somente cadeias de caracteres podem ser usadas como valores para definir propriedades XmlNodes"**

   **Resolução:** Em Cloudconnector.ini, na seção [comum], adicione a configuração "estado" da seguinte maneira: CountryCode = Estados Unidos = WA cidade = Redmond

   Não é obrigatório para que a linha "State" tenha valor, mas a linha "State" não pode ser removida do arquivo Cloudconnector.ini.

- **Problema: você recebe a seguinte mensagem de erro "Dismount-WindowsImage: falha de Dismount-WindowsImage. Código de erro = 0xc1550115 "ao instalar ou atualizar o Cloud Connector Edition.**
    
    **Resolução:** Inicie um console do PowerShell como administrador, execute "DISM-Cleanup-wim" ". Isso limpará todas as imagens do problemáticas. Execute install-CcAppliance novamente ou espere que os bits sejam atualizados automaticamente.
    
- **Problema: falha na implantação do primeiro dispositivo do Cloud Connector em um ambiente de alta disponibilidade**
    
    **Resolução:** As etapas que você executar dependem do motivo pelo qual a implantação falhou:
    
  - Se o primeiro dispositivo do Cloud Connector falhar e você não puder determinar o motivo da falha, você deverá instalar o dispositivo novamente até que a implantação seja bem-sucedida e, em seguida, instalar os outros dispositivos.
    
  - Se o primeiro dispositivo do Cloud Connector falhar com um problema secundário, como um problema de certificado externo, você poderá corrigir o problema sem precisar reinstalar o dispositivo. Você pode usar o PowerShell remoto do locatário para marcar a implantação com êxito da seguinte maneira. (Você também pode usar as etapas a seguir se a primeira implantação tiver sido bem-sucedida, mas, por algum motivo, o Cloud Connector não conseguir relatar a implantação como um sucesso.)
    
  - Para obter a identidade (GUID) do primeiro dispositivo do Cloud Connector, execute o cmdlet Get-CsHybridPSTNAppliance.
    
  - Para marcar o dispositivo como implantado com êxito, execute o set-CsCceApplianceDeploymentStatus da seguinte maneira:
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- **Problema: você precisa verificar e instalar as atualizações do Windows manualmente no servidor host ou nas máquinas virtuais.**
    
   **Resolução:** Recomendamos que você aproveite as atualizações automatizadas de so fornecidas pelo Skype for Business Cloud Connector Edition. Depois que um dispositivo é registrado para o gerenciamento online e a atualização de so automática está habilitada, o servidor host e as máquinas virtuais verificam e instalam as atualizações do Windows automaticamente, de acordo com as configurações da janela de tempo de atualização do sistema operacional.
    
   Se você precisar verificar e instalar as atualizações do Windows manualmente, siga as etapas desta seção que se aplicam ao seu tipo de implantação. Você deve planejar a atualização do servidor host e das máquinas virtuais em execução no mesmo momento para minimizar a quantidade de tempo de inatividade necessária para as atualizações.
    
   Se preferir, você pode usar um servidor WSUS (Windows Server Update Services) para fornecer atualizações para os servidores do Cloud Connector. Apenas certifique-se de configurar o Windows Update para **não** instalar automaticamente.
    
   Para obter informações sobre como atualizar manualmente sua implantação do Cloud Connector, consulte a seção a seguir.
    
- **Problema: quando as atualizações do Cloud Connector para um novo Build, os cmdlets do Cloud Connector não são atualizados.** Às vezes, isso ocorre quando uma janela do PowerShell é deixada aberta quando ocorre a atualização automática.
    
  **Resolução:** Para carregar os cmdlets atualizados, você pode executar uma das seguintes etapas:
    
   - Feche o PowerShell no dispositivo do Cloud Connector e reabra o PowerShell.
    
     - Ou, você pode executar Import-Module CloudConnector-Force. 
 
-   **Problema: "o termo" Stop-CsWindowsService "não é reconhecido como o nome de um cmdlet, de função, de um arquivo de script ou de um programa operável." erro ao tentar executar o cmdlet Enter-CcUpdate.**

    **Resolução:** Exclua o arquivo $HOME \AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache.
O PowerShell cria esse arquivo como um cache de cmdlets de módulos que ele encontra, de forma que não seja necessário analisar novamente todos os módulos, sempre que isso tornaria as coisas muito lentas. Provavelmente, houve alguma corrupção de arquivo que forneciam resultados enganosos para o PowerShell quando ele estava lendo novamente desse cache.

-   **Problema: "Import-Module CloudConnector" gera o erro "Import-Module: o módulo especificado" CloudConnector "não foi carregado porque nenhum arquivo de módulo válido foi encontrado em nenhum diretório de módulo"**

    **Resolução:**
    - Validar que o módulo CloudConnector existe em c:\Program Files\WindowsPowerShell\Modules
    
    - Depois de validar que o módulo CloudConnector existe nesse local, a variável de ambiente PSModulePath que armazena o caminho para os locais dos módulos pode ser alterada:
    
     a. Alteração temporária: Inicie o PowerShell como administrador e execute o seguinte comando: $env:P SModulePath = $env:P SModulePath + "; C:\Arquivos de Files\WindowsPowerShell\Modules\"
        
     b. Para uma alteração persistente, inicie o PowerShell como administrador e execute os seguintes comandos, um por um: $CurrentValue = [Environment]:: GetEnvironmentVariable ("PSModulePath", "Machine") SetEnvironmentVariable ("PSModulePath", $CurrentValue + "; C:\Arquivos de Files\WindowsPowerShell\Modules "," Machine ")

    
## <a name="install-windows-updates-manually"></a>Instalar as atualizações do Windows manualmente

Se não quiser usar as atualizações automáticas em seu ambiente, siga estas etapas para verificar e aplicar as atualizações do Windows manualmente. Verificar e instalar as atualizações do Windows pode exigir uma reinicialização do servidor. Quando um servidor host está sendo reiniciado, os usuários não poderão usar o Cloud Connector para fazer ou receber chamadas. Você pode verificar e instalar as atualizações manualmente para controlar quando as atualizações ocorrerem e, em seguida, reiniciar as máquinas conforme necessário durante os horários em que você optar por evitar a interrupção de serviços.
  
Para verificar as atualizações manualmente, conecte-se a cada servidor host e abra o **painel de controle**. Selecione **sistema e segurança \> Windows Update**e gerencie as atualizações e as reinicializações do servidor conforme apropriado para o seu ambiente.
  
- Se houver apenas um dispositivo no site, conecte-se a cada máquina virtual e abra o **painel de controle**. Selecione **sistema e segurança \> Windows Update**e configure as atualizações e as reinicializações do servidor conforme apropriado.
    
- Se houver mais de um dispositivo no site, a instância que está sendo atualizada e reiniciada não poderá ser acessada pelos usuários durante as atualizações. Os usuários se conectarão a outras instâncias na implantação até que todas as máquinas virtuais e todos os serviços do Skype for Business sejam iniciados nas máquinas virtuais depois que as atualizações forem concluídas. Para evitar qualquer interrupção em potencial para o serviço, você pode remover a instância da alta disponibilidade enquanto aplica as atualizações e, em seguida, restaurá-la ao concluir. Para fazer isso:
    
1. Em cada servidor host, abra um console do PowerShell como administrador.
    
2. Remova a instância da alta disponibilidade com o seguinte cmdlet:
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    Siga as etapas para uma única instância para aplicar manualmente as atualizações e reiniciar a máquina virtual.
    
4. Defina a instância de volta para HA com o seguinte cmdlet:
    
   ```powershell
   Exit-CcUpdate
   ```

Para implantações de vários sites, siga as etapas para um único site para cada site na implantação, aplicando atualizações a um site de cada vez.
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a>Dicas ao instalar o software antivírus na máquina host do Cloud Connector

Se for necessário instalar o software antivírus na máquina host do Cloud Connector, você precisará adicionar as seguintes exclusões:
  
- Diretório de dispositivo local em cada máquina.
    
- Diretório de sites remotos em cada máquina.
    
- Diretório de sites locais no computador hospeda a pasta raiz do site compartilhado.
    
- %ProgramFiles%\Skype para o Business Cloud Connector Edition
    
- %ALLUSERSPROFILE%\CloudConnector
    
- %ProgramFiles%\WindowsPowerShell\Modules\CloudConnector
    
- O processo Microsoft.Rtc.CCE.ManagementService.exe.
