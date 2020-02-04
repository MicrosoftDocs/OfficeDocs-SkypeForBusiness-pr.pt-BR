---
title: 'Lync Server 2013: Verificar acesso por meio de seu proxy reverso'
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
ms.openlocfilehash: e13f7e23f3404191f7251c1f49bda6f8935a2929
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763555"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-access-through-your-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="ff016-102">Verificar acesso por meio de seu proxy reverso no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff016-102">Verify access through your reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff016-103">_**Tópico da última modificação:** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="ff016-103">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="ff016-104">Use o procedimento a seguir para verificar se os usuários podem acessar informações no proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="ff016-104">Use the following procedure to verify that your users can access information on the reverse proxy.</span></span> <span data-ttu-id="ff016-105">Talvez seja necessário concluir a configuração do firewall e a configuração do sistema de nome de domínio (DNS) antes de o Access funcionar corretamente.</span><span class="sxs-lookup"><span data-stu-id="ff016-105">You might need to complete the firewall configuration and Domain Name System (DNS) configuration before access will work correctly.</span></span>

<div>

## <a name="to-verify-that-you-can-access-the-website-through-the-internet"></a><span data-ttu-id="ff016-106">Para verificar se você pode acessar o site pela Internet</span><span class="sxs-lookup"><span data-stu-id="ff016-106">To verify that you can access the website through the Internet</span></span>

  - <span data-ttu-id="ff016-107">Abra um navegador da Web, digite as URLs na barra de **endereços** que os clientes usam para acessar os arquivos do catálogo de endereços e o site para conferência da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="ff016-107">Open a web browser, type the URLs in the **Address** bar that clients use to access the Address Book files and the website for conferencing as follows:</span></span>
    
      - <span data-ttu-id="ff016-108">Para o servidor do catálogo de endereços, digite uma URL semelhante à **https://externalwebfarmFQDN/abs** seguinte: onde externalwebfarmFQDN é o FQDN externo dos serviços Web externos que hospeda os serviços de catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="ff016-108">For Address Book Server, type a URL similar to the following: **https://externalwebfarmFQDN/abs** where externalwebfarmFQDN is the external FQDN of the external web services that hosts Address Book services.</span></span> <span data-ttu-id="ff016-109">O usuário deve receber um desafio HTTP porque a segurança do diretório na pasta do servidor do catálogo de endereços está configurada como autenticação do Windows por padrão.</span><span class="sxs-lookup"><span data-stu-id="ff016-109">The user should receive an HTTP challenge, because directory security on the Address Book Server folder is configured to Windows authentication by default.</span></span>
    
      - <span data-ttu-id="ff016-110">Em conferência, digite uma URL semelhante à seguinte: **https://externalwebfarmFQDN/meet** onde externalwebfarmFQDN é o FQDN externo do Web farm que hospeda o conteúdo da reunião.</span><span class="sxs-lookup"><span data-stu-id="ff016-110">For conferencing, type a URL similar to the following: **https://externalwebfarmFQDN/meet** where externalwebfarmFQDN is the external FQDN of the web farm that hosts meeting content.</span></span> <span data-ttu-id="ff016-111">Esta URL deve exibir a página de solução de problemas para conferência.</span><span class="sxs-lookup"><span data-stu-id="ff016-111">This URL should display the troubleshooting page for conferencing.</span></span> <span data-ttu-id="ff016-112">Se preferir, confirme se sua URL simples para a conferência funciona corretamente.</span><span class="sxs-lookup"><span data-stu-id="ff016-112">Alternatively, confirm that your Simple URL for conferencing functions correctly.</span></span> <span data-ttu-id="ff016-113">Um exemplo de URL simples para a junção em conferência pode serhttps://meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ff016-113">An example Simple URL for the conference join might be https://meet.contoso.com</span></span>
    
      - <span data-ttu-id="ff016-114">Para expansão do grupo de distribuição, digite uma URL semelhante à seguinte **https://externalwebfarmFQDN/GroupExpansion/service.svc**:.</span><span class="sxs-lookup"><span data-stu-id="ff016-114">For distribution group expansion, type a URL similar to the following: **https://externalwebfarmFQDN/GroupExpansion/service.svc**.</span></span> <span data-ttu-id="ff016-115">O usuário deve receber um desafio HTTP porque a segurança de diretório no serviço de expansão do grupo de distribuição é configurada como autenticação do Windows por padrão.</span><span class="sxs-lookup"><span data-stu-id="ff016-115">The user should receive an HTTP challenge, because directory security on the distribution group expansion service is configured to Windows authentication by default.</span></span>
    
      - <span data-ttu-id="ff016-116">Para discagem, digite a URL simples semelhante à seguinte **https://externalwebfarmFQDN/dialin** em que externalwebfarmFQDN é o FQDN externo do Web farm que hospeda a página de discagem para conferência discada.</span><span class="sxs-lookup"><span data-stu-id="ff016-116">For dial-in, type the simple URL similar to the following **https://externalwebfarmFQDN/dialin** where externalwebfarmFQDN is the external FQDN of the web farm that hosts the dial-in page for dial-in conferencing.</span></span> <span data-ttu-id="ff016-117">O usuário deve ser direcionado para a página de discagem.</span><span class="sxs-lookup"><span data-stu-id="ff016-117">The user should be directed to the dial-in page.</span></span> <span data-ttu-id="ff016-118">Como alternativa, confirme se a sua URL simples de discagem funciona corretamente.</span><span class="sxs-lookup"><span data-stu-id="ff016-118">Alternatively, confirm that your Simple URL dial-in functions correctly.</span></span> <span data-ttu-id="ff016-119">Um exemplo de URL simples para discagem pode serhttps://dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ff016-119">An example Simple URL for dial-in might be https://dialin.contoso.com</span></span>
    
      - <span data-ttu-id="ff016-120">Para confirmar se a URL da descoberta automática está funcionando, https://lyncdiscoverdigite.</span><span class="sxs-lookup"><span data-stu-id="ff016-120">To confirm that the autodiscover URL is working, type https://lyncdiscover.</span></span> <span data-ttu-id="ff016-121">externaldomainFQDN.</span><span class="sxs-lookup"><span data-stu-id="ff016-121">externaldomainFQDN.</span></span> <span data-ttu-id="ff016-122">O navegador deve solicitar a abertura de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="ff016-122">The browser should prompt you to open a file.</span></span> <span data-ttu-id="ff016-123">Selecione bloco de notas para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="ff016-123">Select Notepad to open it.</span></span> <span data-ttu-id="ff016-124">Uma resposta típica seria semelhante a:</span><span class="sxs-lookup"><span data-stu-id="ff016-124">A typical response would be similar to:</span></span>
        
            {"AccessLocation":"External","Root":{"Links":[{"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/domain","token":"Domain"},
            {"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/user","token":"User"},
            {"href":"https:\/\/lyncweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/oauth\/user","token":"OAuth"}]}}

</div>

</div>

<span> </span>

</div>

</div>

</div>

