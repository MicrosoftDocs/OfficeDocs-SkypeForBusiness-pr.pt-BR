---
title: 'Lync Server 2013: migrando os usuários do Lync Online para o Lync local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Migrating Lync Online users to Lync on-premises
ms:assetid: 0e29605b-db2d-4cbf-b6a9-15db6b9fdabc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689115(v=OCS.15)
ms:contentKeyID: 62258120
ms.date: 11/13/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d33888069b00eaf8a4d743f1e6ed3937d7a442bc
ms.sourcegitcommit: 5895afd0d5752a6ea1ace68d613f86c68eae8bdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2019
ms.locfileid: "34857488"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-lync-online-users-to-lync-on-premises-in-lync-server-2013"></a>Migrando usuários do Lync Online para o Lync local no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2015-11-13_

<div class="">


> [!IMPORTANT]  
> Essas etapas são necessárias somente para migrar contas de usuário originalmente habilitadas para o Lync no Lync Online antes de você implantar o Lync local. Para mover os usuários que foram originalmente habilitados para o Lync local e depois foram movidos para o Lync Online, consulte <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">administrando usuários em uma implantação híbrida do Lync Server 2013</A>.<BR>Além disso, todos os usuários que migrarem devem ter contas no Diretório Ativo local.



</div>

<div>

## <a name="migrating-user-accounts-originally-enabled-in-lync-online-to-lync-on-premises"></a>Migrando contas de usuário originalmente habilitadas no Lync Online para o Lync local

1.  Primeiro, verifique se a sua organização está configurada para híbrido.
    
      - Instale a ferramenta de sincronização do Azure Active Directory. Para obter mais informações, <http://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>consulte.
    
      - Para permitir que seus usuários usem o logon único para o Lync Online, instale os serviços <http://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>de Federação do Active Directory.
    
      - Na sua implantação local, no Shell de gerenciamento do Lync Server, digite os seguintes cmdlets para criar o provedor de hospedagem para o Lync Online:
        
           ```
           Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
           ```
        
           ```
            New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
           ```

2.  Confirme que, em seus servidores de borda local, você tem a cadeia de certificados que permite a conexão com o Lync Online, conforme mostrado na tabela a seguir. Você pode baixar esta cadeia aqui:https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb


    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Certificado</th>
    <th>Repositório de Certificado</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Raiz do Baltimore CyberTrust</p></td>
    <td><p>AC Raiz Confiável</p></td>
    </tr>
    <tr class="even">
    <td><p>Microsoft Internet Authority (novo certificado CA)</p></td>
    <td><p>CA intermediário</p></td>
    </tr>
    <tr class="odd">
    <td><p>MSIT Machine Auth CA2 (nova emissão de CA2)</p></td>
    <td><p>CA intermediário</p></td>
    </tr>
    </tbody>
    </table>

3.  Em seu Active Directory local, habilite as contas de usuário afetadas no Lync local. Essa ação é possível para usuários individuais digitando o cmdlet a seguir:
    
        Enable-CsUser
        -Identity "username" 
        -SipAddress "sip: username@contoso.com"
        -HostingProviderProxyFqdn "sipfed.online.lync.com"
    
    Você também pode criar um script que lê os nomes de usuário a partir de um arquivo e os oferece como input ao cmdlet Enable-CsUser:
    
        Enable-CsUser
        -Identity $Identity 
        -SipAddress $SipAddress 
        -HostingProviderProxyFqdn "sipfed.online.lync.com"

4.  Execute o DirSync para sincronizar os usuários do Lync Online com os usuários do Lync local atualizados.

5.  Atualize alguns registros DNS para direcionar todo o tráfego SIP para o Lync local:
    
      - Atualize o **lyncdiscover.contoso.com** Um registro para apontar ao FQDN do servidor de proxy reverso do local.
    
      - Atualize o ***\_SIP *.\_ **registro SRV TLS.contoso.com para resolver para o endereço IP público ou VIP do serviço de borda de acesso do Lync local.
    
      - Atualize o ***\_sipfederationtls *.\_ **registro SRV TCP.contoso.com para resolver para o endereço IP público ou VIP do serviço de borda de acesso do Lync local.
    
      - Se sua organização usa DNS divididos (conhecidos como “split-brain DNS”), certifique-se de que os usuários que solucionam nomes por meio da zona DNS interna sejam direcionados ao Pool de Front-ends.

6.  Digite o `Get-CsUser` cmdlet para verificar algumas propriedades sobre os usuários que você moverá. Você deseja certificar-se de que o HostingProviderProxyFQDN está definido `"sipfed.online.lync.com"` e que os endereços SIP estão definidos corretamente.

7.  Mover os usuários do Lync Online para o Lync local.
    
    Para mover um único usuário, digite:
    
       ```
       $cred = Get-Credential
       ```
    
       ```
       Move-CsUser -Identity <username>@contoso.com -Target "<fe-pool>.contoso.com" -Credential $cred -HostedMigrationOverrideURL <URL>
       ```
    
    Você pode mover usuários únicos por meio do cmdlet **Get-CsUSer** com o parâmetro –Filtro para selecionar os usuários com determinada propriedade. Por exemplo, você pode selecionar todos os usuários do Lync Online filtrando para {host Provider – EQ "sipfed.online.lync.om"}. Em seguida, poderá canalizar os usuários retornados para o cmdlet **Move-CsUSer**, como mostra abaixo.
    
        Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com" -Credential $creds -HostedMigrationOverrideURL <URL>
    
    O formato da URL especificada para o parâmetro **HostedMigrationOverrideUrl** deve ser a URL do pool em que o serviço de migração hospedada está em execução, no seguinte formato *:\<https://pool\>FQDN/HostedMigration/ hostedmigrationService. svc*.
    
    Você pode identificar a URL do serviço de migração hospedado visualizando a URL do Painel de Controle do Lync Online da sua conta de locatário do Office 365.
    
    <div>
    
    ## <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a>Para identificar a URL do Serviço de Migração Hospedada do seu locatário do Office 365
    
    1.  Faça logon no seu inquilino do Office 365 como um administrador.
    
    2.  Abra o **centro de administração do Lync**.
    
    3.  Com o **centro de administração do Lync** exibido, selecione e copie a URL na barra de endereços até **Lync.com**. Uma URL de exemplo seria parecida com esta:
        
        `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`
    
    4.  Substitua **webdir** na URL por **admin**, o que resulta no seguinte:
        
        `https://admin0a.online.lync.com`
    
    5.  Anexe a cadeia de caracteres a seguir à URL: **/HostedMigration/hostedmigrationservice.svc**.
        
        A URL resultante, que tem o valor de **HostedMigrationOverrideUrl**, deverá ser parecida com esta:
        
        `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    </div>
    
    <div class="">
    

    > [!NOTE]  
    > O tamanho máximo padrão para arquivos de registro de transação do banco de dados rtcxds é 16 GB. Este tamanho pode não ser suficiente caso você esteja movendo uma grande quantidade de usuários de uma só vez, especialmente se o espelhamento estiver ativado. Para contornar a situação, aumente o tamanho de arquivo ou faça backup dos arquivos de registro regularmente. Para obter mais informações, <A class=uri href="http://support.microsoft.com/kb/2756725">http://support.microsoft.com/kb/2756725</A>consulte.

    
    </div>

8.  Esta etapa é opcional. Caso precise fazer a integração com o Exchange 2013 Online, será necessário utilizar um provedor de hospedagem adicional. Para obter detalhes, consulte Configurando [a integração do Lync Server 2013 no Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md).

9.  Os usuários foram movidos. Para verificar se um usuário possui os valores corretos dos atributos exibidos na tabela a seguir, digite este cmdlet:
    
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
    <td><p>HostingProvider</p></td>
    <td><p>sipfed.online.lync.com</p></td>
    <td><p>SRV:</p></td>
    </tr>
    <tr class="even">
    <td><p>msRTCSIP-PrimaryUserAddress</p></td>
    <td><p>SIPAddress</p></td>
    <td><p>sip:userName@contoso.com</p></td>
    <td><p>sip:userName@contoso.com</p></td>
    </tr>
    <tr class="odd">
    <td><p>msRTCSIP-UserEnabled</p></td>
    <td><p>Habilitado</p></td>
    <td><p>True</p></td>
    <td><p>True</p></td>
    </tr>
    </tbody>
    </table>


10. Cada usuário que tiver sido movido precisará fazer logoff do Lync e, em seguida, conectar-se novamente. Ao fazer login, deverão verificar a lista de contatos e adicionar, caso seja necessário.
    
    Observe que as reuniões agendadas não são migradas do Lync Online para o Lync local. Os usuários precisarão reagendar as reuniões depois de serem movidos.
    
    Depois que os registros DNS são atualizados e todos os usuários são direcionados para o local, o atributo Hostingprovider direciona o usuário do Lync para usar registros SRV ou direcioná-los para o provedor online "sipfed.online.lync.com".

</div>

</div>

<span> </span>

</div>

</div>

</div>

