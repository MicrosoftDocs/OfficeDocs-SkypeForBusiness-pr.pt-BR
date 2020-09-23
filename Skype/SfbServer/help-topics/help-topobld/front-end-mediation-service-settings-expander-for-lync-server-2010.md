---
title: Expansor de Configurações do Serviço de Mediação de Front End para Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: 'Edite as propriedades das configurações do Gateway PSTN do Servidor de Mediação nesta caixa de diálogo. Defina as seguintes configurações:'
ms.openlocfilehash: 37baf89b6100528c1485f939f69e20c697803123
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217722"
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a><span data-ttu-id="45df9-104">Expansor de Configurações do Serviço de Mediação de Front End para Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="45df9-104">Front End Mediation Service Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="45df9-105">Edite as propriedades das configurações do **Gateway PSTN do Servidor de Mediação** nesta caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="45df9-105">You edit the properties of the **Mediation Server PSTN gateway** settings in this dialog.</span></span> <span data-ttu-id="45df9-106">Defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="45df9-106">You define the following settings:</span></span>
  
- <span data-ttu-id="45df9-107">Selecione o **servidor de mediação posicionado habilitado** se você quiser colocar o servidor de mediação com este servidor front-end ou pools de front-ends.</span><span class="sxs-lookup"><span data-stu-id="45df9-107">Select the **Collocated Mediation Server enabled** if you want to collocate the Mediation Server with this Front End Server or Front End pools.</span></span>
    
- <span data-ttu-id="45df9-108">**Portas de escuta**: defina as portas nas quais o servidor de mediação escutará.</span><span class="sxs-lookup"><span data-stu-id="45df9-108">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="45df9-109">É possível definir uma porta para **TLS**, ou transport layer security, ou para **TCP**, ou transport control protocol.</span><span class="sxs-lookup"><span data-stu-id="45df9-109">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="45df9-110">Para a entrada da porta TCP ficar disponível, é necessário marcar a caixa de seleção **Habilitar porta TCP**.</span><span class="sxs-lookup"><span data-stu-id="45df9-110">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="45df9-111">Consulte a documentação e as configurações de seu gateway PSTN (rede telefônica pública comutada) para determinar se precisa habilitar e definir os valores de porta TLS, TCP ou ambos.</span><span class="sxs-lookup"><span data-stu-id="45df9-111">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="45df9-112">O TLS é um protocolo mais seguro, usando certificados para criptografar o tráfego entre o servidor de mediação e o gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="45df9-112">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="45df9-113">Nem todos os gateways PSTN suportam TLS.</span><span class="sxs-lookup"><span data-stu-id="45df9-113">Not all PSTN gateways support TLS.</span></span> 
  
- <span data-ttu-id="45df9-114">Uma listagem do **Tronco** associado atualmente e existente (ou seja, Troncos SIP [Session Initiation Protocol]), **Gateway** (Gateway PSTN ou IP-PBX) e **Site** (site configurado para o tronco e gateway).</span><span class="sxs-lookup"><span data-stu-id="45df9-114">A listing of currently associated and existing **Trunk** (that is, Session Initiation Protocol (SIP) Trunks), **Gateway** (PSTN gateway or IP-PBX) and **Site** (configured site for the trunk and gateway).</span></span>
    
- <span data-ttu-id="45df9-p105">Selecione um Tronco, Gateway e Site e clique em **Tornar Padrão** para definir a seleção como padrão para esse serviço de Mediação. Selecione o padrão atual e clique em **Desfazer Padrão** para remover a seleção como o padrão atual. Em seguida, você seleciona um novo o padrão e clica em **Tornar Padrão**.</span><span class="sxs-lookup"><span data-stu-id="45df9-p105">You select a Trunk, Gateway and Site and click **Make Default** to set the selection as the default for this Mediation service. You select the current default and click **Unmake Default** to remove the selection as the current default. You then select a new default and click **Make Default**.</span></span>
    
  <span data-ttu-id="45df9-118">**OK** aceita e confirma as alterações na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="45df9-118">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="45df9-119">**Cancelar** descarta as alterações e fecha a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="45df9-119">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="45df9-120">**Ajuda** exibe essa tela de ajuda.</span><span class="sxs-lookup"><span data-stu-id="45df9-120">**Help** Displays this help screen.</span></span>
  

