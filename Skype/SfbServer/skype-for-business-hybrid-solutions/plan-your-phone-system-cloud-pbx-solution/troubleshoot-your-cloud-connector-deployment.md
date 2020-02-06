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
description: Solucionar problemas de implantação da edição do Cloud Connector.
ms.openlocfilehash: 3a6fd80cc0c4125303021746cdb626d8c5b49a5a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814219"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a>Solução de problemas de implantação do Cloud Connector
 
Solucionar problemas de implantação da edição do Cloud Connector.
  
Este tópico descreve soluções para problemas comuns em implantações do Cloud Connector Edition. Se você está tendo problemas com chamadas de entrada e saída PSTN (Rede Telefônica Pública Comutada), poderá investigar seguindo as soluções descritas neste tópico.
  
O Cloud Connector fornece mecanismos internos para resolver automaticamente alguns problemas. Um processo de detecção automática procura possíveis problemas com o Cloud Connector appliances e, se possível, toma uma ação corretiva para solucionar esses problemas sem a necessidade de intervenção do administrador. O processo de detecção funciona da seguinte maneira:
  
- **Sequência de detecção:** O serviço de gerenciamento do conector de nuvem executa um processo a cada 60 segundos para detectar se um dispositivo está inoperante. No Cloud Connector versão 2,0 e posterior, o processo de detecção usa a opção corpnet do Skype for Business para fazer conexões do PowerShell com os computadores do conector de nuvem; para versões anteriores ao 2,0, o processo de detecção usa a opção de gerenciamento do conector de nuvem.
    
    > [!NOTE]
    > Para que a recuperação automática seja bem-sucedida, deve haver conectividade de rede entre o host e máquinas virtuais no switch de rede do host. Certifique-se de verificar a conectividade da rede para garantir que a detecção automática e a recuperação possam ser bem-sucedidas. 
  
- **Monitoramento:** Os seguintes serviços são monitorados na versão 2,0 do Cloud Connector e posterior:
    
  - Máquinas virtuais não estão conectadas aos comutadores de nuvem corporativos ou virtuais da Internet
    
  - As máquinas virtuais estão em um status salvo ou parado
    
  - Serviços do servidor central de gerenciamento: réplica, mestre
    
  - Serviços do servidor de mediação: réplica, RTCSRV e MEDSVC
    
  - Serviços do servidor de borda: réplica, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY
    
  - As regras de firewall de entrada estão desabilitadas para CS RTCSRV no servidor de borda, CS RTCMEDSRV no servidor de mediação
    
    Na versão 1.4.2 do conector de nuvem, somente os seguintes serviços são monitorados:
    
  - Serviços do servidor de mediação: RTCSRV e MEDSVC
    
  - Serviço do servidor de borda: RTCSRV
    
- **Processo de recuperação:** Se algum serviço monitorado estiver inoperante, um dispositivo será marcado para baixo e os serviços serão interrompidos e marcados como manual até que todos os problemas possam ser resolvidos. Isso impedirá chamadas do roteamento para um dispositivo que pode causar falhas na chamada.
    
    O serviço de gerenciamento do conector de nuvem tentará automaticamente a recuperação automática da seguinte maneira
    
  - O intervalo inicial de repetição é a cada dez segundos com um tempo máximo de intervalo de uma hora.
    
  - Para as três primeiras tentativas de recuperação, o intervalo de tempo é de 10 segundos. A partir da quarta repetição, o tempo do intervalo aumenta em duas vezes o tempo anterior do intervalo. Por exemplo, a quarta tentativa ocorrerá em 20 segundos, a quinta em 40 segundos e assim por diante. 
    
  - Quando o tempo máximo de intervalo de uma hora for atingido, as tentativas continuarão uma vez por hora.
    
  - Quando a recuperação é bem-sucedida, os números intervalo e repetição são definidos como seus valores iniciais.
    
  - Se o serviço de gerenciamento for reiniciado, o intervalo e os números de repetição serão redefinidos para seus valores iniciais.
    
## <a name="troubleshooting"></a>Solução de problemas

Veja a seguir as soluções para problemas freqüentes encontrados:
  
- **Problema: a implantação falha ou para de responder durante a execução dos scripts de implantação. Depois de fazer logon em cada VM, o endereço IP está ausente ou está incorreto para a NIC de Gerenciamento/Interna/Externa.**
    
    **Resolução:** Esse problema não pode ser resolvido automaticamente. Desligue e remova essas VMs no Gerenciador do Hyper-V. Depois, execute estes cmdlets:
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    **Problema: após a instalação do Servidor do Active Directory e da floresta, o Servidor CMS e/ou o Servidor de Mediação não ingressou(aram) corretamente no domínio.**
    
    **Resolução:** para resolver esse problema, faça o seguinte:
    
  - Faça logon no Servidor do Active Directory e verifique se o domínio foi criado corretamente.
    
  - Faça logon no servidor CMS/Servidor de Mediação e verifique se foi atribuído um endereço IP válido à NIC da rede corporativa e se um DNS e um IP estático válidos foram configurados como endereço IP do servidor do AD.
    
  - Faça logon no servidor CMS/mediação e abra um prompt de comando. Verifique se é possível executar ping no FQDN e no endereço IP do Servidor do Active Directory. Se não o for, talvez haja um conflito de endereço IP. Tente atribuir um novo IP ao Active Directory e atualize apropriadamente o DNS no Servidor CMS/Servidor de Mediação.
    
- **Problema: você recebe a seguinte mensagem de erro: "Remove-VMSwitch: falha ao remover o comutador Ethernet virtual. A opção de gerenciamento do conector de nuvem do comutador virtual ' não pode ser excluída porque está sendo usada executando máquinas virtuais ou atribuídas a pools filho. "**
    
    **Resolução:** A "opção de gerenciamento do conector de nuvem" não foi excluída após a implantação. Se você clicar nesse erro, vá para o Gerenciador do Hyper-v e verifique se ainda não há uma máquina virtual conectada a ele. Se houver máquinas virtuais ainda conectadas, desconecte-as e exclua a opção de gerenciamento. Se a opção de gerenciamento ainda não puder ser excluída, reinicie o servidor host e tente novamente.
    
- **Problema: você recebe a seguinte mensagem de erro: "o serviço RTCMRAUTH falhou ao iniciar. Verifique se o serviço não está desabilitado. "**
    
    > [!NOTE]
    > Esse problema só se aplica a versões anteriores a 1.4.2 do Cloud Connector. 
  
    A falha de inicialização também pode ocorrer porque já foi feito failover desse Servidor Front-End (usando o failover do computador). Se for o caso, invoque o failback (usando o failback do computador).
    
    **Resolução:** esse problema acontece no Servidor de Borda quando o Certificado de Autoridade de Certificação raiz ou o Certificado de Autoridade de Certificação intermediário não é confiável para o Servidor de Borda. Mesmo que o certificado externo possa ser importado, a cadeia de certificados está desfeita. Nessa situação, não é possível iniciar o serviço RTCMRAUTH e/ou RTCSRV.
    
    Importe manualmente o Certificado de Autoridade de Certificação raiz e todos os Certificados de Autoridade de Certificação intermediários de seu certificado externo para o Servidor de Borda e reinicie o Servidor de Borda. Depois que os serviços RTCMRAUTH e RTCSRV forem iniciados no Servidor de Borda, volte ao servidor host, inicie um console do PowerShell como administrador e execute o seguinte cmdlet para alternar para a nova implantação:
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    **Problema: o servidor host foi reiniciado durante a aplicação de atualizações do Windows e ocorrem falhas nas chamadas atendidas pelo servidor.**
    
    **Resolução:** se você tiver implantado um ambiente de alta disponibilidade, a Microsoft fornece um cmdlet para ajudar a transferir um computador host (instância de implantação) para dentro ou para fora da topologia atual durante a verificação e a instalação manual da atualização do Windows. Para fazer isso, execute estas etapas:
    
1. No servidor host, inicie um console do PowerShell como administrador e execute:
    
   ```powershell
   Enter-CcUpdate
   ```

2. Verifique se há atualizações e instale as que estiverem disponíveis.
    
3. No console do PowerShell, execute o seguinte cmdlet:
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    **Problema: quando é feita uma chamada do Cliente Skype for Business usando um número PSTN, não é possível escalonar a chamada para uma conferência por meio de um convite a outro número PSTN.**
    
    **Resolução:** Para solucionar esse problema, consulte [definir as configurações do servidor de mediação híbrida online](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).
    
- **Problema: durante a instalação do servidor do Active Directory, é exibida esta mensagem de aviso sobre o Windows Update: "A atualização automática do Windows não está habilitada. Para verificar se a função ou o recurso recém-instalado é atualizado automaticamente, ative o Windows Update."**
    
    **Resolução:** Inicie uma sessão do PowerShell remoto de locatário usando as credenciais de administrador de locatários do Skype for Business e execute o seguinte cmdlet para verificar a configuração do _EnableAutoUpdate_ do seu site:
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    Se _EnableAutoUpdate_ for definido como **true**, você poderá ignorar com segurança essa mensagem de aviso porque o serviço CCEManagement manipulará o download e a instalação das atualizações do Windows para as máquinas virtuais e o servidor host. Se _EnableAutoUpdate_ estiver definido como **false**, execute o cmdlet a seguir para defini-lo como **verdadeiro**.
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    Como opção, você pode verificar e instalar as atualizações manualmente. Consulte a próxima seção.
    
- **Problema: você recebe uma mensagem de erro: não é possível registrar o dispositivo porque o \<endereço\> IP \<do servidor\> de \<\> \<MediaName ou o FQDN ou o endereço\> IP do servidor de mediação atual ou o endereço IP do servidor de mediação está em conflito com os aplicativos existentes Remova o dispositivo de conflito ou atualize as informações de entrada/configuração e registre-se novamente. ' When Run-CcAppliance para registrar o aplicativo atual para online.**
    
    **Resolução:** Os valores para \<o reaparelhoname\> \<, o\> servidor \<de mediador de\> servidor FQDN e o endereço IP do servidor de mediação devem ser exclusivos e apenas usados para um registro de dispositivo. Por padrão, \<o nome\> do aplicativo vem do nome do host. \<Endereço\> IP do\> servidor \<de mediação e FQDN do servidor de mediação definido no arquivo ini de configuração.
    
    Por exemplo, ao usar (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) para se registrar em SiteName=MySite, se houver um dispositivo registrado (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), haverá um conflito.
    
    Primeiro, verifique o arquivo CloudConnector.ini na seção do diretório ApplianceRoot. Você obterá \<os\>valores \<de endereço\> IP\> do \<SiteName do servidor de mediação e do SiteName do servidor de mediação no arquivo. \<Appliancename\> é o nome do seu servidor host.
    
    Em seguida, inicie o PowerShell Remote locatário usando suas credenciais de administrador de locatário do Skype for Business e execute o cmdlet a seguir para verificar o (s) dispositivo (s) registrado (s).
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    Depois de identificar os conflitos, você poderá atualizar o arquivo CloudConnector.ini com informações compatíveis com o dispositivo registrado ou cancelar o registro do dispositivo existente para resolver os conflitos.
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- **Problema: o cmdlet Get-CcRunningVersion retorna um valor vazio se houver um dispositivo implantado em execução no host.**
    
  **Resolução:** Isso pode acontecer quando você atualiza do 1.3.4 ou do 1.3.8 para o 1.4.1. Depois de instalar a versão 1.4.1 com o. msi, você deve `Register-CcAppliance` executar antes de executar qualquer outro cmdlet. `Register-CcAppliance`migrará o arquivo module. ini de%UserProfile%\CloudConnector para%ProgramData%\CloudConnector. Se você a perdeu, um novo module. ini será criado na pasta%ProgramData%\CloudConnector e substituirá as informações sobre a versão de execução/backup do 1.3.4 ou do 1.3.8.
    
  Compare os arquivos module.ini das pastas %UserProfile%\CloudConnector e %ProgramData%\CloudConnector. Se houver diferenças, exclua o arquivo module. ini no%ProgramData%\CloudConnector e execute `Register-CcAppliance`novamente. Você também pode modificar o arquivo manualmente para a versão correta de execução e backup.
    
- **Problema: depois de executar o cmdlet switch-CcVersion para alternar para uma versão antiga diferente da versão do script atual, não há suporte de alta disponibilidade para esta versão antiga.**
    
    **Resolução:** Por exemplo, você atualizou de 1.4.1 para 1.4.2. Sua versão de script atual, que pode ser determinada pela `Get-CcVersion`execução, e sua versão em execução, que pode ser determinada `Get-CcRunningVersion` pela execução é de ambos 1.4.2. Nesse momento, se você executar `Switch-CcVersion` a versão de execução novamente no 1.4.1, não haverá suporte de alta disponibilidade para esta versão antiga.
    
    Para ter suporte completo para Alta Disponibilidade, alterne novamente para a versão 1.4.2. Assim, a versão em execução e a versão do script serão iguais. Se houver problemas com a implantação da versão 1.4.2, desinstale-a e instale-a novamente assim que possível.
    
- **Problema: os certificados da autoridade de certificação ou os certificados internos emitidos para o Repositório de Gerenciamento Central, o Servidor de Mediação e o Servidor de Borda estão prestes a expirar ou estão comprometidos.**
    
    **Resolução:** os certificados da autoridade de certificação do Skype for Business são válidos por cinco anos. Os certificados internos emitidos para o Repositório de Gerenciamento Central, o Servidor de Mediação e o Servidor de Borda são válidos por dois anos.
    
    > [!NOTE]
    > No Cloud Connector versão 2,0 e posterior, o cmdlet Renew-CcServerCertificate mudou para Update-CcServerCertificate, e o cmdlet Renew-CcCACertificate mudou para Update-CcCACertificate. 
  
    Se certificados internos emitidos para o repositório de gerenciamento central, servidor de mediação e Edge Server estiverem próximos de expiração ou comprometidos, execute o cmdlet Renew-CcServerCertificate ou Update-CcServerCertificate para renovar seus certificados.
    
    Se os certificados de autoridade de certificação estiverem prestes a expirar, execute o cmdlet Renew-CcCACertificate ou Update-CcCACertificate para renovar seus certificados.
    
    **Se os certificados de autoridade de certificação estiverem comprometidos e houver apenas um dispositivo no site,** execute as seguintes etapas:
    
1. Execute o cmdlet Enter-CcUpdate para esvaziar os serviços e colocar o dispositivo no modo de manutenção.
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. Execute os seguintes cmdlets para redefinir e criar novos certificados da autoridade de certificação e todos os certificados de servidor interno:
    
    Para versões do conector de nuvem antes de 2,0:
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    Ou para o Cloud Connector Release 2,0 e posterior:
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. Se o TLS for usado entre o gateway e o servidor de mediação, execute o cmdlet Export-CcRootCertificate do aparelho e instale o certificado exportado em seus gateways PSTN. Você também pode ser solicitado a emitir novamente o certificado em seu gateway.

   ```powershell
   Export-CcRootCertificate
   ```

4. Execute o cmdlet Exit-CcUpdate para iniciar serviços e sair do modo de manutenção.

   ```powershell
   Exit-CcUpdate
   ```


    **Se os certificados de autoridade de certificação estiverem comprometidos e houver vários dispositivos no site,** execute as seguintes etapas sequenciais em cada aplicativo do site.
    
    A Microsoft recomenda que você execute essas etapas durante horários de uso sem pico.
    
1. No primeiro dispositivo, execute o cmdlet Remove-CcCertificationAuthorityFile para limpar os arquivos de backup da CA no diretório \<SiteRoot\> .

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. Execute o cmdlet Enter-CcUpdate para drenar serviços e colocar cada utilitário no modo de manutenção.

     ```powershell
     Enter-CcUpdate
     ```
    
3. No primeiro dispositivo, execute os seguintes cmdlets para redefinir e criar novos certificados de autoridade de certificação e todos os certificados de servidor interno:
    
     Para versões do conector de nuvem antes de 2,0:
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     Ou para o Cloud Connector Release 2,0 e posterior:
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. No primeiro dispositivo, execute o cmdlet a seguir para fazer backup dos arquivos da CA para \<a\> pasta SiteRoot.
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. Em todos os outros aplicativos do mesmo site, execute os seguintes comandos para consumir os arquivos de backup da CA, para que todos os aplicativos usem o mesmo certificado raiz e, em seguida, solicite novos certificados. 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. Se o TLS for usado entre o gateway e o servidor de mediação, execute o cmdlet Export-CcRootCertificate de qualquer dispositivo no site e instale o certificado exportado em seus gateways PSTN. Você também pode ser solicitado a emitir novamente o certificado em seu gateway.
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. Execute o cmdlet Exit-CcUpdate para iniciar serviços e sair do modo de manutenção. 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- **Problema: você recebe a seguinte mensagem de erro no log do serviço de gerenciamento do Cloud Connector, "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService erro: 0: exceção inesperada ao relatar status para online: System. Management. Automation. CmdletInvocationException: falha no \<logon para o\>administrador de locatário global do usuário. Crie um novo objeto Credential, certificando-se de que você usou o nome de usuário e a senha corretos. ---\>**
    
    **Resolução:** As credenciais de administrador de locatário global do Office 365 foram alteradas desde que o dispositivo do conector de nuvem foi registrado. Para atualizar as credenciais armazenadas localmente no aparelho do Cloud Connector, execute o seguinte do administrador do PowerShell no dispositivo host:
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- **Problema: depois de alterar a senha da conta do servidor host que você usou para a implantação, você recebe a seguinte mensagem de erro: "ConvertTo-SecureString: a chave não é válida para uso no estado especificado." no%ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log ou durante a execução do cmdlet Get-CcCredential.**
    
    **Resolução:** Todas as credenciais do conector de nuvem são armazenadas no seguinte arquivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ". Quando for alterada a senha do servidor host, você precisará atualizar as credenciais armazenadas localmente.
    
    **Se você estiver executando a versão 1.4.2 do Cloud Connector,** regenere todas as senhas do Cloud Connector seguindo estas etapas:
    
  1. Reinicie o servidor host.
    
  2. Exclua o seguinte arquivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ".
    
  3. Inicie um console do PowerShell como administrador e, em seguida, execute "Register-CcAppliance-local" para inserir novamente as senhas após a descrição. Insira as mesmas senhas que você inseriu anteriormente para a implantação do Cloud Connector.
    
     **Se você estiver executando o Cloud Connector versão 2,0 ou posterior,** gere novamente todas as senhas do conector de nuvem seguindo estas etapas:
    
  4. Reinicie o servidor host.
    
  5. Exclua o seguinte arquivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ".
    
  6. Inicie um console do PowerShell como administrador e, em seguida, execute "Register-CcAppliance-local" para inserir novamente as senhas após a descrição. 
    
     Se o arquivo de senha em cache foi gerado com a versão 1.4.2 do Cloud Connector, use a senha do VMAdmin como a senha do CceService quando ela for solicitada. Insira a mesma senha que você inseriu anteriormente para a implantação do Cloud Connector para todas as outras contas.
    
     Se o arquivo de senha em cache foi gerado com a versão 1.4.2 do Cloud Connector e as senhas de DomainAdmin e VMAdmin forem diferentes, você deverá executar as seguintes etapas:
    
  7. Execute Set-CcCredential -AccountType DomainAdmin da seguinte maneira:
    
  8. Quando solicitada a antiga credencial da conta, insira a credencial que você usou para a senha do CceService.
    
  9. Quando for solicitada a nova credencial da conta, insira a senha do DomainAdmin usada anteriormente.
    
     Se o arquivo de senha em cache foi gerado com o Cloud Connector versão 2,0 ou posterior, por padrão, VmAdmin e DomainAdmin usam a mesma senha que CceService. Se você tiver alterado as senhas do DomainAdmin e VMAdmin, deverá executar as seguintes etapas:
    
  10. Execute Set-CcCredential -AccountType DomainAdmin da seguinte maneira:
    
       1. Quando solicitada a antiga credencial da conta, insira a credencial que você usou para a senha do CceService
    
       2. Quando for solicitada a nova credencial da conta, insira a senha do DomainAdmin usada anteriormente.
    
  11. Execute Set-CcCredential -AccountType VmAdmin da seguinte maneira:
    
       1. Quando solicitada a antiga credencial da conta, insira a credencial que você usou para a senha do CceService
    
       2. Quando for solicitada a nova credencial da conta, insira a senha do VmAdmin usada anteriormente.  
    
- **Problema: com o Cloud Connector versão 2,1 e posterior, ao executar Register-CcAppliance ou outros cmdlets no dispositivo, você recebe uma mensagem de erro como: "para cada objeto: a propriedade ' Common ' não pode ser encontrada nesse objeto. Verifique se a propriedade existe. Em C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 carac: 14 "**
    
    **Resolução:** O Cloud Connector 2,1 e posterior exige o .NET Framework 4.6.1 ou posterior. Atualize o .NET Framework no aparelho para a versão 4.6.1 ou posterior e execute o (s) cmdlet (s) novamente.

- **Problema: com o Cloud Connector Edition 2,1, ao executar install-CcAppliance, você recebe uma mensagem de erro como: "falha ao instalar nova instância com erro: não é possível definir" State "porque apenas cadeias de caracteres podem ser usadas como valores para definir propriedades XmlNode"**

   **Resolução:** No Cloudconnector. ini, na seção [Common], adicione a configuração "estado" da seguinte maneira: CountryCode = EUA state = WA City = Redmond

   Não é obrigatório para a linha "State" ter valor, mas a linha "State" não pode ser removida do arquivo Cloudconnector. ini.

- **Problema: você recebe a seguinte mensagem de erro "Dismount-WindowsImage: Dismount-WindowsImage falhou. Código de erro = 0xc1550115 "ao instalar ou atualizar a edição do conector de nuvem.**
    
    **Resolução:** Inicie um console do PowerShell como administrador, execute "DISM-Cleanup-wim" ". Isso limpará todas as imagens problemáticas. Execute Install-CcAppliance novamente ou aguarde a atualização automática dos bits.
    
- **Problema: a implantação do primeiro dispositivo de conector de nuvem em um ambiente de alta disponibilidade falha**
    
    **Resolução:** As etapas que você tomar dependerão do motivo da falha na implantação:
    
  - Se o primeiro dispositivo de conector de nuvem falhar e você não puder determinar o motivo da falha, instale o aparelho novamente até que a implantação seja bem-sucedida e, em seguida, instale os outros aparelhos.
    
  - Se o primeiro dispositivo de conector de nuvem falhar com um problema secundário, como um problema de certificado externo, talvez você possa corrigir o problema sem reinstalar o aparelho. Em seguida, você pode usar o PowerShell Remote locatário para marcar a implantação com êxito da seguinte maneira. (Você também pode usar as etapas a seguir se a primeira implantação tiver sido bem-sucedida, mas, por algum motivo, o Cloud Connector não conseguir relatar a implantação como sucesso.)
    
  - Para obter a identidade (GUID) do primeiro aparelho de conexão de nuvem, execute o cmdlet Get-CsHybridPSTNAppliance.
    
  - Para marcar o aparelho como implantado com êxito, execute o set-CsCceApplianceDeploymentStatus da seguinte maneira:
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- **Problemas: você precisa verificar e instalar as atualizações do Windows manualmente no servidor host ou nas máquinas virtuais.**
    
   **Resolução:** é recomendável utilizar as atualizações automatizadas do sistema operacional fornecidas pelo Skype for Business Cloud Connector Edition. Depois que um dispositivo é registrado para o gerenciamento online e a atualização automática do sistema operacional é habilitada, o servidor host e as máquinas virtuais verificarão e instalarão as atualizações do Windows automaticamente de acordo com as configurações da janela de tempo de atualização do sistema operacional.
    
   Se você precisar verificar e instalar as atualizações do Windows manualmente, siga as etapas nesta seção correspondentes ao seu tipo de implantação. Planeje a atualização simultânea do servidor host e das máquinas virtuais executadas nele para minimizar o tempo de inatividade necessário para as atualizações.
    
   Se preferir, é possível usar um servidor do Windows Server Update Services (WSUS) para fornecer atualizações para os servidores do Cloud Connector. Mas certifique-se de configurar o Windows Update para **não** instalar nada automaticamente.
    
   Para obter informações sobre como atualizar manualmente a implantação do Cloud Connector, consulte a seção a seguir.
    
- **Problema: quando o Cloud Connector é atualizado para uma nova compilação, os cmdlets do conector de nuvem não são atualizados.** Às vezes, isso acontece se uma janela do PowerShell é deixada aberta quando ocorre a atualização automática.
    
  **Resolução:** Para carregar os cmdlets atualizados, você pode executar uma das seguintes etapas:
    
   - Feche o PowerShell no aparelho do Cloud Connector e, em seguida, abra novamente o PowerShell.
    
     - Ou então, você pode executar Import-Module CloudConnector-Force. 
 
-   **Problema: "o termo" parar-CsWindowsService "não é reconhecido como o nome de um cmdlet, função, arquivo de script ou programa funcional." erro ao tentar executar o cmdlet Enter-CcUpdate.**

    **Resolução:** Exclua o arquivo \AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache do $HOME.
O PowerShell cria esse arquivo como um cache de cmdlets a partir de módulos que ele encontra para que não precise analisá-los novamente todos os módulos, sempre que isso tornaria as coisas realmente lentas. Provavelmente, houve uma certa corrupção de arquivo que fornecia resultados enganosas ao PowerShell quando ele estava lendo novamente desse cache.

-   **Problema: "Import-Module CloudConnector" gera o erro "Import-Module: o módulo especificado" CloudConnector "não foi carregado porque nenhum arquivo de módulo válido foi encontrado em qualquer diretório de módulo"**

    **Solução:**
    - Valide se o módulo CloudConnector existe em c:\Program Files\WindowsPowerShell\Modules
    
    - Depois de validar que o módulo CloudConnector existe nesse local, a variável de ambiente PSModulePath que armazena o caminho para os locais dos módulos pode ser alterada:
    
     a. Alteração temporária: Inicie o PowerShell como administrador e execute o seguinte comando: $env:P SModulePath = $env:P SModulePath + "; C:\Program Files\WindowsPowerShell\Modules\"
        
     b. Para alteração persistente, inicie o PowerShell como administrador e execute os seguintes comandos, um por um: $CurrentValue = [Environment]:: GetEnvironmentVariable ("PSModulePath", "máquina") SetEnvironmentVariable ("PSModulePath", $CurrentValue + "; C:\Arquivos de Files\WindowsPowerShell\Modules "," computador ")

    
## <a name="install-windows-updates-manually"></a>Instalar atualizações do Windows manualmente

Caso não queira usar atualizações automáticas em seu ambiente, siga estas etapas para verificar e aplicar as atualizações do Windows manualmente. Talvez seja necessário reiniciar o servidor. Quando um servidor host estiver sendo reiniciado, os usuários não poderão usar o conector de nuvem para fazer ou receber chamadas. Você pode verificar e instalar as atualizações manualmente para controlar quando isso é feito e depois reiniciar os computadores conforme necessário, no momento mais conveniente, para evitar a interrupção dos serviços.
  
Para verificar as atualizações manualmente, conecte-se a cada servidor host e abra o **Painel de Controle**. Selecione **sistema e segurança \>Windows Update**e, em seguida, gerencie as atualizações e reinícios do servidor conforme apropriado para o seu ambiente.
  
- Se houver apenas um dispositivo no site, conecte-se a cada máquina virtual e abra o **Painel de Controle**. Selecione **sistema e segurança \>Windows Update**e, em seguida, configure as atualizações e os reinícios do servidor, conforme apropriado.
    
- Se houver mais de um dispositivo no site, os usuários não poderão acessar a instância que está sendo atualizada e reiniciada durante as atualizações. Eles serão conectados a outras instâncias da implantação até que todas as máquinas virtuais e todos os serviços do Skype for Business sejam iniciados nas máquinas virtuais após a conclusão das atualizações. Para evitar possíveis interrupções do serviço, você pode remover a instância da alta disponibilidade enquanto aplica as atualizações e restaurá-la depois da conclusão. Para fazer isso:
    
1. Em cada servidor host, abra um console do PowerShell como administrador.
    
2. Remova a instância da alta disponibilidade usando o seguinte cmdlet:
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    Siga as etapas para uma única instância para aplicar as atualizações e reiniciar a máquina virtual manualmente.
    
4. Defina a instância novamente para alta disponibilidade com o seguinte cmdlet:
    
   ```powershell
   Exit-CcUpdate
   ```

Para implantações de vários sites, siga as etapas referentes a um único site para cada site da implantação, aplicando as atualizações a um site de cada vez.
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a>Dicas ao instalar um software antivírus na máquina host do conector da nuvem

Se você precisar instalar um software antivírus na máquina host do conector de nuvem, será necessário adicionar as seguintes exclusões:
  
- Diretório de dispositivos locais em cada máquina.
    
- Diretório de sites remotos em cada máquina.
    
- Diretório de sites local no computador hospeda a pasta raiz do site compartilhado.
    
- %ProgramFiles%\Skype for Business Cloud Connector Edition
    
- %ALLUSERSPROFILE%\CloudConnector
    
- %ProgramFiles%\WindowsPowerShell\Modules\CloudConnector
    
- O processo Microsoft. RTC. CCE. ManagementService. exe.
