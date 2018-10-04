---
title: Expansor de configurações de serviço de mediação de Front-End do Lync Server 2010
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: 'Você editar as propriedades das configurações de gateway PSTN do servidor de mediação nessa caixa de diálogo. Defina as seguintes configurações:'
ms.openlocfilehash: a70ec5e569b60c28e8ec91e86d09ac5f5285ee00
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25371488"
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a><span data-ttu-id="e520a-104">Expansor de configurações de serviço de mediação de Front-End do Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="e520a-104">Front End Mediation Service Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="e520a-105">Você editar as propriedades das configurações de **gateway PSTN do servidor de mediação** nessa caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="e520a-105">You edit the properties of the **Mediation Server PSTN gateway** settings in this dialog.</span></span> <span data-ttu-id="e520a-106">Defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="e520a-106">You define the following settings:</span></span>
  
- <span data-ttu-id="e520a-107">Selecione o **servidor de mediação posicionado habilitado** se quiser colocar o servidor de mediação com esse servidor Front-End ou Front-End pools.</span><span class="sxs-lookup"><span data-stu-id="e520a-107">Select the **Collocated Mediation Server enabled** if you want to collocate the Mediation Server with this Front End Server or Front End pools.</span></span>
    
- <span data-ttu-id="e520a-108">**Portas de escuta**: definir as portas que o servidor de mediação escutará.</span><span class="sxs-lookup"><span data-stu-id="e520a-108">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="e520a-109">Você pode definir uma porta para segurança de camada de transporte ou **TLS** ou **TCP**, ou o protocolo de controle de transporte.</span><span class="sxs-lookup"><span data-stu-id="e520a-109">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="e520a-110">Para a entrada de porta para TCP esteja disponível, você deve selecionar a caixa de seleção para **Habilitar TCP porta**.</span><span class="sxs-lookup"><span data-stu-id="e520a-110">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="e520a-111">Consulte as configurações de documentação e configuração de seu gateway PSTN (rede) telefônica pública comutada para determinar se você precisa habilitar e definir valores de portas TLS, TCP ou ambos.</span><span class="sxs-lookup"><span data-stu-id="e520a-111">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="e520a-112">O TLS é um protocolo mais seguro, usando certificados para criptografar o tráfego entre o servidor de mediação e o gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="e520a-112">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="e520a-113">Nem todos os gateways PSTN suportam TLS.</span><span class="sxs-lookup"><span data-stu-id="e520a-113">Not all PSTN gateways support TLS.</span></span> 
  
- <span data-ttu-id="e520a-114">Uma listagem do **Tronco** associado atualmente e existente (ou seja, Troncos SIP), **Gateway** (Gateway PSTN ou IP-PBX) e **Site** (site configurado para o tronco e gateway).</span><span class="sxs-lookup"><span data-stu-id="e520a-114">A listing of currently associated and existing **Trunk** (that is, Session Initiation Protocol (SIP) Trunks), **Gateway** (PSTN gateway or IP-PBX) and **Site** (configured site for the trunk and gateway).</span></span>
    
- <span data-ttu-id="e520a-p105">Selecione um Tronco, Gateway e Site e clique em **Tornar Padrão** para definir a seleção como padrão para esse serviço de Mediação. Selecione o padrão atual e clique em **Desfazer Padrão** para remover a seleção como o padrão atual. Em seguida, selecione um novo o padrão e clique em **Tornar Padrão**.</span><span class="sxs-lookup"><span data-stu-id="e520a-p105">You select a Trunk, Gateway and Site and click **Make Default** to set the selection as the default for this Mediation service. You select the current default and click **Unmake Default** to remove the selection as the current default. You then select a new default and click **Make Default**.</span></span>
    
  <span data-ttu-id="e520a-118">**OK** Aceita e confirma as alterações na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="e520a-118">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="e520a-119">**Cancelar** Descarta as alterações e fecha a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="e520a-119">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="e520a-120">**Ajuda** Exibe essa tela de ajuda.</span><span class="sxs-lookup"><span data-stu-id="e520a-120">**Help** Displays this help screen.</span></span>
  

