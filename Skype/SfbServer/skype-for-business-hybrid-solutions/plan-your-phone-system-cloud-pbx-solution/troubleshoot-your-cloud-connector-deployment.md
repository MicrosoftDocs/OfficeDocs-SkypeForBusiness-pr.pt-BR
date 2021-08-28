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
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: Solucionar problemas de implantação do Cloud Connector Edition.
ms.openlocfilehash: 95a3a89e4ae593ffa972f7b5de3891ee94aaeff6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58623399"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a>Solução de problemas de implantação do Cloud Connector

> [!Important]
> O Cloud Connector Edition se aposentará em 31 de julho de 2021 junto com Skype for Business Online. Depois que sua organização tiver sido atualizada para Teams, saiba como conectar sua rede de telefonia local ao Teams usando [Roteamento Direto.](/MicrosoftTeams/direct-routing-landing-page)
 
Solucionar problemas de implantação do Cloud Connector Edition.
  
Este tópico descreve soluções para problemas comuns com implantações do Cloud Connector Edition. Se você estiver enfrentando problemas com chamadas de e para a PSTN (Rede Telefônica Pública Comucionada), você pode investigar seguindo as soluções descritas neste tópico.
  
O Cloud Connector fornece mecanismos integrados para resolver automaticamente alguns problemas. Um processo de detecção automática procura possíveis problemas com os dispositivos do Cloud Connector e, se possível, toma medidas corretivas para resolver esses problemas sem a necessidade de intervenção do administrador. O processo de detecção funciona da seguinte forma:
  
- **Sequência de detecção:** O serviço de Gerenciamento do Cloud Connector executa um processo a cada 60 segundos para detectar se um dispositivo está ino mesmo. No Cloud Connector versão 2.0 e posterior, o processo de detecção usa a opção Skype for Business Corpnet para fazer conexões do PowerShell com os máquinas do Cloud Connector; para versões anteriores a 2.0, o processo de detecção usa a opção de gerenciamento do Cloud Connector.
    
    > [!NOTE]
    > Para que a recuperação automática seja bem-sucedida, deve haver conectividade de rede entre o host e as máquinas virtuais por meio da opção de rede do host. Verifique a conectividade de rede para garantir que a detecção e a recuperação automática possam ser bem-sucedidas. 
  
- **Monitoramento:** Os seguintes serviços são monitorados no Cloud Connector versão 2.0 e posterior:
    
  - As Máquinas Virtuais não estão conectadas aos comutadores virtuais corporativos ou da Internet do Cloud Connector
    
  - As Máquinas Virtuais estão em um status salvo ou interrompido
    
  - Serviços do Servidor de Gerenciamento Central: RÉPLICA, MASTER
    
  - Serviços do Servidor de Mediação: RÉPLICA, RTCSRV e MEDSVC
    
  - Serviços do Servidor de Borda: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY
    
  - As regras de firewall de entrada estão desabilitadas para CS RTCSRV no servidor de Borda, CS RTCMEDSRV no servidor de mediação
    
    No Cloud Connector versão 1.4.2, somente os seguintes serviços são monitorados:
    
  - Serviços do Servidor de Mediação: RTCSRV e MEDSVC
    
  - Serviço de Servidor de Borda: RTCSRV
    
- **Processo de recuperação:** Se algum serviço monitorado estiver inosse, um dispositivo será marcado para baixo e os serviços serão interrompidos e marcados manualmente até que todos os problemas possam ser resolvidos. Isso impedirá que as chamadas roteem para um dispositivo que possa causar falhas de chamada.
    
    O serviço de Gerenciamento do Cloud Connector repetirá a recuperação automática da seguinte forma
    
  - O intervalo inicial de nova tentativa é a cada dez segundos com um intervalo máximo de uma hora.
    
  - Para as três primeiras tentativas de recuperação, o tempo de intervalo é de 10 segundos. A partir da quarta tentativa, o tempo de intervalo aumenta duas vezes o tempo de intervalo anterior. Por exemplo, a quarta tentativa ocorrerá em 20 segundos, a quinta em 40 segundos e assim por diante. 
    
  - Quando o tempo máximo de intervalo de uma hora é atingido, as recuperações continuarão uma vez por hora.
    
  - Quando a recuperação é bem-sucedida, as contagens de intervalo e de tentativa são definidas como seus valores iniciais.
    
  - Se o serviço de Gerenciamento for reiniciado, as contagens de intervalo e de nova tentativa serão redefinidas para seus valores iniciais.
    
## <a name="troubleshooting"></a>Solução de problemas

A seguir estão soluções para problemas comumente encontrados:
  
- **Problema: a implantação falha ou para de responder ao executar os scripts de implantação. Depois de fazer logon em cada VM, o endereço IP está ausente ou incorreto para a NIC Gerenciamento/Interna/Externa.**
    
    **Resolução:** Esse problema não pode ser resolvido automaticamente. Os NICs não podem ser adicionados a VMs enquanto eles estão em execução. Desligue e remova essas VMs no gerenciador hyper-v e execute os seguintes cmdlets:
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    **Problema: depois que o Servidor do Active Directory e a floresta são instalados, o Servidor CMS e/ou Servidor de Mediação não ingressaram no domínio corretamente.**
    
    **Resolução:** Para resolver esse problema, tome as seguintes etapas:
    
  - Faça logoff no Servidor do Active Directory e verifique se o domínio foi criado corretamente.
    
  - Faça logon no SERVIDOR CMS/Mediação e verifique se, na NIC da corpnet, um endereço IP válido está atribuído e se o IP estático válido e DNS está configurado como o endereço IP do servidor AD.
    
  - Faça logon no SERVIDOR CMS/Mediação e abra um prompt de comando. Certifique-se de que você pode pingar o FQDN e o endereço IP do Servidor do Active Directory. Se você não puder, pode haver um conflito de endereço IP. Tente atribuir um novo IP para o Active Directory e atualize o DNS no servidor CMS/Mediação de acordo.
    
- **Problema: Você recebe a seguinte mensagem de erro, "Remove-VMSwitch : Falhou ao remover a opção Ethernet virtual. A opção virtual 'Cloud Connector Management Switch' não pode ser excluída porque está sendo usada pela execução de máquinas virtuais ou atribuída a pools filho."**
    
    **Resolução:** O "Cloud Connector Management Switch" não foi excluído após a implantação. Se você tiver atingido esse erro, vá até o gerente do Hyper-v e verifique se ainda não há uma máquina virtual conectada a ela. Se ainda houver máquinas virtuais conectadas, desconecte-as e exclua a opção de gerenciamento. Se a opção de gerenciamento ainda não puder ser excluída, reinicie o servidor host e tente novamente.
    
- **Problema: Você recebe a seguinte mensagem de erro: "Falha ao iniciar o serviço RTCMRAUTH. Verifique se o serviço não está desabilitado."**
    
    > [!NOTE]
    > Esse problema só se aplica a versões do Cloud Connector anteriores a 1.4.2. 
  
    A falha ao iniciar também pode ser porque esse servidor Front-End foi anteriormente reprovado (usando o fail over do computador). Se esse for o caso, invoque fail-back (usando o fail back do computador).
    
    **Resolução:** Esse problema acontece em um Servidor de Borda quando o certificado de AC raiz ou certificado de AC intermediário não é confiável pelo Servidor de Borda. Mesmo que o certificado externo possa ser importado, mas a cadeia de certificados estiver quebrada. Nessa condição, o serviço RTCMRAUTH e/ou RTCSRV não pode iniciar.
    
    Importe o certificado de AC raiz e todos os certificados ca intermediários do certificado externo manualmente para o Servidor de Borda e reinicie o Servidor de Borda. Depois de ver os serviços RTCMRAUTH e RTCSRV iniciados no Servidor de Borda, volte para o servidor host, iniciar um console do PowerShell como administrador e executar o seguinte cmdlet para alternar para a nova implantação:
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    **Problema: o servidor host foi reiniciado quando Windows as atualizações foram aplicadas e as chamadas a serviço pelo servidor estão falhando.**
    
    **Resolução:** Se você implantou um ambiente de alta disponibilidade, a Microsoft fornece um cmdlet para ajudar a mover uma máquina host (instância de implantação) para dentro ou para fora da topologia atual ao verificar e instalar Windows atualização manualmente. Use as etapas a seguir para fazer isso:
    
1. No servidor host, inicie um console do PowerShell como administrador e execute:
    
   ```powershell
   Enter-CcUpdate
   ```

2. Verifique se há atualizações e instale todas as que estão disponíveis.
    
3. No console do PowerShell, execute o seguinte cmdlet:
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    **Problema: quando uma chamada é feita de um cliente Skype for Business usando um número PSTN, a chamada não pode ser escalonada para uma conferência convidando outro número PSTN.**
    
    **Resolução:** Para resolver esse problema, consulte [Configure online hybrid Mediation Server Configurações](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).
    
- **Problema: uma mensagem de aviso é exibida Windows atualização quando você está instalando o servidor do Active Directory - "Windows atualização automática não está habilitada. Para garantir que sua função ou recurso recém-instalado seja atualizado automaticamente, a Windows Update."**
    
    **Resolução:** Iniciar uma sessão do Tenant Remote PowerShell usando Skype for Business de administrador de locatários e execute o seguinte cmdlet para verificar a configuração _EnableAutoUpdate_ do seu site:
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    Se _EnableAutoUpdate_ estiver definido como **True**, você poderá ignorar com segurança essa mensagem de aviso porque o serviço CCEManagement tratará de baixar e instalar atualizações Windows para máquinas virtuais e o servidor host. Se  _EnableAutoUpdate_ for definido como **False**, execute o seguinte cmdlet para defini-lo como **True**.
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    Como alternativa, você pode verificar manualmente e instalar atualizações. Confira a próxima seção.
    
- **Problema: você recebe uma mensagem de erro: não é possível registrar o dispositivo porque sua entrada/configuração atual ou ou conflitos com os \<SiteName\> \<ApplianceName\> \<Mediation Server FQDN\> \<Mediation Server IP Address\> dispositivos existentes. Remova o dispositivo de conflito ou atualize suas informações de entrada/configuração e registre-se novamente. ' ao executar Register-CcAppliance para registrar o dispositivo atual online.**
    
    **Resolução:** Valores para \<ApplianceName\> o , e devem ser \<Mediation Server FQDN\> \<Mediation Server IP Address\> exclusivos e usados apenas para um registro de dispositivo. Por padrão, \<ApplianceName\> vem do nome do host. \<Mediation Server FQDN\> e \<Mediation Server IP Address\> definido no arquivo de configuração ini.
    
    Por exemplo, usando (ApplianceName= MyserverNew, FQDN=ms.contoso.com, Endereço IP do Servidor de Mediação=10.10.10.10) para registrar-se em SiteName=MySite, mas se houver um dispositivo registrado (ApplianceName= Myserver, Servidor de Mediação FQDN=ms.contoso.com, Endereço IP do Servidor de Mediação=10.10.10.10), você terá o conflito.
    
    Primeiro, verifique seu arquivo CloudConnector.ini na seção Diretório ApplianceRoot. Você receberá \<SiteName\> valores e valores no \<Mediation Server FQDN\> \<Mediation Server IP Address\> arquivo. \<ApplianceName\> é o nome do servidor host.
    
    Em segundo lugar, iniciar o PowerShell Remoto do Locatário usando suas credenciais de administrador de locatários do Skype for Business e, em seguida, execute o cmdlet a seguir para verificar os dispositivos registrados.
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    Depois de identificar quaisquer conflitos, você pode atualizar seu arquivo CloudConnector.ini com informações que corresponde ao dispositivo registrado ou não registrar o dispositivo existente para resolver os conflitos.
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- **Problema: o Get-CcRunningVersion cmdlet retorna um valor vazio se houver um dispositivo implantado em execução no host.**
    
  **Resolução:** Isso pode acontecer quando você atualiza de 1.3.4 ou 1.3.8 para 1.4.1. Depois de instalar a versão 1.4.1 com o .msi, você deve executar antes de executar `Register-CcAppliance` qualquer outro cmdlet. `Register-CcAppliance` migrará o arquivo module.ini de %UserProfile%\CloudConnector para %ProgramData%\CloudConnector. Se você não tiver perdido, um novo module.ini será criado na pasta %ProgramData%\CloudConnector e substituirá as informações de versão de execução/backup por 1.3.4 ou 1.3.8.
    
  Compare module.ini arquivos em %UserProfile%\CloudConnector e %ProgramData%\Pasta CloudConnector. Se houver diferenças, exclua o arquivo module.ini em %ProgramData%\CloudConnector e reprise  `Register-CcAppliance` . Você também pode modificar o arquivo manualmente para a versão correta de execução e backup.
    
- **Problema: depois de executar o cmdlet Switch-CcVersion para alternar para uma versão antiga que é diferente da versão de script atual, não há suporte para Alta Disponibilidade para essa versão antiga.**
    
    **Resolução:** Por exemplo, você atualizou de 1.4.1 para 1.4.2. Sua versão de script atual, que pode ser determinada executando e sua versão em execução, que pode ser determinada pela execução são `Get-CcVersion`  `Get-CcRunningVersion` 1.4.2. Neste momento, se você executar para alternar a versão em execução de volta para 1.4.1, não haverá suporte para Alta Disponibilidade para `Switch-CcVersion` essa versão antiga.
    
    Para obter suporte completo a Alta Disponibilidade, alternar de volta para 1.4.2, para que a versão em execução e a versão de script sejam as mesmas. Se você estiver enfrentando problemas com sua implantação 1.4.2, desinstale e reinstale-o assim que possível.
    
- **Problema: certificados de autoridade de certificado ou certificados internos emitidos para o Armazenamento de Gerenciamento Central, o Servidor de Mediação e o Servidor de Borda estão próximos de expirar ou estão comprometidos.**
    
    **Resolução:** Skype for Business certificados de autoridade de certificação são válidos por cinco anos. Os certificados internos emitidos para o Armazenamento de Gerenciamento Central, o Servidor de Mediação e o Servidor de Borda são válidos por dois anos.
    
    > [!NOTE]
    > No Cloud Connector versão 2.0 e posterior, o cmdlet Renew-CcServerCertificate foi alterado para Update-CcServerCertificate e o cmdlet Renew-CcCACertificate foi alterado para Update-CcCACertificate. 
  
    Se os certificados internos emitidos para o Armazenamento de Gerenciamento Central, o Servidor de Mediação e o Servidor de Borda estão próximos da expiração ou comprometidos, execute o cmdlet Renew-CcServerCertificate ou Update-CcServerCertificate para renovar seus certificados.
    
    Se os certificados de autoridade de certificação estão próximos de expirar, execute o cmdlet Renew-CcCACertificate ou Update-CcCACertificate para renovar seus certificados.
    
    **Se os certificados de autoridade de** certificação estão comprometidos e há apenas um dispositivo no site, execute as seguintes etapas:
    
1. Execute o cmdlet Enter-CcUpdate para drenar os serviços e colocar o dispositivo no modo de manutenção.
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. Execute os seguintes cmdlets para redefinir e criar novos certificados de autoridade de certificação e todos os certificados de servidor internos:
    
    Para versões do Cloud Connector antes de 2.0:
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    Ou para a versão 2.0 do Cloud Connector e posterior:
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. Se o TLS for usado entre o gateway e o Servidor de Mediação, execute o cmdlet Export-CcRootCertificate do dispositivo e instale o certificado exportado para seus gateways PSTN. Você também pode ser obrigado a reemissão do certificado em seu gateway.

   ```powershell
   Export-CcRootCertificate
   ```

4. Execute o cmdlet Exit-CcUpdate para iniciar os serviços e sair do modo de manutenção.

   ```powershell
   Exit-CcUpdate
   ```


    **Se os certificados de** autoridade de certificação estão comprometidos e há vários dispositivos no site, execute as etapas sequenciais a seguir em cada dispositivo no site.
    
    A Microsoft recomenda que você execute essas etapas durante os horários de uso que não são de pico.
    
1. No primeiro dispositivo, execute o cmdlet Remove-CcCertificationAuthorityFile para limpar os arquivos de backup da CA no \<SiteRoot\> diretório.

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. Execute o cmdlet Enter-CcUpdate para drenar os serviços e colocar cada dispositivo no modo de manutenção.

     ```powershell
     Enter-CcUpdate
     ```
    
3. No primeiro dispositivo, execute os seguintes cmdlets para redefinir e criar novos certificados de autoridade de certificação e todos os certificados de servidor internos:
    
     Para versões do Cloud Connector antes de 2.0:
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     Ou para a versão 2.0 do Cloud Connector e posterior:
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. No primeiro dispositivo, execute o seguinte cmdlet para fazer o back up dos arquivos ca na \<SiteRoot\> pasta.
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. Em todos os outros dispositivos no mesmo site, execute os seguintes comandos para consumir os arquivos de backup da CA, para que todos os dispositivos usem o mesmo certificado raiz e solicitem novos certificados. 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. Se o TLS for usado entre o gateway e o Servidor de Mediação, execute o cmdlet Export-CcRootCertificate de qualquer dispositivo no site e instale o certificado exportado para seus gateways PSTN. Você também pode ser obrigado a reemissão do certificado em seu gateway.
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. Execute o cmdlet Exit-CcUpdate para iniciar os serviços e sair do modo de manutenção. 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- **Problema: você recebe a seguinte mensagem de erro no Log de Serviço de Gerenciamento do Cloud Connector, "C:\Arquivos de Programas\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": Erro CceService: 0 : exceção inesperada ao relatar o status para online: System.Management.Automation.CmdletInvocationException: Falha no logon para o usuário \<Global Tenant Admin\> . Crie um novo objeto de credencial, certifique-se de ter usado o nome de usuário e a senha corretos. ---\>**
    
    **Resolução:** As Microsoft 365 ou Office 365 de administrador de locatários globais foram alteradas desde que o dispositivo do Cloud Connector foi registrado. Para atualizar as credenciais armazenadas localmente no dispositivo do Cloud Connector, execute o seguinte do Administrador do PowerShell no dispositivo host:
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- **Problema: depois de alterar a senha da conta de servidor host usada para a implantação, você recebe a seguinte mensagem de erro: "ConvertTo-SecureString : Chave não válida para uso no estado especificado." em %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log ou durante a execução do cmdlet Get-CcCredential.**
    
    **Resolução:** Todas as credenciais do Cloud Connector são armazenadas no seguinte arquivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml". Quando a senha no servidor host for mudada, você precisará atualizar as credenciais armazenadas localmente.
    
    **Se você estiver executando o Cloud Connector versão 1.4.2,** regenere todas as senhas do Cloud Connector seguindo estas etapas:
    
  1. Reinicie o servidor host.
    
  2. Exclua o seguinte arquivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml".
    
  3. Iniciar um console do PowerShell como administrador e executar "Register-CcAppliance -Local" para inserir as senhas após a descrição. Insira as mesmas senhas inseridas antes para a implantação do Cloud Connector.
    
     **Se você estiver executando o Cloud Connector versão 2.0** ou posterior, regenere todas as senhas do Cloud Connector seguindo estas etapas:
    
  4. Reinicie o servidor host.
    
  5. Exclua o seguinte arquivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml" .
    
  6. Iniciar um console do PowerShell como administrador e executar "Register-CcAppliance -Local" para inserir as senhas após a descrição. 
    
     Se o arquivo de senha em cache foi gerado com o Cloud Connector versão 1.4.2, use a senha VMAdmin para a senha CceService quando solicitado. Insira a mesma senha inserida antes para a implantação do Cloud Connector para todas as outras contas.
    
     Se o arquivo de senha em cache foi gerado com o Cloud Connector versão 1.4.2 e as senhas DomainAdmin e VMAdmin são diferentes, você deve executar as seguintes etapas:
    
  7. Execute Set-CcCredential -AccountType DomainAdmin da seguinte forma:
    
  8. Quando solicitado a usar a credencial da conta antiga, insira a credencial usada para a senha do CceService.
    
  9. Quando solicitado a nova credencial da conta, insira a senha da senha DomainAdmin que você usou antes.
    
     Se o arquivo de senha em cache foi gerado com o Cloud Connector versão 2.0 ou posterior, por padrão, VmAdmin e DomainAdmin usarão a mesma senha que CceService. Se você tiver alterado as senhas DomainAdmin e VMAdmin, deverá executar as seguintes etapas:
    
  10. Execute Set-CcCredential -AccountType DomainAdmin da seguinte forma:
    
       1. Quando solicitado a usar a credencial da conta antiga, insira a credencial usada para a senha do CceService
    
       2. Quando solicitado a nova credencial da conta, insira a senha da senha DomainAdmin que você usou antes.
    
  11. Execute Set-CcCredential -AccountType VmAdmin da seguinte forma:
    
       1. Quando solicitado a usar a credencial da conta antiga, insira a credencial usada para a senha do CceService
    
       2. Quando solicitado para a nova credencial da conta, insira a senha da senha VmAdmin que você usou antes. 
    
- **Problema: com o Cloud Connector versão 2.1 e posterior, ao executar o Register-CcAppliance ou outros cmdlets no dispositivo, você recebe uma mensagem de erro como: "Para Each-Object : a propriedade 'Common' não pode ser encontrada neste objeto. Verifique se a propriedade existe. Em C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**
    
    **Resolução:** O Cloud Connector 2.1 e posterior requer .NET Framework 4.6.1 ou posterior. Atualize .NET Framework no dispositivo para a versão 4.6.1 ou posterior e execute os cmdlets novamente.

- **Problema: com o Cloud Connector Edition 2.1, ao executar Install-CcAppliance, você recebe uma mensagem de erro como: "Falha ao instalar nova instância com erro: não é possível definir "Estado" porque somente cadeias de caracteres podem ser usadas como valores para definir propriedades XmlNode"**

   **Resolução:** Em Cloudconnector.ini, na seção [Comum], adicione a configuração "Estado" abaixo: CountryCode=US State=WA City=Redmond

   Não é obrigatório que a linha "State" tenha valor, no entanto, a linha "State" não pode ser removida do arquivo Cloudconnector.ini.

- **Problema: Você recebe a seguinte mensagem de erro "Dismount-WindowsImage : Dismount-WindowsImage falhou. Código de erro = 0xc1550115" ao instalar ou atualizar o Cloud Connector Edition.**
    
    **Resolução:** Iniciar um console do PowerShell como administrador, execute "DISM -Cleanup-Wim'". Isso limpará todas as imagens problemáticas. Execute Install-CcAppliance ou aguarde que os bits atualizem automaticamente.
    
- **Problema: Falha na implantação do primeiro dispositivo do Cloud Connector em um ambiente de HA**
    
    **Resolução:** As etapas que você tomar dependem do motivo pelo qual a implantação falhou:
    
  - Se o primeiro dispositivo do Cloud Connector falhar e você não puder determinar o motivo da falha, instale o dispositivo novamente até que a implantação seja bem-sucedida e instale os outros dispositivos.
    
  - Se o primeiro dispositivo do Cloud Connector falhar com um problema secundário, como um problema de certificado externo, talvez seja possível corrigir o problema sem instalar o dispositivo. Em seguida, você pode usar o PowerShell remoto do locatário para marcar a implantação como bem-sucedida da seguinte forma. (Você também pode usar as etapas a seguir se a primeira implantação foi bem-sucedida, mas, por algum motivo, o Cloud Connector não relata a implantação como um sucesso.)
    
  - Para obter a Identidade (GUID) do primeiro dispositivo do Cloud Connector, execute o cmdlet Get-CsHybridPSTNAppliance de nuvem.
    
  - Para marcar o dispositivo como implantado com êxito, execute o Set-CsCceApplianceDeploymentStatus da seguinte maneira:
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- **Problema: você precisa verificar e instalar Windows atualizações manualmente no servidor host ou em máquinas virtuais.**
    
   **Resolução:** Recomendamos que você aproveite as atualizações automatizadas do sistema operacional fornecidas pelo Skype for Business Cloud Connector Edition. Depois que um dispositivo é registrado para o gerenciamento online e a atualização automática do sistema operacional está habilitada, o servidor Windows host e máquinas virtuais verificarão e instalarão as atualizações automaticamente de acordo com as configurações da janela de atualização do sistema operacional.
    
   Se você precisar verificar e instalar Windows atualizações manualmente, siga as etapas nesta seção que se aplicam ao seu tipo de implantação. Você deve planejar a atualização do servidor host e das máquinas virtuais em execução nele ao mesmo tempo para minimizar a quantidade de tempo de inação necessária para as atualizações.
    
   Se preferir, você pode usar um servidor Windows Server Update Services (WSUS) para fornecer atualizações para servidores do Cloud Connector. Apenas certifique-se de configurar o Windows Update para **não instalar** automaticamente.
    
   Para obter informações sobre como atualizar manualmente sua implantação do Cloud Connector, consulte a seção a seguir.
    
- **Problema: quando o Cloud Connector é atualizado para uma nova com build, os cmdlets do Cloud Connector não são atualizados.** Isso às vezes acontece se uma janela do PowerShell for deixada aberta quando a atualização automática ocorrer.
    
  **Resolução:** Para carregar os cmdlets atualizados, você pode fazer uma das seguintes etapas:
    
   - Feche o PowerShell no dispositivo do Cloud Connector e reabra o PowerShell.
    
     - Ou, você pode executar Import-Module CloudConnector -Force. 
 
-   **Problema: "O termo 'Stop-CsWindowsService' não é reconhecido como o nome de um cmdlet, função, arquivo de script ou programa operável." ao tentar executar Enter-CcUpdate cmdlet.**

    **Resolução:** Exclua o arquivo $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache.
O PowerShell cria esse arquivo como um cache de cmdlets a partir de módulos que ele encontra para que ele não tenha que analisar todos os módulos sempre, pois isso torna as coisas muito lentas. Provavelmente, houve alguma corrupção de arquivo que forneceu resultados enganosos para o PowerShell quando ele estava lendo de volta desse cache.

-   **Problema: "Import-Module CloudConnector" gera erro "Import-Module: The specified module "CloudConnector" was not loaded because no valid module file was found in any module directory"**

    **Resolução:**
    - Valide se, na verdade, o módulo CloudConnector existe em c:\Arquivos de Programas\WindowsPowerShell\Modules
    
    - Depois de validar que o módulo CloudConnector existe nesse local, a variável de ambiente PSModulePath que armazenará o caminho para os locais dos módulos pode ser alterada:
    
     a. Alteração temporária: inicie o Powershell como administrador e execute o seguinte comando: $env:PSModulePath = $env:PSModulePath + "; C:\Arquivos de Programas\WindowsPowerShell\Modules\"
        
     b. Para alterações persistentes, inicie o PowerShell como administrador e execute os seguintes comandos, um a um: $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Arquivos de Programas\WindowsPowerShell\Modules", "Machine")

    
## <a name="install-windows-updates-manually"></a>Instalar Windows atualizações manualmente

Se você não quiser usar atualizações automáticas em seu ambiente, siga estas etapas para verificar manualmente e aplicar Windows atualizações. Verificar e instalar as atualizações Windows pode exigir uma reinicialização do servidor. Quando um servidor host estiver sendo reiniciado, os usuários não poderão usar o Cloud Connector para fazer ou receber chamadas. Você pode verificar manualmente e instalar atualizações para controlar quando as atualizações ocorrem e reiniciar os dispositivos conforme necessário durante os horários que você optar por evitar interrupção dos serviços.
  
Para verificar manualmente as atualizações, conecte-se a cada servidor host e abra o **Painel de Controle**. Selecione **Sistema e Segurança Windows \> Atualização** e, em seguida, gerencie as atualizações e reinicializações do servidor conforme apropriado para seu ambiente.
  
- Se houver apenas um dispositivo no site, conecte-se a cada máquina virtual e abra o **Painel de Controle**. Selecione **Sistema e Segurança Windows \> Atualização** e, em seguida, configure as atualizações e reinicializações do servidor conforme apropriado.
    
- Se houver mais de um dispositivo no site, a instância que está sendo atualizada e reiniciada não poderá ser acessada pelos usuários durante as atualizações. Os usuários se conectarão a outras instâncias na implantação até que todas as máquinas virtuais e todos os serviços Skype for Business iniciem nas máquinas virtuais após a conclusão das atualizações. Para evitar possíveis interrupções no serviço, você pode remover a instância do HA enquanto aplica as atualizações e restaurá-la quando concluída. Para fazer isso:
    
1. Em cada servidor host, abra um console do PowerShell como administrador.
    
2. Remova a instância de HA com o seguinte cmdlet:
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    Siga as etapas para que uma única instância aplique manualmente as atualizações e reinicie a máquina virtual.
    
4. De definir a instância de volta como HA com o seguinte cmdlet:
    
   ```powershell
   Exit-CcUpdate
   ```

Para implantações de vários sites, siga as etapas de um único site para cada site na implantação, aplicando atualizações a um site por vez.
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a>Dicas ao instalar software antivírus na máquina host do Cloud Connector

Se você precisar instalar software antivírus na máquina host do Cloud Connector, será necessário adicionar as seguintes exclusões:
  
- Diretório de Dispositivos Local em cada máquina.
    
- Diretório de Sites Remotos em cada máquina.
    
- O Diretório de Sites Local no computador hospeda a pasta raiz do site compartilhado.
    
- %ProgramFiles%\Skype for Business Cloud Connector Edition
    
- %ALLUSERSPROFILE%\CloudConnector
    
- %ProgramFiles%\WindowsPowerShell\Modules\CloudConnector
    
- O processo Microsoft.Rtc.CCE.ManagementService.exe.