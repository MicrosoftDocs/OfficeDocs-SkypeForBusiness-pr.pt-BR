---
title: Mover os usuários do Skype para Business Online no local
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/19/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 55733bb5-6742-4daf-8db5-1c5df86f4cea
description: 'Resumo: Saiba como mover as contas de usuário de online para no local no Skype para Business Server.'
ms.openlocfilehash: 77ef2ad5cf22632d3f81f35fc0c3a20054303e96
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23884528"
---
# <a name="move-users-from-skype-for-business-online-to-on-premises"></a>Mover os usuários do Skype para Business Online no local

**Resumo:** Aprenda a mover as contas de usuário de online para no local no Skype para Business Server.

Você pode precisar mover as contas de usuário de online para no local para garantir que os usuários hospedagem online e no local são detectáveis uns aos outros. Para ser descoberto uns aos outros, todos os usuários devem ter uma presença no Active Directory local. Para obter mais informações, consulte [Planejar a conectividade híbrida entre Skype para Business Server e do Skype para negócios Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md). Talvez você queira mover usuários online no local, por exemplo, se:

- Você tem a novos usuários que precisam ser criadas no local e depois movido para a nuvem.

- Sua organização implantou o Skype para Business Online antes que ele implantado Skype para Business Server. Portanto, você tiver usuários que foram criados pela primeira vez na nuvem e agora precisa ser movido para no local antes de serem: mover para Skype para negócios Online.

Este tópico descreve os dois cenários:

- [Mover usuários online — que estavam originalmente online — como local](move-users-from-skype-for-business-online-to-on-premises.md#BKMK_originallyonline)

- [Mover usuários on-line (que estavam originalmente no local) no local](move-users-from-skype-for-business-online-to-on-premises.md#BKMK_originallyonprem)

## <a name="move-online-userswho-were-originally-onlineto-on-premises"></a>Mover usuários online — que estavam originalmente online — como local
<a name="BKMK_originallyonline"> </a>

Esta seção se aplica somente aos usuários que foram criados e habilitados online, mas que não têm uma conta do local no Active Directory.

Antes de iniciar a migração dos usuários online para seu ambiente local, verifique se as opções a seguir são todas verdadeiras:

- Seu ambiente local deve estar completamente implantado e validado. Para obter mais informações, consulte [Deploying Lync Server 2013](https://technet.microsoft.com/library/b76795a4-4e71-4c70-a5c0-d1197fa8028c.aspx) ou [Implantar Skype para Business Server 2015](../../deploy/deploy.md), dependendo da versão que você esteja usando no local.

- Seu locatário online deve ser configurado para acesso remoto do PowerShell.

    Para fazer isso, primeiro instale o Skype para o módulo de conector Business Online para o Windows PowerShell, que você pode obter aqui: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911).

    Após instalar o módulo, você pode estabelecer uma sessão remota digitando os seguintes cmdlets no Skype do Shell de gerenciamento do servidor de negócios:

  ```
  Import-Module SkypeOnlineConnector
  ```

  ```
  $cred = Get-Credential
  ```

  ```
  $CSSession = New-CsOnlineSession -Credential $cred
  ```

  ```
  Import-PSSession $CSSession -AllowClobber
  ```

    Para obter mais informações sobre como usar o PowerShell com Skype para Business Online, consulte [Configurar o computador para o Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

- Seu locatário online deve ser configurado para um espaço de endereçamento SIP compartilhado. Para fazer isso, primeiro inicie uma sessão Powershell remota com Skype para negócios Online. Em seguida, execute este cmdlet:

  ```
  Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
  ```

    > [!NOTE]
    > As necessidades de atributo SharedSipAddressSpace permaneça "True", até que a mudança para online é final e nenhum usuário permanecerão no local.

Depois que terminar estas etapas, você pode migrar contas de usuário, conforme descrito no procedimento a seguir:

### <a name="move-user-accounts-originally-enabled-online-to-an-on-premises-deployment"></a>Mover as contas de usuário habilitadas originalmente online em uma implantação local

1. Primeiro, certifique-se de que sua organização está configurada para implantação híbrida, incluindo ferramentas de conexão do Azure Active Directory e de sincronização. Para obter mais informações, consulte [Planejar a conectividade híbrida entre Skype para Business Server e do Skype para negócios Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).

  - Na sua implantação no local, no Skype do Shell de gerenciamento do servidor de negócios, digite os seguintes cmdlets para criar o provedor de hospedagem para Skype para Business Online. Você pode usar o valor que desejar para os parâmetros Identity e Name.

  ```
  Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
  ```

  ```
  New-CsHostingProvider -Identity SkypeforBusinessOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
  ```

2. Confirme se em seus servidores de borda de local, você tem a cadeia de certificados que permite a conexão para Skype para negócios Online, conforme mostrado na tabela a seguir. Você pode baixar essa cadeia aqui: [https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip](https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip).

|**Certificado**|**Repositório de Certificado**|
|:-----|:-----|
|Raiz do Baltimore CyberTrust  <br/> |AC Raiz Confiável  <br/> |
|Microsoft Internet Authority (novo certificado CA)  <br/> |CA intermediário  <br/> |
|MSIT Machine Auth CA2 (nova emissão de CA2)  <br/> |CA intermediário  <br/> |

3. Em seu local no Active Directory, habilite as contas de usuário afetado para Skype para negócios 2015 de servidor no local. Essa ação é possível para usuários individuais digitando o cmdlet a seguir:

  ```
  Enable-CsUser
-Identity "username "
-SipAddress "sip: username @contoso.com"
-HostingProviderProxyFqdn "sipfed.online.lync.com"
  ```

    Você também pode criar um script que lê os nomes de usuário a partir de um arquivo e os oferece como input ao cmdlet Enable-CsUser:

  ```
  Enable-CsUser
-Identity $Identity
-SipAddress $SipAddress
-HostingProviderProxyFqdn "sipfed.online.lync.com"
  ```

4. Sincronize os usuários online com os usuários atualizados no local. Para obter mais informações, consulte [Ferramentas de integração de diretório](https://go.microsoft.com/fwlink/p/?LinkId=530320).

5. Atualize os seguintes registros DNS para direcionar todo o tráfego SIP para sua implantação no local:

  - Atualize o **lyncdiscover.contoso.com** Um registro para apontar ao FQDN do servidor de proxy reverso do local.

  - Atualização do ** *SIP* . _tls.contoso.com** registro SRV para resolver para o endereço IP ou o VIP público do serviço de borda de acesso do Lync local.

  - Atualização do ** *sipfederationtls* . _tcp.contoso.com** registro SRV para resolver para o endereço IP ou o VIP público do serviço de borda de acesso do Skype para Business Server 2015 local.

  - Se sua organização utiliza dividido (às vezes chamado de "Split-Brain DNS") de DNS, certifique-se de que os usuários a resolução de nomes por meio da zona DNS interno são direcionados para o Pool Front-End.

6. Tipo de `Get-CsUser` cmdlet para verificar algumas propriedades sobre os usuários que estiver movendo. Certifique-se de que o HostingProviderProxyFQDN esteja definido como `"sipfed.online.lync.com"` e que os endereços SIP estejam definidos corretamente.

7. Mova usuários online no local.

    Para mover um único usuário, digite:

  ```
  $cred = Get-Credential
  Move-CsUser -Identity <username>@contoso.com  -Target "<fe-pool>.contoso.com " -Credential $cred -HostedMigrationOverrideURL <URL>
  ```

    Você pode mover vários usuários usando o cmdlet **Get-CsUSer** com o parâmetro - Filter para selecionar os usuários com uma propriedade específica. Por exemplo, você pode selecionar todos os usuários Online pela filtragem de {provedor de hospedagem - eq "sipfed.online.lync.om"}. Em seguida, você pode direcionar os usuários retornados para o cmdlet **Move-CsUSer** , conforme mostrado abaixo.

  ```
  Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com " -Credential $creds -HostedMigrationOverrideURL <URL>
  ```

    O formato da URL especificado para o parâmetro **HostedMigrationOverrideUrl** deve ser a URL para o pool de onde o serviço de migração hospedado estiver em execução, no seguinte formato: _Https://\<FQDN do Pool\>/HostedMigration/ hostedmigrationService.svc_.

    Você pode identificar a URL do serviço de migração hospedado visualizando a URL do Painel de Controle do Lync Online da sua conta de locatário do Office 365.

### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a>Para identificar a URL do Serviço de Migração Hospedada do seu locatário do Office 365

1. Faça logon no seu inquilino do Office 365 como um administrador.

2. Abra o **Centro de administração do Skype for Business**.

3. Com o **Centro de administração do Skype for Business** exibido, selecione e copie a URL na barra de endereço no **lync.com**. Uma URL de exemplo seria parecida com esta:

     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`

4. Substitua **webdir** na URL por **admin**, o que resulta no seguinte:

     `https://admin0a.online.lync.com`

5. Anexe a cadeia de caracteres a seguir à URL: **/HostedMigration/hostedmigrationservice.svc**.

    A URL resultante, que é o valor do **HostedMigrationOverrideUrl**, deve se parecer com o seguinte:

     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

    > [!NOTE]
    > O tamanho máximo padrão para arquivos de registro de transação do banco de dados rtcxds é 16 GB. Isso pode não ser grande o suficiente para se você estiver movendo um grande número de usuários ao mesmo tempo, especialmente se você tiver habilitado o espelhamento. Para contornar a situação, aumente o tamanho de arquivo ou faça backup dos arquivos de registro regularmente. Para obter mais informações, consulte [https://support.microsoft.com/kb/2756725](https://support.microsoft.com/kb/2756725).

8. Esta etapa é opcional. Caso precise fazer a integração com o Exchange 2013 Online, será necessário utilizar um provedor de hospedagem adicional. Para obter detalhes, consulte [Configure de integração entre o local Skype para Business Server 2015 e Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md).

9. Os usuários foram movidos. Para verificar se um usuário possui os valores corretos dos atributos exibidos na tabela a seguir, digite este cmdlet:

  ```
  Get-CsUser | fl DisplayName,HostingProvider,SipAddress,Enabled
  ```

|**Atributo do Active Directory**|**Nome do atributo**|**Valor correto para usuário Online**|**Valor correto para usuários locais**|
|:-----|:-----|:-----|:-----|
|msRTCSIP-DeploymentLocator  <br/> |HostingProvider  <br/> |sipfed  <br/> |SRV:  <br/> |
|msRTCSIP-PrimaryUserAddress  <br/> |SIPAddress  <br/> |SIP:username@contoso.com  <br/> |SIP:username@contoso.com  <br/> |
|msRTCSIP-UserEnabled  <br/> |Habilitado  <br/> |True  <br/> |True  <br/> |

10. Cada usuário movido precisará fazer logout e fazer login novamente. Ao fazer login, deverão verificar a lista de contatos e adicionar, caso seja necessário.

    Observe que as reuniões agendadas não são migradas de online para local. Os usuários precisarão reagendar as reuniões depois de serem movidos.

    Depois que os registros DNS estão atualizados e todos os usuários são direcionados para o local, o atributo HostingProvider direciona o usuário use registros SRV ou direcioná-los para o provedor Online "sipfed."

## <a name="move-online-users-who-were-originally-on-premises-to-on-premises"></a>Mover usuários on-line (que estavam originalmente no local) no local
<a name="BKMK_originallyonprem"> </a>

Esta seção se aplica somente aos usuários que foram criados e habilitados para uma implantação local e depois movidos de uma implantação local para online.

- Execute os seguintes cmdlets para mover um usuário do Skype para Business Online para no local, substituindo o valor para os parâmetros **identidade** e de **destino** corrigir os valores para o seu ambiente:

  ```
  $cred=Get-Credential
  ```

  ```
  Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
  ```

O formato da URL especificado para o parâmetro **HostedMigrationOverrideUrl** deve ser a URL para o pool de onde o serviço de migração hospedado estiver em execução, no seguinte formato:

 _Https://\<FQDN do Pool\>/HostedMigration/hostedmigrationService.svc_. Você pode identificar a URL do serviço de migração hospedado visualizando a URL do Painel de Controle do Lync Online da sua conta de locatário do Office 365.

### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a>Para identificar a URL do Serviço de Migração Hospedada do seu locatário do Office 365

1. Faça logon no seu inquilino do Office 365 como um administrador.

2. Abra o **Centro de administração do Skype for Business**.

3. Com o **Centro de administração do Skype for Business** exibido, selecione e copie a URL na barra de endereço no **lync.com**. Uma URL de exemplo seria parecida com esta:

     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`

4. Substitua **webdir** na URL por **admin**, o que resulta no seguinte:

     `https://admin0a.online.lync.com`

5. Anexe a cadeia de caracteres a seguir à URL: **/HostedMigration/hostedmigrationservice.svc**.

    A URL resultante, que é o valor do **HostedMigrationOverrideUrl**, deve se parecer com o seguinte:

     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`


