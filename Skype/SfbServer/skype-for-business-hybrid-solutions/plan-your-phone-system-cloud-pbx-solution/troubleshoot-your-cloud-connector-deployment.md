---
title: Solução de problemas de implantação do Cloud Connector
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/5/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: Solucionar problemas de sua implantação de edição do conector de nuvem.
ms.openlocfilehash: 2290d032f1461c37c31d138510388f17a52f5843
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/29/2018
ms.locfileid: "25838618"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a>Solução de problemas de implantação do Cloud Connector
 
Solucionar problemas de sua implantação de edição do conector de nuvem.
  
Este tópico descreve soluções para problemas comuns em implantações do Cloud Connector Edition. Se você está tendo problemas com chamadas de entrada e saída PSTN (Rede Telefônica Pública Comutada), poderá investigar seguindo as soluções descritas neste tópico.
  
Conector de nuvem fornece mecanismos internos para automaticamente resolver alguns problemas. Um processo de detecção automática procura possíveis problemas com os dispositivos do conector de nuvem e, se possível, adota ações corretivas para resolver esses problemas, sem a necessidade de intervenção do administrador. O processo de detecção funciona da seguinte maneira:
  
- **Sequência de detecção:** O serviço de gerenciamento de conector de nuvem executa um processo a cada 60 segundos para detectar se um dispositivo está inoperante. No conector de nuvem versão 2.0 e posteriores, o processo de detecção usa o Skype para negócios Corpnet mudança para tomar as conexões do PowerShell para as máquinas do conector de nuvem; para versões anteriores ao 2.0, o processo de detecção usa a opção de gerenciamento de conector de nuvem.
    
    > [!NOTE]
    > Recuperação automática para o sucesso, deve haver conectividade de rede entre o host e máquinas virtuais sobre o comutador de rede do host. Certifique-se de verificar a conectividade de rede para garantir a detecção automática e recuperação funcionem. 
  
- **Monitoring:** Os seguintes serviços são monitorados no conector de nuvem versão 2.0 e posteriores:
    
  - Máquinas virtuais não estão conectadas à nuvem conector corporativo ou switches virtuais da Internet
    
  - Máquinas virtuais são em um status salvo ou parado
    
  - Serviços de servidor de gerenciamento central: réplica, mestre
    
  - Serviços de servidor de mediação: réplica, RTCSRV e MEDSVC
    
  - Serviços de servidor de borda: réplica, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY
    
  - As regras são desabilitadas para CS RTCSRV no servidor de borda, CS RTCMEDSRV no servidor de mediação de firewall de entrada
    
    No conector de nuvem versão 1.4.2, somente os seguintes serviços são monitorados:
    
  - Serviços de servidor de mediação: RTCSRV e MEDSVC
    
  - Serviço do servidor de borda: RTCSRV
    
- **Processo de recuperação:** Se todos os serviços monitorados estão desativados, um aparelho é marcado para baixo e serviços foram interrompidos e marcados manuais até que todos os problemas que podem ser resolvidos. Isto evitará chamadas do roteamento em um dispositivo que pode causar falhas de chamada.
    
    O serviço de gerenciamento de conector de nuvem repetirá a recuperação automática da seguinte maneira
    
  - O intervalo de repetição inicial é a cada dez segundos com um tempo de intervalo máximo de uma hora.
    
  - Para as tentativas de três primeiros recuperação, o intervalo de tempo é de 10 segundos. O intervalo de tempo a partir do quarto repetir, aumenta em duas vezes o anterior intervalo de tempo. Por exemplo, o quarto repetir ocorrerá em 20 segundos, o quinto em 40 segundos e assim por diante. 
    
  - Quando é atingido o tempo de intervalo máximo de uma hora, tentativas continuarão uma vez por hora.
    
  - Quando a recuperação for bem-sucedida, as contagens de intervalo e repetição são definidas com seus valores iniciais.
    
  - Se o serviço de gerenciamento for reiniciado, as contagens de intervalo e repetição são redefinidas para seus valores iniciais.
    
## <a name="troubleshooting"></a>Solução de problemas

Estes são soluções para problemas comuns encontrados:
  
- **Problema: a implantação falha ou para de responder durante a execução dos scripts de implantação. Depois de fazer logon em cada VM, o endereço IP está ausente ou está incorreto para a NIC de Gerenciamento/Interna/Externa.**
    
    **Resolução:** Esse problema não pode ser resolvido automaticamente. Desligue e remova essas VMs no Gerenciador do Hyper-V. Depois, execute estes cmdlets:
    
  ```
  Uninstall-CcAppliance
  ```

  ```
  Install-CcAppliance
  ```

- 
    
    **Problema: após a instalação do Servidor do Active Directory e da floresta, o Servidor CMS e/ou o Servidor de Mediação não ingressou(aram) corretamente no domínio.**
    
    **Resolução:** para resolver esse problema, faça o seguinte:
    
  - Faça logon no Servidor do Active Directory e verifique se o domínio foi criado corretamente.
    
  - Faça logon no servidor CMS/Servidor de Mediação e verifique se foi atribuído um endereço IP válido à NIC da rede corporativa e se um DNS e um IP estático válidos foram configurados como endereço IP do servidor do AD.
    
  - Faça logon no servidor de mediação de CMS/e abra um prompt de comando. Verifique se é possível executar ping no FQDN e no endereço IP do Servidor do Active Directory. Se não o for, talvez haja um conflito de endereço IP. Tente atribuir um novo IP ao Active Directory e atualize apropriadamente o DNS no Servidor CMS/Servidor de Mediação.
    
- **Problema: Você recebe a seguinte mensagem de erro "Remove-VMSwitch: Falha ao remover o comutador virtual de Ethernet. Comutador virtual 'Nuvem conector gerenciamento alternar' não pode ser excluído, pois ele está sendo usado por máquinas virtuais em execução ou atribuído a pools filho."**
    
    **Resolução:** A "nuvem conector gerenciamento opção" não foi excluída após a implantação. Se você entrar com esse erro, vá para o Gerenciador Hyper-v e verifique se há ainda não uma máquina virtual que ainda está conectada a ela. Se houver máquinas virtuais ainda conectadas, desconecte-los e exclua a opção de gerenciamento. Se a opção de gerenciamento ainda não pode ser excluída, reinicie o servidor de host e tente novamente.
    
- **Problema: Você recebe a seguinte mensagem de erro, "serviço RTCMRAUTH falhou ao iniciar. Verifique se que o serviço não está desabilitado."**
    
    > [!NOTE]
    > Esse problema só se aplica às versões de conector de nuvem anteriores a 1.4.2. 
  
    A falha de inicialização também pode ocorrer porque já foi feito failover desse Servidor Front-End (usando o failover do computador). Se for o caso, invoque o failback (usando o failback do computador).
    
    **Resolução:** esse problema acontece no Servidor de Borda quando o Certificado de Autoridade de Certificação raiz ou o Certificado de Autoridade de Certificação intermediário não é confiável para o Servidor de Borda. Mesmo que o certificado externo possa ser importado, a cadeia de certificados está desfeita. Nessa situação, não é possível iniciar o serviço RTCMRAUTH e/ou RTCSRV.
    
    Importe manualmente o Certificado de Autoridade de Certificação raiz e todos os Certificados de Autoridade de Certificação intermediários de seu certificado externo para o Servidor de Borda e reinicie o Servidor de Borda. Depois que os serviços RTCMRAUTH e RTCSRV forem iniciados no Servidor de Borda, volte ao servidor host, inicie um console do PowerShell como administrador e execute o seguinte cmdlet para alternar para a nova implantação:
    
  ```
  Switch-CcVersion
  ```

- 
    
    **Problema: o servidor host foi reiniciado durante a aplicação de atualizações do Windows e ocorrem falhas nas chamadas atendidas pelo servidor.**
    
    **Resolução:** se você tiver implantado um ambiente de alta disponibilidade, a Microsoft fornece um cmdlet para ajudar a transferir um computador host (instância de implantação) para dentro ou para fora da topologia atual durante a verificação e a instalação manual da atualização do Windows. Para fazer isso, execute estas etapas:
    
1. No servidor host, inicie um console do PowerShell como administrador e execute:
    
   ```
   Enter-CcUpdate
   ```

2. Verifique se há atualizações e instale as que estiverem disponíveis.
    
3. No console do PowerShell, execute o seguinte cmdlet:
    
   ```
   Exit-CcUpdate
   ```

- 
    
    **Problema: quando é feita uma chamada do Cliente Skype for Business usando um número PSTN, não é possível escalonar a chamada para uma conferência por meio de um convite a outro número PSTN.**
    
    **Resolução:** Para resolver esse problema, consulte [hybrid online de configurar as configurações do servidor de mediação](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).
    
- **Problema: durante a instalação do servidor do Active Directory, é exibida esta mensagem de aviso sobre o Windows Update: "A atualização automática do Windows não está habilitada. Para verificar se a função ou o recurso recém-instalado é atualizado automaticamente, ative o Windows Update."**
    
    **Resolução:** Iniciar uma sessão do PowerShell remoto do inquilino usando Skype para credenciais de administrador de locatário de negócios, e em seguida, execute o seguinte cmdlet para verificar a configuração de _EnableAutoUpdate_ do seu site:
    
  ```
  Get-CsHybridPSTNSite
  ```

    Se _EnableAutoUpdate_ estiver definida como **True**, você pode ignorar com segurança essa mensagem de aviso, porque o serviço CCEManagement manipulará baixando e instalando atualizações do Windows para máquinas virtuais e o servidor host. Se _EnableAutoUpdate_ estiver definida como **False**, execute o seguinte cmdlet para defini-la como **True**.
    
  ```
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    Como opção, você pode verificar e instalar as atualizações manualmente. Consulte a próxima seção.
    
- **Problema: Você recebe uma mensagem de erro: não é possível registrar appliance porque sua configuração atual de entrada/ \<SiteName\> ou \<ApplianceName\> ou \<FQDN do servidor de mediação\> ou \<endereço de IP do servidor de mediação \> está em conflito com appliance(s) existente. Remover o aparelho de conflito ou atualizar suas informações de entrada/configuração e registre novamente. ' Register-CcAppliance para registrar o aparelho atual para online quando é executado.**
    
    **Resolução:** Valores para o \<ApplianceName\>, \<FQDN do servidor de mediação\> e \<endereço de IP do servidor de mediação\> deve ser exclusivo e somente ela usados para o registro de um dos dispositivos. Por padrão, \<ApplianceName\> proveniente o nome do host. \<FQDN do servidor de mediação\> e \<endereço de IP do servidor de mediação\> definida no arquivo ini de configuração.
    
    Por exemplo, ao usar (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) para se registrar em SiteName=MySite, se houver um dispositivo registrado (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), haverá um conflito.
    
    Primeiro, verifique o arquivo CloudConnector.ini na seção do diretório ApplianceRoot. Você receberá \<SiteName\>, \<FQDN do servidor de mediação\> e \<endereço de IP do servidor de mediação\> valores no arquivo. \<ApplianceName\> é o nome do seu servidor de host.
    
    Em segundo lugar, início locatário PowerShell remoto usando seu Skype para credenciais de administrador de locatário de negócios, em seguida, execute o seguinte cmdlet para verificar a appliance(s) registrados.
    
  ```
  Get-CsHybridPSTNAppliance
  ```

    Depois de identificar os conflitos, você poderá atualizar o arquivo CloudConnector.ini com informações compatíveis com o dispositivo registrado ou cancelar o registro do dispositivo existente para resolver os conflitos.
    
  ```
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- **Problema: O cmdlet Get-CcRunningVersion retorna um valor vazio se não houver um aparelho implantado em execução no host.**
    
  **Resolução:** isso pode acontecer quando você atualiza da versão 1.3.4 ou 1.3.8 para a versão 1.4.1. Depois de instalar a verão 1.4.1 com o .msi, é necessário executar `Register-CcAppliance` antes de executar qualquer outro cmdlet. `Register-CcAppliance` fará a migração do arquivo module.ini de %UserProfile%\CloudConnector para %ProgramData%\CloudConnector. Se ele tiver sido perdido, um novo module.ini será criado na pasta %ProgramData%\CloudConnector, substituindo as informações da versão em execução/de backup para 1.3.4 ou 1.3.8.
    
  Compare os arquivos module.ini das pastas %UserProfile%\CloudConnector e %ProgramData%\CloudConnector. Se houver diferenças, exclua o arquivo de module.ini em %ProgramData%\CloudConnector e novamente `Register-CcAppliance`. Você também pode modificar o arquivo manualmente para a execução correta e a versão de backup.
    
- **Problema: Após executar o cmdlet CcVersion a opção para alternar para uma versão antiga que é diferente da versão atual do script, há não há suporte de alta disponibilidade para essa versão antiga.**
    
    **Resolução:** Por exemplo, você tiver atualizado de 1.4.1 1.4.2. Sua versão atual do script, que pode ser determinado executando `Get-CcVersion`e a sua versão em execução, que pode ser determinado executando `Get-CcRunningVersion` são ambos 1.4.2. Neste momento, se você executar `Switch-CcVersion` para a versão em execução voltar para 1.4.1, em seguida, não haverá nenhum suporte à alta disponibilidade para esta versão antiga.
    
    Para ter suporte completo para Alta Disponibilidade, alterne novamente para a versão 1.4.2. Assim, a versão em execução e a versão do script serão iguais. Se houver problemas com a implantação da versão 1.4.2, desinstale-a e instale-a novamente assim que possível.
    
- **Problema: os certificados da autoridade de certificação ou os certificados internos emitidos para o Repositório de Gerenciamento Central, o Servidor de Mediação e o Servidor de Borda estão prestes a expirar ou estão comprometidos.**
    
    **Resolução:** os certificados da autoridade de certificação do Skype for Business são válidos por cinco anos. Os certificados internos emitidos para o Repositório de Gerenciamento Central, o Servidor de Mediação e o Servidor de Borda são válidos por dois anos.
    
    > [!NOTE]
    > No conector de nuvem versão 2.0 e posteriores, o cmdlet renovar-CcServerCertificate foi alterado para CcServerCertificate de atualização e o cmdlet renovar-CcCACertificate foi alterado para CcCACertificate de atualização. 
  
    Se os certificados internos emitidos para o repositório de gerenciamento Central, o servidor de mediação e o servidor de borda estão prestes a expirar ou comprometida, executem o CcServerCertificate de renovação ou o cmdlet Update-CcServerCertificate para renovar seus certificados.
    
    Se os certificados de autoridade de certificação estão próximo a expiração, execute o cmdlet renovar-CcCACertificate ou CcCACertificate de atualização para renovar seus certificados.
    
    **Se os certificados de autoridade de certificação estão comprometidos e se houver apenas um appliance no site,** execute as seguintes etapas:
    
1. Execute o cmdlet Enter-CcUpdate para esvaziar os serviços e colocar o dispositivo no modo de manutenção.
    
2. Execute os seguintes cmdlets para redefinir e criar novos certificados da autoridade de certificação e todos os certificados de servidor interno:
    
    Para versões do conector de nuvem antes 2.0:
    
    ```
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    Ou para a versão do conector de nuvem 2.0 e posterior:
    
    ```
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

3. Execute o cmdlet sair-CcUpdate para iniciar os serviços e sair do modo de manutenção.
    
4. Execute o cmdlet Export-CcRootCertificate no arquivo local no dispositivo e depois copie e instale o certificado exportado para seus gateways PSTN.
    
    **Se os certificados de autoridade de certificação estão comprometidos e há vários appliances no site,** execute as seguintes etapas de sequenciais em cada dispositivo no site.
    
    A Microsoft recomenda que você execute essas etapas durante os períodos de uso não sejam de pico.
    
   - No primeiro appliance, execute o cmdlet Remove-CcCertificationAuthorityFile para a autoridade de certificação de limpeza fazer backup de arquivos no \<SiteRoot\> directory.
    
   - Execute o cmdlet Enter-CcUpdate para esvaziar serviços e coloque cada aparelho no modo de manutenção.
    
   - Execute os seguintes cmdlets para redefinir e criar novos certificados da autoridade de certificação e todos os certificados de servidor interno:
    
     Para versões do conector de nuvem antes 2.0:
    
     ```
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     Ou para a versão do conector de nuvem 2.0 e posterior:
    
     ```
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

   - No primeiro appliance, execute o seguinte cmdlet para fazer backup dos arquivos de autoridade de certificação para o \<SiteRoot\> pasta. Posteriormente, em todos os outros dispositivos no mesmo site, o cmdlet Reset-CcCACertificate consumirá automaticamente os arquivos de backup de autoridade de certificação e appliances usará o mesmo certificado raiz.
    
     ```
     Backup-CcCertificationAuthority
     ```

   - Execute o cmdlet sair-CcUpdate para iniciar os serviços e sair do modo de manutenção. 
    
   - Se o TLS é usado entre o gateway e o servidor de mediação, executar o cmdlet Export-CcRootCertificate a partir de qualquer aparelho no site e, em seguida, instale o certificado exportado seus gateways PSTN. 
    
- **Problema: Você recebe a seguinte mensagem de erro no Log de serviço de gerenciamento de conector nuvem "C:\Program Files\Skype para negócios nuvem conector Edition\ManagementService\CceManagementService.log": erro CceService: 0: exceção inesperada quando relatórios de status online: System.Management.Automation.CmdletInvocationException: falha de Logon para o usuário \<Administrador Global do locatário\>. Crie um novo objeto de credencial, certificando-se de que você usou o nome correto do usuário e a senha. ---\>**
    
    **Resolução:** As credenciais de administrador de locatário global do Office 365 foram alteradas desde que o aparelho de nuvem conector foi registrado. Para atualizar as credenciais armazenadas localmente no dispositivo do conector de nuvem, execute o seguinte do PowerShell do administrador no dispositivo do host:
    
  ```
  Set-CcCredential -AccountType TenantAdmin
  ```

- **Problema: Depois de alterar a senha para a conta do servidor de host usado para a implantação, você recebe a seguinte mensagem de erro: "ConvertTo-SecureString: especificado da chave não é válido para uso no estado." na %ProgramFiles%\Skype para o Business Connector de nuvem Edition\ManagementService\CceManagementService.log ou enquanto executa o cmdlet Get-CcCredential.**
    
    **Resolução:** Todas as credenciais do conector de nuvem são armazenadas no seguinte arquivo: "% SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ". Quando for alterada a senha do servidor host, você precisará atualizar as credenciais armazenadas localmente.
    
    **Se você estiver executando a versão 1.4.2 do Cloud Connector,** regenere todas as senhas do Cloud Connector seguindo estas etapas:
    
  1. Reinicie o servidor host.
    
  2. Exclua o arquivo a seguir: "% SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ".
    
  3. Iniciar um console do PowerShell como administrador e execute "Register-CcAppliance-Local" digitem novamente as senhas seguindo a descrição. Insira as mesmas senhas que você inseriu anteriormente para a implantação do Cloud Connector.
    
     **Se você estiver executando o conector de nuvem versão 2.0 ou posterior,** regenerar todas as senhas de conector de nuvem, seguindo estas etapas:
    
  4. Reinicie o servidor host.
    
  5. Exclua o arquivo a seguir: "% SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ".
    
  6. Iniciar um console do PowerShell como administrador e execute "Register-CcAppliance-Local" digitem novamente as senhas seguindo a descrição. 
    
     Se o arquivo de senha em cache foi gerado com a versão 1.4.2 do Cloud Connector, use a senha do VMAdmin como a senha do CceService quando ela for solicitada. Insira a mesma senha que você inseriu anteriormente para a implantação do Cloud Connector para todas as outras contas.
    
     Se o arquivo de senha em cache foi gerado com a versão 1.4.2 do Cloud Connector e as senhas de DomainAdmin e VMAdmin forem diferentes, você deverá executar as seguintes etapas:
    
  7. Execute Set-CcCredential -AccountType DomainAdmin da seguinte maneira:
    
  8. Quando solicitada a antiga credencial da conta, insira a credencial que você usou para a senha do CceService.
    
  9. Quando for solicitada a nova credencial da conta, insira a senha do DomainAdmin usada anteriormente.
    
     Se o arquivo de senha armazenada em cache foi gerado com o conector de nuvem versão 2.0 ou posterior, por padrão, VmAdmin e DomainAdmin usam a mesma senha como CceService. Se você tiver alterado as senhas do DomainAdmin e VMAdmin, deverá executar as seguintes etapas:
    
  10. Execute Set-CcCredential -AccountType DomainAdmin da seguinte maneira:
    
       1. Quando solicitada a antiga credencial da conta, insira a credencial que você usou para a senha do CceService
    
       2. Quando for solicitada a nova credencial da conta, insira a senha do DomainAdmin usada anteriormente.
    
  11. Execute Set-CcCredential -AccountType VmAdmin da seguinte maneira:
    
       1. Quando solicitada a antiga credencial da conta, insira a credencial que você usou para a senha do CceService
    
       2. Quando for solicitada a nova credencial da conta, insira a senha do VmAdmin usada anteriormente.  
    
- **Problema: Com o conector de nuvem versão 2.1 e posterior, quando executado Register-CcAppliance ou outros cmdlets no dispositivo, você recebe uma mensagem de erro, como: "For Each-Object: A propriedade 'Comum' não pode ser localizado neste objeto. Verifique se a propriedade existe. Em C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char: 14 "**
    
    **Resolução:** Conector 2.1 em nuvem e posteriormente requer o .NET Framework 4.6.1 ou posterior. Atualize o .NET Framework no dispositivo para a versão 4.6.1 ou posterior e execute o cmdlet(s) novamente.

- **Problema: Com a nuvem conector Edition 2.1, ao se executar Install-CcAppliance, você recebe uma mensagem de erro, como: "Falha ao instalar a nova instância com erro: não é possível definir o"Estado", porque apenas cadeias de caracteres podem ser usadas como valores para definir propriedades de XmlNode"**

   **Resolução:** Em Cloudconnector.ini, na seção [comuns], adicione o config "Estado" como a seguir: CountryCode = US State = WA cidade = Redmond

   Não é obrigatório para a linha "Estado" ter valor, no entanto, a linha "Estado" não pode ser removida do arquivo Cloudconnector.ini exe.

- **Problema: Você recebe a seguinte mensagem de erro "Dismount-WindowsImage: Dismount-WindowsImage falhou. Código de erro = 0xc1550115 "ao instalar ou atualizar a edição do conector de nuvem.**
    
    **Resolução:** Inicie um console do PowerShell como administrador, execute "DISM-limpeza-Wim'". Isso limpará todas as imagens problemáticas. Execute Install-CcAppliance novamente ou aguarde a atualização automática dos bits.
    
- **Problema: Falha de implantação do aparelho de conector de nuvem primeiro em um ambiente de alta disponibilidade**
    
    **Resolução:** As etapas executadas dependem do motivo pelo qual a implantação falhou:
    
  - Se o primeiro appliance de nuvem conector falha e você não consegue determinar o motivo da falha, instale o aparelho novamente até que a implantação for bem-sucedido e, em seguida, instale os outros dispositivos.
    
  - Se o primeiro appliance de nuvem conector falhar com um problema secundário, como um problema de certificado externo, você poderá corrigir o problema sem instalar novamente o aparelho. Você pode usar o PowerShell remoto para marcar a implantação como bem-sucedida da seguinte maneira de inquilinos. (Você pode também usar as etapas a seguir se a primeira implantação foi bem-sucedida, mas, por algum motivo, o conector de nuvem falhar relatar a implantação como um sucesso.)
    
  - Para obter a identidade (GUID) do primeiro aparelho de conector de nuvem, execute o cmdlet Get-CsHybridPSTNAppliance.
    
  - Para marcar o aparelho implantado como com êxito, execute o Set-CsCceApplianceDeploymentStatus da seguinte maneira:
    
  ```
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- **Problemas: você precisa verificar e instalar as atualizações do Windows manualmente no servidor host ou nas máquinas virtuais.**
    
   **Resolução:** é recomendável utilizar as atualizações automatizadas do sistema operacional fornecidas pelo Skype for Business Cloud Connector Edition. Depois que um dispositivo é registrado para o gerenciamento online e a atualização automática do sistema operacional é habilitada, o servidor host e as máquinas virtuais verificarão e instalarão as atualizações do Windows automaticamente de acordo com as configurações da janela de tempo de atualização do sistema operacional.
    
   Se você precisar verificar e instalar as atualizações do Windows manualmente, siga as etapas nesta seção correspondentes ao seu tipo de implantação. Planeje a atualização simultânea do servidor host e das máquinas virtuais executadas nele para minimizar o tempo de inatividade necessário para as atualizações.
    
   Se preferir, é possível usar um servidor do Windows Server Update Services (WSUS) para fornecer atualizações para os servidores do Cloud Connector. Mas certifique-se de configurar o Windows Update para **não** instalar nada automaticamente.
    
   Para obter informações sobre como atualizar manualmente a implantação do Cloud Connector, consulte a seção a seguir.
    
- **Problema: Quando o conector de nuvem atualiza para uma nova compilação, cmdlets de conector de nuvem não serão atualizados.** Às vezes, isso acontecerá se uma janela do PowerShell permanecerá aberta quando ocorre a atualização automática.
    
  **Resolução:** Para carregar os cmdlets atualizados, você pode fazer uma das seguintes etapas:
    
   - Feche o PowerShell no dispositivo do conector de nuvem e reabra PowerShell.
    
     - Ou, você pode executar Import-Module CloudConnector-Force. 
 
-   **Problema: "o termo 'Stop-CsWindowsService' não é reconhecido como o nome de um cmdlet, função, arquivo de script ou programa operável." Erro ao tentar executar o cmdlet CcUpdate de Enter.**

    **Resolução:** Exclua o arquivo de HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache $.
PowerShell cria esse arquivo como um cache de cmdlets de módulos encontrados para que ele não precisa analisar novamente todos os módulos de cada vez como que tornaria coisas realmente lento. Provavelmente, houve alguns corrupção de arquivo que forneceu resultados incorretos ao PowerShell quando ele estava lendo volta de nesse cache.

-   **Problema: "Import-Module CloudConnector" gerará o erro "Import-Module: O módulo especificado"CloudConnector"não foi carregado, porque nenhum arquivo de módulo válido foi encontrado em qualquer diretório módulo"**

    **Solução:**
    - Validar se realmente o módulo CloudConnector existe em c:\Program Files\WindowsPowerShell\Modules
    
    - Após validar esse módulo CloudConnector existe sob este local, a variável de ambiente PSModulePath armazenar o caminho para os locais dos módulos pode ser alterada:
    
     a. Alteração temporária: iniciar o Powershell como administrador e execute o seguinte comando: $env: PSModulePath = $env: PSModulePath + "; C:\Program Files\WindowsPowerShell\Modules\"
        
     b. Para alterar persistente, inicie o PowerShell como administrador e executar os seguintes comandos, um por um: $CurrentValue = [ambiente]:: GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules","Computador")

    
## <a name="install-windows-updates-manually"></a>Instalar atualizações do Windows manualmente

Caso não queira usar atualizações automáticas em seu ambiente, siga estas etapas para verificar e aplicar as atualizações do Windows manualmente. Talvez seja necessário reiniciar o servidor. Quando um servidor host está reiniciando, os usuários não poderão usar o conector de nuvem para fazer ou receber chamadas. Você pode verificar e instalar as atualizações manualmente para controlar quando isso é feito e depois reiniciar os computadores conforme necessário, no momento mais conveniente, para evitar a interrupção dos serviços.
  
Para verificar as atualizações manualmente, conecte-se a cada servidor host e abra o **Painel de Controle**. Selecione **sistema e segurança \>Windows Update**e, em seguida, gerenciar as atualizações e o servidor for reiniciado conforme apropriado para seu ambiente.
  
- Se houver apenas um dispositivo no site, conecte-se a cada máquina virtual e abra o **Painel de Controle**. Selecione **sistema e segurança \>Windows Update**e, em seguida, configure as atualizações e o servidor for reiniciado conforme apropriado.
    
- Se houver mais de um dispositivo no site, os usuários não poderão acessar a instância que está sendo atualizada e reiniciada durante as atualizações. Eles serão conectados a outras instâncias da implantação até que todas as máquinas virtuais e todos os serviços do Skype for Business sejam iniciados nas máquinas virtuais após a conclusão das atualizações. Para evitar possíveis interrupções do serviço, você pode remover a instância da alta disponibilidade enquanto aplica as atualizações e restaurá-la depois da conclusão. Para fazer isso:
    
1. Em cada servidor host, abra um console do PowerShell como administrador.
    
2. Remova a instância da alta disponibilidade usando o seguinte cmdlet:
    
   ```
   Enter-CcUpdate
   ```

3. 
    
    Siga as etapas para uma única instância para aplicar as atualizações e reiniciar a máquina virtual manualmente.
    
4. Defina a instância novamente para alta disponibilidade com o seguinte cmdlet:
    
   ```
   Exit-CcUpdate
   ```

Para implantações de vários sites, siga as etapas referentes a um único site para cada site da implantação, aplicando as atualizações a um site de cada vez.
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a>Dicas ao instalar o software antivírus na máquina host conector de nuvem

Se você precisa instalar o software antivírus na máquina host conector de nuvem, você precisa adicionar as exclusões a seguintes:
  
- Diretório de aparelho de local em cada máquina.
    
- Diretório de Site remoto em cada máquina.
    
- Diretório de Site local na máquina hospeda a pasta raiz do site compartilhado.
    
- %ProgramFiles%\Skype para o conector de nuvem Business Edition
    
- %ALLUSERSPROFILE%\CloudConnector
    
- %ProgramFiles%\WindowsPowerShell\Modules\CloudConnector
    
- O processo Microsoft.Rtc.CCE.ManagementService.exe.
