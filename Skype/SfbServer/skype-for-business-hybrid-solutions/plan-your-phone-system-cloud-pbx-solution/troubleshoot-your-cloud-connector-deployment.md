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
> O Cloud Connector Edition será destivado em 31 de julho de 2021 junto com o Skype for Business Online. Depois que sua organização tiver atualizado para o Teams, saiba como conectar sua rede de telefonia local ao Teams usando o [Roteamento Direto.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)
 
Solucionar problemas de implantação do Cloud Connector Edition.
  
Este tópico descreve soluções para problemas comuns com implantações do Cloud Connector Edition. Se você estiver tendo problemas com chamadas de e para a PSTN (Rede Telefônica Pública Comucionada), poderá investigar seguindo as soluções descritas neste tópico.
  
O Cloud Connector fornece mecanismos integrados para resolver automaticamente alguns problemas. Um processo de detecção automática procura possíveis problemas com os dispositivos do Cloud Connector e, se possível, toma medidas corretivas para resolver esses problemas sem a necessidade de intervenção do administrador. O processo de detecção funciona da seguinte forma:
  
- **Sequência de detecção:** O serviço gerenciamento do Cloud Connector executa um processo a cada 60 segundos para detectar se um dispositivo está ino mesmo. No Cloud Connector versão 2.0 e posterior, o processo de detecção usa a opção Corpnet do Skype for Business para fazer conexões do PowerShell com os máquinas do Cloud Connector; para versões anteriores à 2.0, o processo de detecção usa a opção de gerenciamento do Cloud Connector.
    
    > [!NOTE]
    > Para que a recuperação automática seja bem-sucedida, deve haver conectividade de rede entre o host e as máquinas virtuais por meio da opção de rede host. Certifique-se de verificar a conectividade de rede para garantir que a detecção e a recuperação automática possam ser bem-sucedidas. 
  
- **Monitoramento:** Os seguintes serviços são monitorados no Cloud Connector versão 2.0 e posterior:
    
  - As máquinas virtuais não estão conectadas aos comutadores virtuais corporativos ou da Internet do Cloud Connector
    
  - As Máquinas Virtuais estão em um status salvo ou interrompido
    
  - Serviços do Servidor de Gerenciamento Central: REPLICA, MASTER
    
  - Serviços do Servidor de Mediação: REPLICA, RTCSRV e MEDSVC
    
  - Serviços do Servidor de Borda: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY
    
  - As regras de firewall de entrada estão desabilitadas para CS RTCSRV no servidor de Borda, CS RTCMEDSRV no servidor de Mediação
    
    No Cloud Connector versão 1.4.2, apenas os seguintes serviços são monitorados:
    
  - Serviços do Servidor de Mediação: RTCSRV e MEDSVC
    
  - Serviço de Servidor de Borda: RTCSRV
    
- **Processo de recuperação:** Se algum serviço monitorado estiver ino mesmo, um dispositivo será marcado para baixo e os serviços serão interrompidos e marcados manualmente até que todos os problemas possam ser resolvidos. Isso impedirá que chamadas roteiem para um dispositivo que possa causar falhas de chamada.
    
    O serviço de Gerenciamento do Cloud Connector repetirá a recuperação automática da seguinte forma:
    
  - O intervalo de nova tentativa inicial é a cada dez segundos com um intervalo máximo de uma hora.
    
  - Nas três primeiras tentativas de recuperação, o tempo de intervalo é de 10 segundos. A partir da quarta tentativa, o tempo de intervalo aumenta em duas vezes o tempo de intervalo anterior. Por exemplo, a quarta tentativa ocorrerá em 20 segundos, a quinta em 40 segundos e assim por diante. 
    
  - Quando o tempo máximo de intervalo de uma hora for atingido, as novamente continuarão uma vez por hora.
    
  - Quando a recuperação for bem-sucedida, o intervalo e as contagens de repetir serão definidos com seus valores iniciais.
    
  - Se o serviço de Gerenciamento for reiniciado, as contagens de intervalo e de nova tentativa serão redefinidas para seus valores iniciais.
    
## <a name="troubleshooting"></a>Solução de problemas

A seguir estão soluções para problemas comuns encontrados:
  
- **Problema: a implantação falha ou para de responder ao executar os scripts de implantação. Depois de fazer logon em cada VM, o endereço IP está ausente ou incorreto para a NIC Gerenciamento/Interna/Externa.**
    
    **Resolução:** Esse problema não pode ser resolvido automaticamente. NiCs não podem ser adicionadas às VMs enquanto estão em execução. Desligue e remova essas VMs no gerenciador do Hyper-V e execute os seguintes cmdlets:
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    **Problema: depois que o Servidor do Active Directory e a floresta são instalados, o Servidor CMS e/ou Servidor de Mediação não ingressaram corretamente no domínio.**
    
    **Resolução:** Para resolver esse problema, tome as seguintes etapas:
    
  - Faça logoff no Servidor do Active Directory e verifique se o domínio foi criado corretamente.
    
  - Faça logon no Servidor CMS/Servidor de Mediação e verifique se um endereço IP válido foi atribuído na NIC da corpnet e se o DNS e o IP estático válidos estão configurados como endereço IP do servidor do AD.
    
  - Faça logon no SERVIDOR CMS/Servidor de Mediação e abra um prompt de comando. Certifique-se de poder fazer ping no FQDN e no endereço IP do Servidor do Active Directory. Se não for possível, pode haver um conflito de endereço IP. Tente atribuir um novo IP para o Active Directory e atualize o DNS no servidor CMS/Mediação de acordo.
    
- **Problema: você recebe a seguinte mensagem de erro, "Remove-VMSwitch: Falha ao remover o comutório Ethernet virtual. O comutado virtual "Comutada de Gerenciamento do Cloud Connector" não pode ser excluído porque está sendo usado por máquinas virtuais em execução ou atribuído a pools filho."**
    
    **Resolução:** O "Comutado de Gerenciamento do Cloud Connector" não foi excluído após a implantação. Se você tiver esse erro, vá para o Gerenciador do Hyper-v e verifique se ainda não há uma máquina virtual conectada a ela. Se ainda houver máquinas virtuais conectadas, desconecte-as e exclua a opção de gerenciamento. Se a opção de gerenciamento ainda não puder ser excluída, reinicie o servidor host e tente novamente.
    
- **Problema: Você recebe a seguinte mensagem de erro: "Falha ao iniciar o serviço RTCMRAUTH. Verifique se o serviço não está desabilitado."**
    
    > [!NOTE]
    > Esse problema só se aplica às versões do Cloud Connector anteriores à 1.4.2. 
  
    A falha ao iniciar também pode ser porque esse servidor front-end foi anteriormente fail over (usando o fail over do computador). Se esse for o caso, invoque o fail back (usando o fail back do computador).
    
    **Resolução:** Esse problema acontece em um Servidor de Borda quando o certificado de AC raiz ou o certificado de AC intermediário não é confiável para o Servidor de Borda. Mesmo se o certificado externo puder ser importado, mas a cadeia de certificados estiver quebrada. Sob essa condição, o serviço RTCMRAUTH e/ou RTCSRV não pode iniciar.
    
    Importe manualmente o certificado de AC raiz e todos os certificados ca intermediários do seu certificado externo para o Servidor de Borda e reinicie o Servidor de Borda. Depois que você vir os serviços RTCMRAUTH e RTCSRV iniciados no Servidor de Borda, volte para o servidor host, iniciar um console do PowerShell como administrador e execute o seguinte cmdlet para alternar para a nova implantação:
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    **Problema: o servidor host foi reiniciado quando as atualizações do Windows foram aplicadas e as chamadas a serviço pelo servidor estão falhando.**
    
    **Resolução:** Se você implantou um ambiente de alta disponibilidade, a Microsoft fornece um cmdlet para ajudar a mover uma máquina host (instância de implantação) para dentro ou para fora da topologia atual ao verificar e instalar a atualização do Windows manualmente. Use as etapas a seguir para fazer isso:
    
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
    
    **Problema: quando uma chamada é feita de um cliente Skype for Business usando um número PSTN, a chamada não pode ser escalonada para uma conferência convidando outro número PSTN.**
    
    **Resolução:** Para resolver esse problema, consulte Configurar definições do Servidor de [Mediação híbrido online.](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer)
    
- **Problema: uma mensagem de aviso é exibida sobre o Windows Update quando você está instalando o servidor do Active Directory - "A atualização automática do Windows não está habilitada. Para garantir que sua função ou recurso recém-instalado seja atualizado automaticamente, a ligue o Windows Update."**
    
    **Resolução:** Iniciar uma sessão do PowerShell Remoto do Locatário usando as credenciais de administrador de locatários do Skype for Business e, em seguida, execute o seguinte cmdlet para verificar a configuração _enableAutoUpdate_ do seu site:
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    Se  _EnableAutoUpdate_ for definido como **True,** você poderá ignorar com segurança essa mensagem de aviso porque o serviço CCEManagement tratará do download e da instalação de atualizações do Windows para máquinas virtuais e o servidor host. Se  _EnableAutoUpdate_ for definido como **False**, execute o seguinte cmdlet para defini-lo como **True**.
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    Como alternativa, você pode verificar e instalar atualizações manualmente. Confira a próxima seção.
    
- **Problema: você recebe uma mensagem de erro: não é possível registrar o dispositivo porque sua entrada/configuração atual ou está em conflito com os \<SiteName\> \<ApplianceName\> \<Mediation Server FQDN\> \<Mediation Server IP Address\> dispositivos existentes. Remova o dispositivo de conflito ou atualize suas informações de entrada/configuração e registre-se novamente. ' when run Register-CcAppliance to register current appliance to online.**
    
    **Resolução:** Valores para \<ApplianceName\> o , e devem ser \<Mediation Server FQDN\> \<Mediation Server IP Address\> exclusivos e usados somente para um registro de dispositivo. Por padrão, \<ApplianceName\> vem do nome do host. \<Mediation Server FQDN\> e \<Mediation Server IP Address\> definido no arquivo ini de configuração.
    
    Por exemplo, usando (ApplianceName= MyserverNew, FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) para registrar-se em SiteName=MySite, mas se houver um dispositivo registrado (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), você terá o conflito.
    
    Primeiro, verifique seu arquivo CloudConnector.ini na seção de diretório ApplianceRoot. Você obterá \<SiteName\> e os valores no \<Mediation Server FQDN\> \<Mediation Server IP Address\> arquivo. \<ApplianceName\> é o nome do servidor host.
    
    Em segundo lugar, iniciar o PowerShell Remoto do Locatário usando suas credenciais de administrador de locatários do Skype for Business e, em seguida, execute o cmdlet a seguir para verificar os dispositivos registrados.
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    Depois de identificar quaisquer conflitos, você pode atualizar o arquivo CloudConnector.ini com informações que corresponde ao dispositivo registrado ou ressuitir o dispositivo existente para resolver os conflitos.
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- **Problema: o Get-CcRunningVersion cmdlet retornará um valor vazio se houver um dispositivo implantado em execução no host.**
    
  **Resolução:** Isso pode acontecer quando você atualiza de 1.3.4 ou 1.3.8 para 1.4.1. Depois de instalar a versão 1.4.1 com o .msi, você deve executar antes de `Register-CcAppliance` executar qualquer outro cmdlet. `Register-CcAppliance` migrará o arquivo module.ini de %UserProfile%\CloudConnector para %ProgramData%\CloudConnector. Se você não o tiver, um novo module.ini será criado na pasta %ProgramData%\CloudConnector e substituirá as informações de versão em execução/backup para 1.3.4 ou 1.3.8.
    
  Compare module.ini arquivos na pasta %UserProfile%\CloudConnector e %ProgramData%\CloudConnector. Se houver diferenças, exclua o arquivo module.ini %ProgramData%\CloudConnector e rerun  `Register-CcAppliance` . Você também pode modificar o arquivo manualmente para a versão correta em execução e de backup.
    
- **Problema: depois de executar o cmdlet Switch-CcVersion para alternar para uma versão antiga diferente da versão atual do script, não há suporte para Alta Disponibilidade para essa versão antiga.**
    
    **Resolução:** Por exemplo, você atualizou de 1.4.1 para 1.4.2. Sua versão de script atual, que pode ser determinada pela execução, e sua versão em execução, que pode ser determinada pela execução são `Get-CcVersion`  `Get-CcRunningVersion` 1.4.2. Neste momento, se você executar para alternar a versão em execução de volta para 1.4.1, não haverá suporte para Alta Disponibilidade para `Switch-CcVersion` esta versão antiga.
    
    Para obter suporte completo para Alta Disponibilidade, volte para a 1.4.2, para que a versão em execução e a versão do script sejam as mesmas. Se você estiver tendo problemas com sua implantação 1.4.2, desinstale e reinstale-a assim que possível.
    
- **Problema: os certificados de autoridade de certificação ou os certificados internos emitidos para o Armazenamento de Gerenciamento Central, o Servidor de Mediação e o Servidor de Borda estão próximos de expirar ou estão comprometidos.**
    
    **Resolução:** Os certificados da autoridade de certificação do Skype for Business são válidos por cinco anos. Os certificados internos emitidos para o Armazenamento de Gerenciamento Central, o Servidor de Mediação e o Servidor de Borda são válidos por dois anos.
    
    > [!NOTE]
    > Na versão 2.0 e posteriores do Cloud Connector, o cmdlet Renew-CcServerCertificate foi alterado para Update-CcServerCertificate e o cmdlet Renew-CcCACertificate foi alterado para Update-CcCACertificate. 
  
    Se os certificados internos emitidos para o Armazenamento de Gerenciamento Central, o Servidor de Mediação e o Servidor de Borda estão próximos de expirar ou estão comprometidos, execute o cmdlet Renew-CcServerCertificate ou Update-CcServerCertificate para renovar seus certificados.
    
    Se os certificados da autoridade de certificação estão próximos de expirar, execute o cmdlet Renew-CcCACertificate ou Update-CcCACertificate para renovar seus certificados.
    
    **Se os certificados da autoridade de certificação estão comprometidos** e há apenas um dispositivo no site, execute as seguintes etapas:
    
1. Execute o Enter-CcUpdate cmdlet para esvaziar os serviços e colocar o dispositivo no modo de manutenção.
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. Execute os seguintes cmdlets para redefinir e criar novos certificados de autoridade de certificação e todos os certificados de servidor internos:
    
    Para versões do Cloud Connector antes da 2.0:
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    Ou para a versão 2.0 e posterior do Cloud Connector:
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. Se o TLS for usado entre o gateway e o Servidor de Mediação, execute o cmdlet Export-CcRootCertificate do dispositivo e instale o certificado exportado para seus gateways PSTN. Talvez também seja necessário emitir o certificado em seu gateway outra vez.

   ```powershell
   Export-CcRootCertificate
   ```

4. Execute o cmdlet Exit-CcUpdate para iniciar os serviços e sair do modo de manutenção.

   ```powershell
   Exit-CcUpdate
   ```


    **Se os certificados de autoridade** de certificação estão comprometidos e há vários dispositivos no site, execute as seguintes etapas sequenciais em cada dispositivo no site.
    
    A Microsoft recomenda que você execute essas etapas durante períodos de uso fora do pico.
    
1. No primeiro dispositivo, execute o Remove-CcCertificationAuthorityFile para limpar os arquivos de backup da AC no \<SiteRoot\> diretório.

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. Execute o Enter-CcUpdate cmdlet para esvaziar os serviços e colocar cada dispositivo no modo de manutenção.

     ```powershell
     Enter-CcUpdate
     ```
    
3. No primeiro dispositivo, execute os seguintes cmdlets para redefinir e criar novos certificados de autoridade de certificação e todos os certificados de servidor internos:
    
     Para versões do Cloud Connector antes da 2.0:
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     Ou para a versão 2.0 e posterior do Cloud Connector:
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. No primeiro dispositivo, execute o cmdlet a seguir para fazer o back up dos arquivos de AC na \<SiteRoot\> pasta.
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. Em todos os outros dispositivos no mesmo site, execute os seguintes comandos para consumir os arquivos de backup da AC, para que todos os dispositivos usem o mesmo certificado raiz e, em seguida, solicite novos certificados. 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. Se o TLS for usado entre o gateway e o Servidor de Mediação, execute o cmdlet Export-CcRootCertificate de qualquer dispositivo no site e instale o certificado exportado para seus gateways PSTN. Talvez também seja necessário emitir o certificado em seu gateway outra vez.
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. Execute o cmdlet Exit-CcUpdate para iniciar os serviços e sair do modo de manutenção. 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- **Problema: Você recebe a seguinte mensagem de erro no Log de Serviço de Gerenciamento do Cloud Connector, "C:\Arquivos de Programas\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": Erro do CceService: 0 : Exceção inesperada ao relatar o status para online: System.Management.Automation.CmdletInvocationException: Falha de logon para o usuário \<Global Tenant Admin\> . Crie um novo objeto de credencial, certifique-se de ter usado o nome de usuário e a senha corretos. ---\>**
    
    **Resolução:** As credenciais de administrador de locatário global do Microsoft 365 ou Office 365 foram alteradas desde que o dispositivo do Cloud Connector foi registrado. Para atualizar as credenciais armazenadas localmente no dispositivo do Cloud Connector, execute o seguinte a partir do Administrador do PowerShell no dispositivo host:
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- **Problema: depois de alterar a senha da conta do servidor host usada para a implantação, você recebe a seguinte mensagem de erro: "ConvertTo-SecureString : Chave não válida para uso no estado especificado." em %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log ou durante a execução do cmdlet Get-CcCredential.**
    
    **Resolução:** Todas as credenciais do Cloud Connector são armazenadas no seguinte arquivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . xml". Quando a senha no servidor host for mudada, você precisará atualizar as credenciais armazenadas localmente.
    
    **Se você estiver executando a versão 1.4.2** do Cloud Connector, regenere todas as senhas do Cloud Connector seguindo estas etapas:
    
  1. Reinicie o servidor host.
    
  2. Exclua o seguinte arquivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . xml".
    
  3. Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description. Insira as mesmas senhas inseridas anteriormente para a implantação do Cloud Connector.
    
     **Se você estiver executando a versão 2.0 ou posterior** do Cloud Connector, regenere todas as senhas do Cloud Connector seguindo estas etapas:
    
  4. Reinicie o servidor host.
    
  5. Exclua o seguinte arquivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . xml" .
    
  6. Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description. 
    
     Se o arquivo de senha em cache foi gerado com a versão 1.4.2 do Cloud Connector, use a senha VMAdmin para a senha do CceService quando solicitado. Insira a mesma senha inserida anteriormente para a implantação do Cloud Connector para todas as outras contas.
    
     Se o arquivo de senha em cache foi gerado com a versão 1.4.2 do Cloud Connector e as senhas de DomainAdmin e VMAdmin são diferentes, você deve executar as seguintes etapas:
    
  7. Execute Set-CcCredential -AccountType DomainAdmin da seguinte forma:
    
  8. Quando solicitado a inserir a credencial da conta antiga, insira a credencial usada para a senha do CceService.
    
  9. Quando for solicitado a nova credencial da conta, insira a senha do DomainAdmin que você usou antes.
    
     Se o arquivo de senha em cache tiver sido gerado com a versão 2.0 ou posterior do Cloud Connector, por padrão, VmAdmin e DomainAdmin usarão a mesma senha do CceService. Se você alterou as senhas DomainAdmin e VMAdmin, deve executar as seguintes etapas:
    
  10. Execute Set-CcCredential -AccountType DomainAdmin da seguinte forma:
    
       1. Quando solicitado a inserir a credencial da conta antiga, insira a credencial usada para a senha do CceService
    
       2. Quando for solicitado a nova credencial da conta, insira a senha do DomainAdmin que você usou antes.
    
  11. Execute Set-CcCredential -AccountType VmAdmin da seguinte forma:
    
       1. Quando solicitado a inserir a credencial da conta antiga, insira a credencial usada para a senha do CceService
    
       2. Quando for solicitado a nova credencial da conta, insira a senha do VmAdmin que você usou antes. 
    
- **Problema: com o Cloud Connector versão 2.1 e posterior, ao executar o Register-CcAppliance ou outros cmdlets no dispositivo, você recebe uma mensagem de erro como: "Para o Each-Object: a propriedade 'Common' não pode ser encontrada neste objeto. Verifique se a propriedade existe. Em C:\Programa Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**
    
    **Resolução:** O Cloud Connector 2.1 e posterior requer o .NET Framework 4.6.1 ou posterior. Atualize o .NET Framework no dispositivo para a versão 4.6.1 ou posterior e execute os cmdlets novamente.

- **Problema: com o Cloud Connector Edition 2.1, ao executar Install-CcAppliance, você recebe uma mensagem de erro como: "Falha ao instalar nova instância com erro: não é possível definir "State" porque somente cadeias de caracteres podem ser usadas como valores para definir propriedades XmlNode"**

   **Resolução:** In Cloudconnector.ini, under the [Common] section, please add the "State" config as below: CountryCode=US State=WA City=Redmond

   Não é obrigatório que a linha "State" tenha valor, mas a linha "State" não pode ser removida do arquivo Cloudconnector.ini arquivo.

- **Problema: você recebe a seguinte mensagem de erro "Dismount-WindowsImage : Dismount-WindowsImage falhou. Código de erro = 0xc1550115" ao instalar ou atualizar o Cloud Connector Edition.**
    
    **Resolução:** Iniciar um console do PowerShell como administrador, execute "DISM -Cleanup-Wim'". Isso limpará todas as imagens problemáticas. Execute Install-CcAppliance novamente ou aguarde até que os bits atualizem automaticamente.
    
- **Problema: falha na implantação do primeiro dispositivo do Cloud Connector em um ambiente de HA**
    
    **Resolução:** As etapas a serem tomadas dependem do motivo pelo qual a implantação falhou:
    
  - Se o primeiro dispositivo do Cloud Connector falhar e você não puder determinar o motivo da falha, deverá instalá-lo novamente até que a implantação seja bem-sucedida e, em seguida, instalar os outros dispositivos.
    
  - Se o primeiro dispositivo do Cloud Connector falhar com um pequeno problema, como um problema de certificado externo, você poderá corrigir o problema sem re-instalar o dispositivo. Em seguida, você pode usar o PowerShell remoto do locatário para marcar a implantação como bem-sucedida da seguinte forma. (Você também pode usar as etapas a seguir se a primeira implantação foi bem-sucedida, mas, por algum motivo, o Cloud Connector falha ao relatar a implantação como um sucesso.)
    
  - Para obter a Identidade (GUID) do primeiro dispositivo do Cloud Connector, execute o Get-CsHybridPSTNAppliance cmdlet.
    
  - Para marcar o dispositivo como implantado com êxito, execute o Set-CsCceApplianceDeploymentStatus da seguinte maneira:
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- **Problema: você precisa verificar e instalar as atualizações do Windows manualmente no servidor host ou nas máquinas virtuais.**
    
   **Resolução:** Recomendamos que você aproveite as atualizações automatizadas do sistema operacional fornecidas pelo Skype for Business Cloud Connector Edition. Depois que um dispositivo for registrado para gerenciamento online e a atualização automática do sistema operacional estiver habilitada, o servidor host e as máquinas virtuais verificarão e instalarão as atualizações do Windows automaticamente de acordo com as configurações da janela de tempo de atualização do sistema operacional.
    
   Se você precisar verificar e instalar as atualizações do Windows manualmente, siga as etapas nesta seção que se aplicam ao seu tipo de implantação. Você deve planejar a atualização do servidor host e das máquinas virtuais em execução nele ao mesmo tempo para minimizar a quantidade de tempo de inação necessário para as atualizações.
    
   Se preferir, você pode usar um servidor do Windows Server Update Services (WSUS) para fornecer atualizações aos servidores do Cloud Connector. Apenas certifique-se de configurar o Windows Update para **não ser instalado** automaticamente.
    
   Para obter informações sobre como atualizar manualmente sua implantação do Cloud Connector, consulte a seção a seguir.
    
- **Problema: quando o Cloud Connector atualiza para um novo build, os cmdlets do Cloud Connector não são atualizados.** Isso às vezes acontece se uma janela do PowerShell for deixada aberta quando a atualização automática ocorrer.
    
  **Resolução:** Para carregar os cmdlets atualizados, você pode seguir uma das seguintes etapas:
    
   - Feche o PowerShell no dispositivo do Cloud Connector e reabra o PowerShell.
    
     - Ou você pode executar o Import-Module CloudConnector -Force. 
 
-   **Problema: "O termo 'Stop-CsWindowsService' não é reconhecido como o nome de um cmdlet, função, arquivo de script ou programa operável". Erro ao tentar executar Enter-CcUpdate cmdlet.**

    **Resolução:** Exclu$ $ $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache.
O PowerShell cria esse arquivo como um cache de cmdlets a partir de módulos que ele encontra para que ele não tenha que analisar todos os módulos sempre que isso faria as coisas realmente lentas. Provavelmente, houve alguma corrupção de arquivo que forneceu resultados enganosos para o PowerShell quando ele estava lendo de volta desse cache.

-   **Problema: "Import-Module CloudConnector" gera o erro "Import-Module: The specified module "CloudConnector" was not loaded because no valid module file was found in any module directory"**

    **Resolução:**
    - Valide que, na verdade, o módulo CloudConnector existe em c:\Arquivos de Programas\WindowsPowerShell\Modules
    
    - Depois de validar que o módulo CloudConnector existe nesse local, a variável de ambiente PSModulePath que armazenar o caminho para os locais dos módulos pode ser alterada:
    
     a. Alteração temporária: Inicie o PowerShell como Administrador e execute o seguinte comando: $env:PSModulePath = $env:PSModulePath + "; C:\Arquivos de Programas\WindowsPowerShell\Módulos\"
        
     b. Para alterações persistentes, inicie o PowerShell como Administrador e execute os seguintes comandos, um a um: $CurrentValue = [Ambiente]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules", "Machine")

    
## <a name="install-windows-updates-manually"></a>Instalar atualizações do Windows manualmente

Se você não quiser usar as atualizações automáticas em seu ambiente, siga estas etapas para verificar e aplicar as atualizações do Windows manualmente. Verificar e instalar atualizações do Windows pode exigir uma reinicialização do servidor. Quando um servidor host estiver reiniciando, os usuários não poderão usar o Cloud Connector para fazer ou receber chamadas. Você pode verificar e instalar atualizações manualmente para controlar quando as atualizações ocorrerão e, em seguida, reiniciar os máquinas conforme necessário durante os momentos que você optar por evitar a interrupção dos serviços.
  
Para verificar manualmente se há atualizações, conecte-se a cada servidor host e abra o Painel **de Controle.** Selecione **Sistema e Segurança do Windows \> Update** e gerencie as atualizações e as reinicializações do servidor conforme apropriado para seu ambiente.
  
- Se houver apenas um dispositivo no site, conecte-se a cada máquina virtual e abra o Painel **de Controle.** Selecione **Sistema e Segurança do Windows \> Update** e configure as atualizações e as reinicializações do servidor conforme apropriado.
    
- Se houver mais de um dispositivo no site, a instância que está sendo atualizada e reiniciada não poderá ser acessada pelos usuários durante as atualizações. Os usuários se conectarão a outras instâncias na implantação até que todas as máquinas virtuais e todos os serviços do Skype for Business iniciem nas máquinas virtuais após a conclusão das atualizações. Para evitar possíveis interrupções no serviço, você pode remover a instância da alta segurança enquanto aplica as atualizações e restaurá-la ao concluir. Para fazer isso:
    
1. Em cada servidor host, abra um console do PowerShell como administrador.
    
2. Remova a instância da alta com o seguinte cmdlet:
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    Siga as etapas para uma única instância aplicar manualmente as atualizações e reiniciar a máquina virtual.
    
4. De definir a instância de volta para ALTA com o seguinte cmdlet:
    
   ```powershell
   Exit-CcUpdate
   ```

Para implantações de vários sites, siga as etapas para um único site para cada site na implantação, aplicando atualizações a um site por vez.
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a>Dicas ao instalar software antivírus no computador host do Cloud Connector

Se você precisar instalar o software antivírus na máquina host do Cloud Connector, será necessário adicionar as seguintes exclusões:
  
- Diretório de Dispositivos Local em cada computador.
    
- Diretório de Sites Remotos em cada computador.
    
- O Diretório de Sites Local no computador hospeda a pasta raiz do site compartilhado.
    
- %ProgramFiles%\Skype for Business Cloud Connector Edition
    
- %ALLUSERSPROFILE%\CloudConnector
    
- %ProgramFiles%\WindowsPowerShell\Modules\CloudConnector
    
- O processo Microsoft.Rtc.CCE.ManagementService.exe.
