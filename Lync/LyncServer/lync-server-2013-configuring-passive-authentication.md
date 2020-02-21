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
ms.openlocfilehash: 96c2c94bde12e6b8b77060a82f1990b673421de9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198774"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-passive-authentication"></a><span data-ttu-id="af9b4-102">Configurando a autenticação passiva do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af9b4-102">Configuring Lync Server 2013 passive authentication</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af9b4-103">_**Última modificação do tópico:** 2013-07-11_</span><span class="sxs-lookup"><span data-stu-id="af9b4-103">_**Topic Last Modified:** 2013-07-11_</span></span>

<span data-ttu-id="af9b4-104">A seção a seguir descreve como configurar o Lync Server 2013 com atualizações cumulativas: 2013 de julho para dar suporte à autenticação passiva.</span><span class="sxs-lookup"><span data-stu-id="af9b4-104">The following section describes how to configure Lync Server 2013 with Cumulative Updates: July 2013 to support passive authentication.</span></span> <span data-ttu-id="af9b4-105">Uma vez habilitado, os usuários do Lync habilitados para a autenticação de dois fatores serão solicitados a usar um cartão inteligente físico ou virtual e um PIN válido para entrar usando o Lync 2013 com atualizações cumulativas: cliente de julho de 2013.</span><span class="sxs-lookup"><span data-stu-id="af9b4-105">Once enabled, Lync users who are enabled for two-factor authentication will be required to use a physical or virtual smart card and a valid PIN to sign in using the Lync 2013 with Cumulative Updates: July 2013 client.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="af9b4-106">É altamente recomendável que os clientes habilitem a autenticação passiva para o registrador e os serviços Web no nível de serviço.</span><span class="sxs-lookup"><span data-stu-id="af9b4-106">It is strongly recommended that customers enable passive authentication for Registrar and Web Services at the service level.</span></span> <span data-ttu-id="af9b4-107">Se a autenticação passiva estiver habilitada para o registrador e os serviços Web no nível global, ele provavelmente resultará em falhas de autenticação em toda a organização para usuários que não estão fazendo logon com o Lync 2013 com atualizações cumulativas: cliente da área de trabalho cliente de julho de 2013.</span><span class="sxs-lookup"><span data-stu-id="af9b4-107">If passive authentication is enabled for Registrar and Web Services at the global level, it will likely result in organization-wide authentication failures for users who are not signing in with the Lync 2013 with Cumulative Updates: July 2013 client desktop client.</span></span>



</div>

<div>

## <a name="web-service-configuration"></a><span data-ttu-id="af9b4-108">Configuração do serviço Web</span><span class="sxs-lookup"><span data-stu-id="af9b4-108">Web Service Configuration</span></span>

<span data-ttu-id="af9b4-109">As etapas a seguir descrevem como criar uma configuração de serviço Web personalizada para diretores, pools corporativos e servidores Standard Edition que serão habilitados para autenticação passiva.</span><span class="sxs-lookup"><span data-stu-id="af9b4-109">The following steps describe how to create a custom web service configuration for Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

<span data-ttu-id="af9b4-110">**Para criar uma configuração de serviço da Web personalizada**</span><span class="sxs-lookup"><span data-stu-id="af9b4-110">**To create a custom web service configuration**</span></span>

1.  <span data-ttu-id="af9b4-111">Faça logon no Lync Server 2013 com atualizações cumulativas: servidor front end de julho de 2013 usando uma conta de administrador do Lync.</span><span class="sxs-lookup"><span data-stu-id="af9b4-111">Log in to your Lync Server 2013 with Cumulative Updates: July 2013 Front End server using a Lync administrator account.</span></span>

2.  <span data-ttu-id="af9b4-112">Inicie o Shell de gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="af9b4-112">Launch the Lync Server 2013 Management Shell.</span></span>

3.  <span data-ttu-id="af9b4-113">Na linha de comando do Shell de gerenciamento do Lync Server, crie uma nova configuração de serviço Web para cada diretor, pool corporativo e servidor Standard Edition que será habilitado para autenticação passiva executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="af9b4-113">From the Lync Server Management Shell command-line, create a new Web Service configuration for each Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command:</span></span>
    ```powershell
    New-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
    ```

    <div class="">
    

    > [!WARNING]  
    > <span data-ttu-id="af9b4-114">O valor para o FQDN WsFedPassiveMetadataUri é o nome do serviço de Federação do seu servidor AD FS 2,0.</span><span class="sxs-lookup"><span data-stu-id="af9b4-114">The value for the WsFedPassiveMetadataUri FQDN is the Federation Service Name of your AD FS 2.0 server.</span></span> <span data-ttu-id="af9b4-115">O valor do nome do serviço de Federação pode ser encontrado no console de gerenciamento do AD FS 2,0 clicando com o botão direito do mouse no <STRONG>serviço</STRONG> no painel de navegação e, em seguida, selecionando <STRONG>Editar propriedades do serviço de Federação</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="af9b4-115">The Federation Service Name value can be found in the AD FS 2.0 Management Console by right-clicking on <STRONG>Service</STRONG> from the navigation pane and then selecting <STRONG>Edit Federation Service Properties</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="af9b4-116">Verifique se os valores UseWsFedPassiveAuth e WsFedPassiveMetadataUri foram definidos corretamente executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="af9b4-116">Verify that the UseWsFedPassiveAuth and WsFedPassiveMetadataUri values were set correctly by running the following command:</span></span>
     ```powershell
     Get-CsWebServiceConfiguration -identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
     ```
5.  <span data-ttu-id="af9b4-117">Para clientes, a autenticação passiva é o método de autenticação menos preferencial para a autenticação webticket.</span><span class="sxs-lookup"><span data-stu-id="af9b4-117">For clients, Passive Authentication is the least preferred authentication method for webticket authentication.</span></span> <span data-ttu-id="af9b4-118">Para todos os diretores, pools corporativos e servidores Standard Edition que serão habilitados para autenticação passiva, todos os outros tipos de autenticação deverão ser desabilitados nos serviços Web do Lync executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="af9b4-118">For all Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication, all other authentication types must be disabled in Lync Web Services by running the following command:</span></span>
    ```powershell
    Set-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
     ```
6.  <span data-ttu-id="af9b4-119">Verifique se todos os outros tipos de autenticação foram desabilitados com êxito executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="af9b4-119">Verify that all other authentication types have been successfully disabled by running the following command:</span></span>
    ```powershell
    Get-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
     ```
</div>

<div>

## <a name="proxy-configuration"></a><span data-ttu-id="af9b4-120">Configuração de proxy</span><span class="sxs-lookup"><span data-stu-id="af9b4-120">Proxy Configuration</span></span>

<span data-ttu-id="af9b4-121">Quando a autenticação de certificado estiver desabilitada para o Lync Web Services, o cliente Lync usará um tipo de autenticação menos preferencial, como Kerberos ou NTLM, para autenticar no serviço registrador.</span><span class="sxs-lookup"><span data-stu-id="af9b4-121">When certificate authentication is disabled for Lync Web Services, the Lync client will use a less preferred authentication type, such as Kerberos or NTLM, to authenticate to the Registrar service.</span></span> <span data-ttu-id="af9b4-122">A autenticação de certificado ainda é necessária para permitir que o cliente Lync recupere um webticket, no entanto, Kerberos e NTLM devem ser desabilitados para o serviço registrador.</span><span class="sxs-lookup"><span data-stu-id="af9b4-122">Certificate authentication is still needed to allow the Lync client to retrieve a webticket, however, Kerberos and NTLM must be disabled for the Registrar service.</span></span>

<span data-ttu-id="af9b4-123">As etapas a seguir descrevem como criar uma configuração de proxy Personalizada para pools de borda, pools corporativos e servidores Standard Edition que serão habilitados para autenticação passiva.</span><span class="sxs-lookup"><span data-stu-id="af9b4-123">The following steps describe how to create a custom proxy configuration for Edge Pools, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

<span data-ttu-id="af9b4-124">**Para criar uma configuração de proxy Personalizada**</span><span class="sxs-lookup"><span data-stu-id="af9b4-124">**To create a custom proxy configuration**</span></span>

1.  <span data-ttu-id="af9b4-125">Na linha de comando do Shell de gerenciamento do Lync Server, crie uma nova configuração de proxy para cada Lync Server 2013 com atualizações cumulativas: pool de borda de julho de 2013, pool corporativo e servidor Standard Edition que será habilitado para autenticação passiva executando o seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="af9b4-125">From the Lync Server Management Shell command-line, create a new proxy configuration for each Lync Server 2013 with Cumulative Updates: July 2013 Edge Pool, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following commands:</span></span>
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```

2.  <span data-ttu-id="af9b4-126">Verifique se todos os outros tipos de autenticação de proxy foram desabilitados com êxito executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="af9b4-126">Verify that all other proxy authentication types have been successfully disabled by running the following command:</span></span>
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

