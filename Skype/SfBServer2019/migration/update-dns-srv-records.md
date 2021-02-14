---
title: Atualizar registros de DNS SRV
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Para concluir com êxito este procedimento, você deverá estar conectado no servidor ou domínio como um membro do grupo de Administradores de Domínio ou membro do grupo DnsAdmins.
ms.openlocfilehash: 26bb80618868a2bec03d1de32f6c010869b8cf8c
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753263"
---
# <a name="update-dns-srv-records"></a><span data-ttu-id="5967d-103">Atualizar registros de DNS SRV</span><span class="sxs-lookup"><span data-stu-id="5967d-103">Update DNS SRV records</span></span>

<span data-ttu-id="5967d-104">Para concluir com êxito este procedimento, você deverá estar conectado no servidor ou domínio como um membro do grupo de Administradores de Domínio ou membro do grupo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="5967d-104">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
<span data-ttu-id="5967d-105">Este tópico descreve como atualizar os registros dns após migrar para o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5967d-105">This topic describes how to update the Domain Name System (DNS) records after migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="5967d-106">Depois que todos os usuários tiverem sido movidos para o Skype for Business Server 2019, mas antes que o pool ou Diretor herdado seja desativado, você deve atualizar os registros SRV dns em seu DNS interno para cada domínio SIP.</span><span class="sxs-lookup"><span data-stu-id="5967d-106">After all users have been moved to Skype for Business Server 2019, but before the legacy pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="5967d-107">Este procedimento supõe que o DNS interno tem zonas para os domínios de usuário do SIP.</span><span class="sxs-lookup"><span data-stu-id="5967d-107">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>
  
## <a name="to-configure-a-dns-srv-record"></a><span data-ttu-id="5967d-108">Para configurar um registro SRV de DNS</span><span class="sxs-lookup"><span data-stu-id="5967d-108">To configure a DNS SRV record</span></span>

1. <span data-ttu-id="5967d-109">No servidor DNS, clique em **Iniciar**, clique em **Ferramentas Administrativas** e em **DNS**.</span><span class="sxs-lookup"><span data-stu-id="5967d-109">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="5967d-110">Na árvore de console do seu domínio SIP, expanda **Zonas** de Busca Encaminhar, expanda o domínio SIP no qual o Skype for Business Server 2019 está instalado e navegue até a configuração **de** _tcp.</span><span class="sxs-lookup"><span data-stu-id="5967d-110">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Skype for Business Server 2019 is installed, and navigate to the **_tcp** setting.</span></span> 
    
3. <span data-ttu-id="5967d-111">No painel direito, clique com o botão direito do mouse **_sipinternaltls** e selecione **Propriedades.**</span><span class="sxs-lookup"><span data-stu-id="5967d-111">In the right pane, right-click **_sipinternaltls** and select **Properties**.</span></span>
    
4. <span data-ttu-id="5967d-112">No **Host que oferece esse serviço,** atualize o FQDN do host para apontar para o pool do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5967d-112">In **Host offering this service**, update the host FQDN to point to the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="5967d-113">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="5967d-113">Click **OK**.</span></span>
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a><span data-ttu-id="5967d-114">Para verificar se o FQDN do servidor Standard Edition ou pool de Front-Ends pode ser resolvido</span><span class="sxs-lookup"><span data-stu-id="5967d-114">To verify that the FQDN of the Front End pool or Standard Edition server can be resolved</span></span>

1. <span data-ttu-id="5967d-115">Faça logon em um computador cliente no domínio.</span><span class="sxs-lookup"><span data-stu-id="5967d-115">Log on to a client computer in the domain.</span></span>
    
2. <span data-ttu-id="5967d-116">Clique em **Iniciar** e em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="5967d-116">Click **Start**, and then click **Run**.</span></span>
    
3. <span data-ttu-id="5967d-117">Na caixa **Abrir,** digite cmd e clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="5967d-117">In the **Open** box, type cmd, and then click **OK**.</span></span>
    
4. <span data-ttu-id="5967d-118">No prompt de comando, digite nslookup _\<FQDN of the Front End pool\>_ ou  _\<FQDN of the Standard Edition server\>_ e pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="5967d-118">At the command prompt, type nslookup _\<FQDN of the Front End pool\>_ or  _\<FQDN of the Standard Edition server\>_, and then press ENTER.</span></span>
    
5. <span data-ttu-id="5967d-119">Verifique se recebeu uma resposta que resolve para o endereço IP apropriado para o FQDN.</span><span class="sxs-lookup"><span data-stu-id="5967d-119">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>
    

