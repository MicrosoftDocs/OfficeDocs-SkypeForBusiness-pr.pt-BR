---
title: 'Lync Server 2013: Configurando autenticação passiva'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Lync Server passive authentication
ms:assetid: 9a904b8d-9fce-4abf-be73-5c8e48cfb53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308569(v=OCS.15)
ms:contentKeyID: 54973690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 590a196ca0e34c0c063b10703c7edd131eb82c50
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971104"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-passive-authentication"></a>Configurando a autenticação passiva do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-07-11_

A seção a seguir descreve como configurar o Lync Server 2013 com atualizações cumulativas: 2013 de julho para dar suporte à autenticação passiva. Uma vez habilitado, os usuários do Lync habilitados para a autenticação de dois fatores serão necessários para usar um cartão inteligente físico ou virtual e um PIN válido para entrar usando o Lync 2013 com atualizações cumulativas: cliente de julho de 2013.

<div class="">


> [!NOTE]  
> Recomendamos que os clientes habilitem a autenticação passiva para o Registrador e para os Serviços Web no nível de serviço. Se a autenticação passiva estiver habilitada para o registrador e os serviços Web no nível global, ele provavelmente resultará em falhas de autenticação em toda a organização para os usuários que não estão se conectando ao Lync 2013 com atualizações cumulativas: 2013 de julho de cliente da área de trabalho.



</div>

<div>

## <a name="web-service-configuration"></a>Configuração dos Serviços Web

As etapas a seguir descrevem como criar uma configuração personalizada de serviços Web para servidores Diretores, pools Enterprise e Standard Edition que serão habilitados para a autenticação passiva.

**Para criar uma configuração personalizada de serviços Web**

1.  Faça logon no Lync Server 2013 com atualizações cumulativas: servidor front-end de julho de 2013 usando uma conta de administrador do Lync.

2.  Inicie o Shell de gerenciamento do Lync Server 2013.

3.  Na linha de comando do Shell de gerenciamento do Lync Server, crie uma nova configuração de serviço Web para cada director, pool corporativo e servidor Standard Edition que será habilitado para autenticação passiva executando o seguinte comando:
    ```powershell
    New-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
    ```

    <div class="">
    

    > [!WARNING]  
    > O valor para o FQDN WsFedPassiveMetadataUri é o Nome de Serviço de Federação do seu servidor AD FS 2.0. O valor do Nome de Serviço de Federação pode ser encontrado no Console de Gerenciamento do AD FS 2.0 clicando com o botão direito do mouse em <STRONG>Serviço</STRONG> a partir do painel de navegação, selecionando em seguida <STRONG>Editar propriedades do serviço de federação</STRONG>.

    
    </div>

4.  Verifique se os valores UseWsFedPassiveAuth e WsFedPassiveMetadataUri foram definidos corretamente executando o seguinte comando:
     ```powershell
     Get-CsWebServiceConfiguration -identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
     ```
5.  Para clientes, a Autenticação Passiva é o método de autenticação menos indicado para autenticação de webticket. Para todos os directors, pools corporativos e servidores Standard Edition que serão habilitados para autenticação passiva, todos os outros tipos de autenticação deverão ser desabilitados nos serviços Web do Lync executando o seguinte comando:
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

Quando a autenticação de certificado estiver desabilitada para os serviços Web do Lync, o cliente Lync usará um tipo de autenticação menos preferencial, como Kerberos ou NTLM, para autenticar para o serviço registrador. A autenticação de certificado ainda é necessária para permitir que o cliente Lync recupere um webticket, no entanto, Kerberos e NTLM devem ser desabilitados para o serviço registrador.

As etapas a seguir descrevem como criar uma configuração personalizada de proxy para servidores de pools Edge, pools Enterprise e Standard Edition que serão habilitados para a autenticação passiva.

**Para criar uma configuração personalizada de proxy**

1.  Na linha de comando do Shell de gerenciamento do Lync Server, crie uma nova configuração de proxy para cada Lync Server 2013 com atualizações cumulativas: o pool de bordas de julho de 2013, o pool corporativo e o servidor Standard Edition que serão habilitados para autenticação passiva executando o seguintes comandos:
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```

2.  Verifique se todos os outros tipos de autenticação de proxy foram desabilitados com sucesso executando o seguinte comando:
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

