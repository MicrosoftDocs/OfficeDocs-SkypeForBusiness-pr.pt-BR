---
title: 'Lync Server 2013: Configurando a autenticação passiva'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server passive authentication
ms:assetid: 9a904b8d-9fce-4abf-be73-5c8e48cfb53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308569(v=OCS.15)
ms:contentKeyID: 54973690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a50cb75bdf833468d6974b9ddce1b282c1872d3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046334"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-passive-authentication"></a>Configurando a autenticação passiva do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-07-11_

A seção a seguir descreve como configurar o Lync Server 2013 com atualizações cumulativas: 2013 de julho para dar suporte à autenticação passiva. Uma vez habilitado, os usuários do Lync habilitados para a autenticação de dois fatores serão solicitados a usar um cartão inteligente físico ou virtual e um PIN válido para entrar usando o Lync 2013 com atualizações cumulativas: cliente de julho de 2013.

<div class="">


> [!NOTE]  
> É altamente recomendável que os clientes habilitem a autenticação passiva para o registrador e os serviços Web no nível de serviço. Se a autenticação passiva estiver habilitada para o registrador e os serviços Web no nível global, ele provavelmente resultará em falhas de autenticação em toda a organização para usuários que não estão fazendo logon com o Lync 2013 com atualizações cumulativas: cliente da área de trabalho cliente de julho de 2013.



</div>

<div>

## <a name="web-service-configuration"></a>Configuração do serviço Web

As etapas a seguir descrevem como criar uma configuração de serviço Web personalizada para diretores, pools corporativos e servidores Standard Edition que serão habilitados para autenticação passiva.

**Para criar uma configuração de serviço da Web personalizada**

1.  Faça logon no Lync Server 2013 com atualizações cumulativas: servidor front end de julho de 2013 usando uma conta de administrador do Lync.

2.  Inicie o Shell de gerenciamento do Lync Server 2013.

3.  Na linha de comando do Shell de gerenciamento do Lync Server, crie uma nova configuração de serviço Web para cada diretor, pool corporativo e servidor Standard Edition que será habilitado para autenticação passiva executando o seguinte comando:
    ```powershell
    New-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
    ```

    <div class="">
    

    > [!WARNING]  
    > O valor para o FQDN WsFedPassiveMetadataUri é o nome do serviço de Federação do seu servidor AD FS 2,0. O valor do nome do serviço de Federação pode ser encontrado no console de gerenciamento do AD FS 2,0 clicando com o botão direito do mouse no <STRONG>serviço</STRONG> no painel de navegação e, em seguida, selecionando <STRONG>Editar propriedades do serviço de Federação</STRONG>.

    
    </div>

4.  Verifique se os valores UseWsFedPassiveAuth e WsFedPassiveMetadataUri foram definidos corretamente executando o seguinte comando:
     ```powershell
     Get-CsWebServiceConfiguration -identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
     ```
5.  Para clientes, a autenticação passiva é o método de autenticação menos preferencial para a autenticação webticket. Para todos os diretores, pools corporativos e servidores Standard Edition que serão habilitados para autenticação passiva, todos os outros tipos de autenticação deverão ser desabilitados nos serviços Web do Lync executando o seguinte comando:
    ```powershell
    Set-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
     ```
6.  Verifique se todos os outros tipos de autenticação foram desabilitados com êxito executando o seguinte comando:
    ```powershell
    Get-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
     ```
</div>

<div>

## <a name="proxy-configuration"></a>Configuração de proxy

Quando a autenticação de certificado estiver desabilitada para o Lync Web Services, o cliente Lync usará um tipo de autenticação menos preferencial, como Kerberos ou NTLM, para autenticar no serviço registrador. A autenticação de certificado ainda é necessária para permitir que o cliente Lync recupere um webticket, no entanto, Kerberos e NTLM devem ser desabilitados para o serviço registrador.

As etapas a seguir descrevem como criar uma configuração de proxy Personalizada para pools de borda, pools corporativos e servidores Standard Edition que serão habilitados para autenticação passiva.

**Para criar uma configuração de proxy Personalizada**

1.  Na linha de comando do Shell de gerenciamento do Lync Server, crie uma nova configuração de proxy para cada Lync Server 2013 com atualizações cumulativas: pool de borda de julho de 2013, pool corporativo e servidor Standard Edition que será habilitado para autenticação passiva executando o seguintes comandos:
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```

2.  Verifique se todos os outros tipos de autenticação de proxy foram desabilitados com êxito executando o seguinte comando:
    ```powershell
    Get-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com"
         | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
     ```
</div>

</div>

<span> </span>

</div>

</div>

</div>

