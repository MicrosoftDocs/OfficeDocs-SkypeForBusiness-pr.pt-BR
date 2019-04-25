---
title: Atualizar registros de DNS SRV
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Para concluir este procedimento, você deve estar conectado ao servidor ou domínio como membro do grupo Administradores de domínio ou membro do grupo DnsAdmins.
ms.openlocfilehash: 5cdf98d065abbb57b3cb654c8b770f8f1f87500c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231379"
---
# <a name="update-dns-srv-records"></a><span data-ttu-id="f3afb-103">Atualizar registros de DNS SRV</span><span class="sxs-lookup"><span data-stu-id="f3afb-103">Update DNS SRV records</span></span>

<span data-ttu-id="f3afb-104">Para concluir este procedimento, você deve estar conectado ao servidor ou domínio como membro do grupo Administradores de domínio ou membro do grupo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="f3afb-104">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
<span data-ttu-id="f3afb-105">Este tópico descreve como atualizar os registros de sistema de nome de domínio (DNS) após a migração para Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f3afb-105">This topic describes how to update the Domain Name System (DNS) records after migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="f3afb-106">Depois que todos os usuários foram movidos para Skype para Business Server 2019, mas antes que o pool herdado ou diretor é desativado, você deve atualizar os registros DNS SRV no DNS interno para cada domínio SIP.</span><span class="sxs-lookup"><span data-stu-id="f3afb-106">After all users have been moved to Skype for Business Server 2019, but before the legacy pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="f3afb-107">Este procedimento pressupõe que o DNS interno possui zonas para os domínios de usuário do SIP.</span><span class="sxs-lookup"><span data-stu-id="f3afb-107">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>
  
## <a name="to-configure-a-dns-srv-record"></a><span data-ttu-id="f3afb-108">Para configurar um registro SRV de DNS</span><span class="sxs-lookup"><span data-stu-id="f3afb-108">To configure a DNS SRV record</span></span>

1. <span data-ttu-id="f3afb-109">No servidor DNS, clique em **Iniciar**, clique em **Ferramentas administrativas**e clique em **DNS**.</span><span class="sxs-lookup"><span data-stu-id="f3afb-109">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="f3afb-110">Na árvore de console do domínio SIP, expanda **Zonas de pesquisa direta**, expanda o domínio SIP no qual Skype para Business Server 2019 está instalado e navegue até a configuração **TCP** .</span><span class="sxs-lookup"><span data-stu-id="f3afb-110">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Skype for Business Server 2019 is installed, and navigate to the **_tcp** setting.</span></span> 
    
3. <span data-ttu-id="f3afb-111">No painel direito, clique com o botão **sipinternaltls** e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="f3afb-111">In the right pane, right-click **_sipinternaltls** and select **Properties**.</span></span>
    
4. <span data-ttu-id="f3afb-112">Em **Host que oferece este serviço**, atualize o host FQDN para apontar para o Skype para Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="f3afb-112">In **Host offering this service**, update the host FQDN to point to the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="f3afb-113">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3afb-113">Click **OK**.</span></span>
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a><span data-ttu-id="f3afb-114">Para verificar se o FQDN do pool de Front-End ou servidor Standard Edition pode ser resolvido</span><span class="sxs-lookup"><span data-stu-id="f3afb-114">To verify that the FQDN of the Front End pool or Standard Edition server can be resolved</span></span>

1. <span data-ttu-id="f3afb-115">Faça logon em um computador cliente no domínio.</span><span class="sxs-lookup"><span data-stu-id="f3afb-115">Log on to a client computer in the domain.</span></span>
    
2. <span data-ttu-id="f3afb-116">Clique em  \*\*Iniciar \*\* e em  \*\*Executar \*\*.</span><span class="sxs-lookup"><span data-stu-id="f3afb-116">Click **Start**, and then click **Run**.</span></span>
    
3. <span data-ttu-id="f3afb-117">Na caixa **Abrir** , digite cmd e clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="f3afb-117">In the **Open** box, type cmd, and then click **OK**.</span></span>
    
4. <span data-ttu-id="f3afb-118">No prompt de comando, digite nslookup _ \<FQDN do pool de Front-End\> _ ou _ \<FQDN do servidor Standard Edition\>_, e pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="f3afb-118">At the command prompt, type nslookup _\<FQDN of the Front End pool\>_ or  _\<FQDN of the Standard Edition server\>_, and then press ENTER.</span></span>
    
5. <span data-ttu-id="f3afb-119">Verifique se você recebe uma resposta que resolve o endereço IP apropriado para o FQDN.</span><span class="sxs-lookup"><span data-stu-id="f3afb-119">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>
    

