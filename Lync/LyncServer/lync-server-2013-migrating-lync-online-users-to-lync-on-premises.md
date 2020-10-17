---
title: 'Lync Server 2013: Migrando usuários do Lync Online para o Lync local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migrating Lync Online users to Lync on-premises
ms:assetid: 0e29605b-db2d-4cbf-b6a9-15db6b9fdabc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689115(v=OCS.15)
ms:contentKeyID: 62258120
ms.date: 11/13/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a2be7414dbdc48c9e245db33e57b8238cfb2ee9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520988"
---
# <a name="migrating-lync-online-users-to-lync-on-premises-in-lync-server-2013"></a>Migração de usuários do Lync Online para o Lync no local no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2015-11-13_

<div class="">


> [!IMPORTANT]  
> Essas etapas são necessárias somente para migrar contas de usuário que foram originalmente habilitadas para Lync no Lync Online, antes de implantar o Lync local. Para mover os usuários que foram originalmente habilitados para o Lync local e depois movidos para o Lync Online, consulte <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Administração de usuários em uma implantação híbrida do Lync Server 2013</A>.<BR>Além disso, todos os usuários que estão sendo movidos devem ter contas no Active Directory local.



</div>

<div>

## <a name="migrating-user-accounts-originally-enabled-in-lync-online-to-lync-on-premises"></a>Migrando contas de usuário originalmente habilitadas no Lync Online para o Lync local

1.  Primeiro, certifique-se de que sua organização está configurada para híbrido.
    
      - Instale a ferramenta de sincronização do Azure Active Directory. Para obter mais informações, confira <https://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>.
    
      - Para permitir que os usuários usem o single sign-on para o Lync Online, instale os serviços de Federação do Active Directory <https://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx> .
    
      - Em sua implantação local, no Shell de gerenciamento do Lync Server, digite os cmdlets a seguir para criar o provedor de hospedagem para o Lync Online:
        
           ```PowerShell
           Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
           ```
        
           ```PowerShell
            New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
           ```

2.  Confirme que, em seus servidores de borda no local, você tem a cadeia de certificados que permite a conexão com o Lync Online, conforme mostrado na tabela a seguir. Você pode baixar essa cadeia aqui: https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb


    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Certificado</th>
    <th>Repositório de Certificados</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Baltimore CyberTrust Root</p></td>
    <td><p>AC raiz confiável</p></td>
    </tr>
    <tr class="even">
    <td><p>Autoridade da Internet da Microsoft (novo certificado de autoridade de certificação)</p></td>
    <td><p>Autoridade de certificação intermediária</p></td>
    </tr>
    <tr class="odd">
    <td><p>MSIT de autenticação de máquina CA2 (nova CA2 de emissão)</p></td>
    <td><p>Autoridade de certificação intermediária</p></td>
    </tr>
    </tbody>
    </table>

3.  No Active Directory local, habilite as contas de usuário afetadas para o Lync local. Você pode fazer isso para um usuário individual digitando o seguinte cmdlet:
    
        Enable-CsUser
        -Identity "username" 
        -SipAddress "sip: username@contoso.com"
        -HostingProviderProxyFqdn "sipfed.online.lync.com"
    
    Ou você pode criar um script que lê os nomes de usuário de um arquivo e os fornece como entrada para o cmdlet Enable-CsUser:
    
        Enable-CsUser
        -Identity $Identity 
        -SipAddress $SipAddress 
        -HostingProviderProxyFqdn "sipfed.online.lync.com"

4.  Execute DirSync para sincronizar os usuários do Lync Online com os usuários locais do Lync atualizados.

5.  Atualize alguns registros DNS para direcionar todo o tráfego SIP para o Lync local:
    
      - Atualize o **Lyncdiscover.contoso.com** um registro para apontar para o FQDN do servidor de proxy reverso local.
    
      - Atualize o *** \_ SIP *. \_ tls.contoso.com** registro SRV para resolver para o endereço IP público ou VIP do serviço de borda de acesso do Lync local.
    
      - Atualize o *** \_ sipfederationtls *. \_ tcp.contoso.com** registro SRV para resolver para o endereço IP público ou VIP do serviço de borda de acesso do Lync local.
    
      - Se sua organização usa DNS dividido (às vezes chamado de "DNS de divisões"), certifique-se de que os usuários que resolvem nomes através da zona DNS interna sejam direcionados para o pool de front-ends.

6.  Digite o `Get-CsUser` cmdlet para verificar algumas propriedades sobre os usuários que serão movidos. Você deseja certificar-se de que o HostingProviderProxyFQDN está definido como `"sipfed.online.lync.com"` e que os endereços SIP estão definidos corretamente.

7.  Mover os usuários do Lync Online para o Lync no local.
    
    Para mover um único usuário, digite:
    
       ```PowerShell
       $cred = Get-Credential
       ```
    
       ```PowerShell
       Move-CsUser -Identity <username>@contoso.com -Target "<fe-pool>.contoso.com" -Credential $cred -HostedMigrationOverrideURL <URL>
       ```
    
    Você pode mover vários usuários usando o cmdlet **Get-CsUSer** com o parâmetro – Filter para selecionar os usuários com uma propriedade específica. Por exemplo, você pode selecionar todos os usuários do Lync Online filtrando para {Hosting Provider – EQ "sipfed.online.lync.om"}. Você pode canalizar os usuários retornados para o cmdlet **move-CsUSer** , como mostrado abaixo.
    
        Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com" -Credential $creds -HostedMigrationOverrideURL <URL>
    
    O formato da URL especificada para o parâmetro **HostedMigrationOverrideUrl** deve ser a URL para o pool onde o serviço de migração hospedado está sendo executado, no seguinte formato: *https:// \<Pool FQDN\> /HostedMigration/hostedmigrationService.svc*.
    
    Você pode determinar a URL para o serviço de migração hospedado visualizando a URL do painel de controle do Lync Online para sua conta de organização do Microsoft 365 ou do Office 365.
    
    <div>
    
    ## <a name="to-determine-the-hosted-migration-service-url-for-your-organizaton"></a>Para determinar a URL do serviço de migração hospedado para seu organização
    
    1.  Faça logon na sua organização do Microsoft 365 ou do Office 365 como administrador.
    
    2.  Abra o **centro de administração do Lync**.
    
    3.  Com o **centro de administração do Lync** exibido, selecione e copie a URL na barra de endereços até **Lync.com**. Uma URL de exemplo é semelhante à seguinte:
        
        `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`
    
    4.  Substitua **Webdir** na URL por **admin**, resultando no seguinte:
        
        `https://admin0a.online.lync.com`
    
    5.  Acrescente a seguinte cadeia de caracteres à URL: **/HostedMigration/hostedmigrationservice.svc**.
        
        A URL resultante, que é o valor do **HostedMigrationOverrideUrl**, deve ter a seguinte aparência:
        
        `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    </div>
    
    <div class="">
    

    > [!NOTE]  
    > O tamanho máximo padrão para os arquivos de log de transações do banco de dados do rtcxds é de 16 GB. Isso pode não ser grande o suficiente se você estiver movendo um grande número de usuários de uma só vez, especialmente se você tiver o espelhamento habilitado. Para contornar isso, você pode aumentar o tamanho do arquivo ou fazer o backup dos arquivos de log regularmente. Para obter mais informações, consulte <A class=uri href="https://support.microsoft.com/kb/2756725">https://support.microsoft.com/kb/2756725</A> .

    
    </div>

8.  Esta etapa é opcional. Se for necessário integrar com o Exchange 2013 online, você precisará usar um provedor de hospedagem adicional. Para obter detalhes, consulte [Configuring on-premises Lync Server 2013 Integration with Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md).

9.  Os usuários agora serão movidos. Para verificar se um usuário tem valores corretos para os atributos mostrados na tabela a seguir, digite este cmdlet:
    
        Get-CsUser | fl DisplayName,HostingProvider,SipAddress,Enabled
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Atributo do Active Directory</th>
    <th>Nome do atributo</th>
    <th>Valor correto para o usuário do Lync Online</th>
    <th>Valor correto para usuários do Lync on-premises</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>msRTCSIP-DeploymentLocator</p></td>
    <td><p>Hostingprovider</p></td>
    <td><p>sipfed.online.lync.com</p></td>
    <td><p>SRV</p></td>
    </tr>
    <tr class="even">
    <td><p>msRTCSIP-PrimaryUserAddress</p></td>
    <td><p>SIPAddress</p></td>
    <td><p>sip:userName@contoso.com</p></td>
    <td><p>sip:userName@contoso.com</p></td>
    </tr>
    <tr class="odd">
    <td><p>msRTCSIP-userhabilitado</p></td>
    <td><p>Habilitado</p></td>
    <td><p>Verdadeiro</p></td>
    <td><p>Verdadeiro</p></td>
    </tr>
    </tbody>
    </table>


10. Cada usuário que tiver sido movido precisará fazer logout do Lync e, em seguida, fazer logon novamente. Quando eles fazem logon, eles devem verificar suas listas de contatos e adicionar contatos, se necessário.
    
    Observe que as reuniões agendadas não são migradas do Lync Online para o Lync local. Os usuários precisarão reagendar essas reuniões após serem movidas.
    
    Depois que os registros DNS são atualizados e todos os usuários são direcionados para o local, o atributo Hostingprovider orienta o usuário do Lync a usar registros SRV ou direcioná-los ao provedor online "sipfed.online.lync.com".

</div>

</div>

<span> </span>

</div>

</div>

</div>

