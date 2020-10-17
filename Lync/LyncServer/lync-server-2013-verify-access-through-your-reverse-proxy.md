---
title: 'Lync Server 2013: verificar acesso por meio de seu proxy reverso'
description: 'Lync Server 2013: Verifique o acesso por meio do proxy reverso.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify access through your reverse proxy
ms:assetid: 3076a786-e022-4d41-91ec-1bf252b2a468
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429697(v=OCS.15)
ms:contentKeyID: 48183753
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 593aac5574f0dcf683351f12a6392f6116480ac5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547117"
---
# <a name="verify-access-through-your-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="d876a-103">Verificar o acesso por meio de seu proxy reverso no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d876a-103">Verify access through your reverse proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d876a-104">_**Última modificação do tópico:** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="d876a-104">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="d876a-p101">Execute o procedimento a seguir para verificar se os usuários podem acessar informações no proxy reverso. Talvez seja necessário concluir a configuração do firewall e do DNS (Sistema de Nomes de Domínio) para que o acesso funcione corretamente.</span><span class="sxs-lookup"><span data-stu-id="d876a-p101">Use the following procedure to verify that your users can access information on the reverse proxy. You might need to complete the firewall configuration and Domain Name System (DNS) configuration before access will work correctly.</span></span>

<div>

## <a name="to-verify-that-you-can-access-the-website-through-the-internet"></a><span data-ttu-id="d876a-107">Para verificar se você pode acessar o site via Internet</span><span class="sxs-lookup"><span data-stu-id="d876a-107">To verify that you can access the website through the Internet</span></span>

  - <span data-ttu-id="d876a-108">Abra um navegador da Web e, na barra **Endereço**, digite as URLs que são usadas pelos clientes para acessar os arquivos do Catálogo de Endereços e o site de Webconferências da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="d876a-108">Open a web browser, type the URLs in the **Address** bar that clients use to access the Address Book files and the website for conferencing as follows:</span></span>
    
      - <span data-ttu-id="d876a-109">Para o servidor de catálogo de endereços, digite uma URL semelhante à seguinte: **https://externalwebfarmFQDN/abs** onde externalwebfarmFQDN é o FQDN externo dos serviços Web externos que hospeda os serviços de catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="d876a-109">For Address Book Server, type a URL similar to the following: **https://externalwebfarmFQDN/abs** where externalwebfarmFQDN is the external FQDN of the external web services that hosts Address Book services.</span></span> <span data-ttu-id="d876a-110">O usuário deve receber um desafio HTTP, pois a segurança do diretório na pasta do Servidor de Catálogo de Endereço está configurada para autenticação do Windows por padrão.</span><span class="sxs-lookup"><span data-stu-id="d876a-110">The user should receive an HTTP challenge, because directory security on the Address Book Server folder is configured to Windows authentication by default.</span></span>
    
      - <span data-ttu-id="d876a-111">Para conferência, digite uma URL semelhante à seguinte: **https://externalwebfarmFQDN/meet** onde externalwebfarmFQDN é o FQDN externo do farm da Web que hospeda o conteúdo da reunião.</span><span class="sxs-lookup"><span data-stu-id="d876a-111">For conferencing, type a URL similar to the following: **https://externalwebfarmFQDN/meet** where externalwebfarmFQDN is the external FQDN of the web farm that hosts meeting content.</span></span> <span data-ttu-id="d876a-112">Essa URL deve exibir a página de solução de problemas para conferência.</span><span class="sxs-lookup"><span data-stu-id="d876a-112">This URL should display the troubleshooting page for conferencing.</span></span> <span data-ttu-id="d876a-113">Em alternativa, confirme que sua URL Simples para conferência funcione corretamente.</span><span class="sxs-lookup"><span data-stu-id="d876a-113">Alternatively, confirm that your Simple URL for conferencing functions correctly.</span></span> <span data-ttu-id="d876a-114">Um exemplo de URL simples para a junção de conferência pode ser https://meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d876a-114">An example Simple URL for the conference join might be https://meet.contoso.com</span></span>
    
      - <span data-ttu-id="d876a-115">Para expansão de grupo de distribuição, digite uma URL semelhante à seguinte: **https://externalwebfarmFQDN/GroupExpansion/service.svc** .</span><span class="sxs-lookup"><span data-stu-id="d876a-115">For distribution group expansion, type a URL similar to the following: **https://externalwebfarmFQDN/GroupExpansion/service.svc**.</span></span> <span data-ttu-id="d876a-116">O usuário deve receber um desafio HTTP, pois a segurança do diretório no serviço de expansão do grupo de distribuição está configurada para autenticação do Windows por padrão.</span><span class="sxs-lookup"><span data-stu-id="d876a-116">The user should receive an HTTP challenge, because directory security on the distribution group expansion service is configured to Windows authentication by default.</span></span>
    
      - <span data-ttu-id="d876a-117">Para discagem, digite a URL simples semelhante à seguinte, **https://externalwebfarmFQDN/dialin** em que externalwebfarmFQDN é o FQDN externo do farm da Web que hospeda a página de discagem para conferência discada.</span><span class="sxs-lookup"><span data-stu-id="d876a-117">For dial-in, type the simple URL similar to the following **https://externalwebfarmFQDN/dialin** where externalwebfarmFQDN is the external FQDN of the web farm that hosts the dial-in page for dial-in conferencing.</span></span> <span data-ttu-id="d876a-118">O usuário deve ser redirecionado para a página de discagem.</span><span class="sxs-lookup"><span data-stu-id="d876a-118">The user should be directed to the dial-in page.</span></span> <span data-ttu-id="d876a-119">Em alternativa, confirme que sua discagem de URL simples funcione corretamente.</span><span class="sxs-lookup"><span data-stu-id="d876a-119">Alternatively, confirm that your Simple URL dial-in functions correctly.</span></span> <span data-ttu-id="d876a-120">Um exemplo de URL simples para discagem pode ser https://dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d876a-120">An example Simple URL for dial-in might be https://dialin.contoso.com</span></span>
    
      - <span data-ttu-id="d876a-121">Para confirmar se a URL de descoberta automática está funcionando, digite https://lyncdiscover .</span><span class="sxs-lookup"><span data-stu-id="d876a-121">To confirm that the autodiscover URL is working, type https://lyncdiscover.</span></span> <span data-ttu-id="d876a-122">externaldomainFQDN.</span><span class="sxs-lookup"><span data-stu-id="d876a-122">externaldomainFQDN.</span></span> <span data-ttu-id="d876a-123">O navegador deve solicitar que você abra um arquivo.</span><span class="sxs-lookup"><span data-stu-id="d876a-123">The browser should prompt you to open a file.</span></span> <span data-ttu-id="d876a-124">Selecione o bloco de notas para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="d876a-124">Select Notepad to open it.</span></span> <span data-ttu-id="d876a-125">Uma resposta típica seria semelhante a:</span><span class="sxs-lookup"><span data-stu-id="d876a-125">A typical response would be similar to:</span></span>
        
            {"AccessLocation":"External","Root":{"Links":[{"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/domain","token":"Domain"},
            {"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/user","token":"User"},
            {"href":"https:\/\/lyncweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/oauth\/user","token":"OAuth"}]}}

</div>

</div>

<span> </span>

</div>

</div>

</div>

