---
title: Atualizar registros de DNS SRV
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Para concluir esse procedimento com êxito, você deve estar conectado ao servidor ou ao domínio como membro do grupo Domain admins ou de um membro do grupo DnsAdmins.
ms.openlocfilehash: ef77f491efd090949ff5dd6b653dd3cd6ea1cde7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812769"
---
# <a name="update-dns-srv-records"></a><span data-ttu-id="3b1f5-103">Atualizar registros de DNS SRV</span><span class="sxs-lookup"><span data-stu-id="3b1f5-103">Update DNS SRV records</span></span>

<span data-ttu-id="3b1f5-104">Para concluir esse procedimento com êxito, você deve estar conectado ao servidor ou ao domínio como membro do grupo Domain admins ou de um membro do grupo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="3b1f5-104">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
<span data-ttu-id="3b1f5-105">Este tópico descreve como atualizar os registros DNS (sistema de nomes de domínio) após a migração para o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="3b1f5-105">This topic describes how to update the Domain Name System (DNS) records after migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="3b1f5-106">Depois que todos os usuários tiverem sido movidos para o Skype for Business Server 2019, mas antes que o pool ou o diretor herdado seja encerrado, você deve atualizar os registros SRV DNS no seu DNS interno para cada domínio SIP.</span><span class="sxs-lookup"><span data-stu-id="3b1f5-106">After all users have been moved to Skype for Business Server 2019, but before the legacy pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="3b1f5-107">Este procedimento pressupõe que o seu DNS interno tem zonas para seus domínios de usuário SIP.</span><span class="sxs-lookup"><span data-stu-id="3b1f5-107">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>
  
## <a name="to-configure-a-dns-srv-record"></a><span data-ttu-id="3b1f5-108">Para configurar um registro SRV DNS</span><span class="sxs-lookup"><span data-stu-id="3b1f5-108">To configure a DNS SRV record</span></span>

1. <span data-ttu-id="3b1f5-109">No servidor DNS, clique em **Iniciar**, clique em **Ferramentas administrativas**e, em seguida, clique em **DNS**.</span><span class="sxs-lookup"><span data-stu-id="3b1f5-109">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="3b1f5-110">Na árvore de console do seu domínio SIP, expanda **zonas de pesquisa direta**, expanda o domínio SIP no qual o Skype for Business Server 2019 está instalado e navegue até a configuração **_tcp** .</span><span class="sxs-lookup"><span data-stu-id="3b1f5-110">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Skype for Business Server 2019 is installed, and navigate to the **_tcp** setting.</span></span> 
    
3. <span data-ttu-id="3b1f5-111">No painel direito, clique com o botão direito do mouse em **_sipinternaltls** e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="3b1f5-111">In the right pane, right-click **_sipinternaltls** and select **Properties**.</span></span>
    
4. <span data-ttu-id="3b1f5-112">Em **host oferecendo esse serviço**, atualize o FQDN do host para apontar para o pool do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="3b1f5-112">In **Host offering this service**, update the host FQDN to point to the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="3b1f5-113">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3b1f5-113">Click **OK**.</span></span>
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a><span data-ttu-id="3b1f5-114">Para verificar se o FQDN do servidor de front-end ou do servidor Standard Edition pode ser resolvido</span><span class="sxs-lookup"><span data-stu-id="3b1f5-114">To verify that the FQDN of the Front End pool or Standard Edition server can be resolved</span></span>

1. <span data-ttu-id="3b1f5-115">Faça logon em um computador cliente no domínio.</span><span class="sxs-lookup"><span data-stu-id="3b1f5-115">Log on to a client computer in the domain.</span></span>
    
2. <span data-ttu-id="3b1f5-116">Clique em  \*\*Iniciar \*\* e em  \*\*Executar \*\*.</span><span class="sxs-lookup"><span data-stu-id="3b1f5-116">Click **Start**, and then click **Run**.</span></span>
    
3. <span data-ttu-id="3b1f5-117">Na caixa **abrir** , digite cmd e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3b1f5-117">In the **Open** box, type cmd, and then click **OK**.</span></span>
    
4. <span data-ttu-id="3b1f5-118">No prompt de comando, digite _ \<FQDN do nslookup do pool\> de front-end_ ou _ \<FQDN do servidor\>Standard Edition_e, em seguida, pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="3b1f5-118">At the command prompt, type nslookup _\<FQDN of the Front End pool\>_ or  _\<FQDN of the Standard Edition server\>_, and then press ENTER.</span></span>
    
5. <span data-ttu-id="3b1f5-119">Verifique se você recebe uma resposta que é resolvida para o endereço IP apropriado para o FQDN.</span><span class="sxs-lookup"><span data-stu-id="3b1f5-119">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>
    

