---
title: Expansor de Configurações de Máquina de Borda para Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: 'Para editar as propriedades de computadores servidores de borda como um único servidor de borda ou como computador membro em um pool de borda, você pode configurar definições de configuração de endereço IP e de nome do servidor:'
ms.openlocfilehash: ad8b763b2509d558a8de96e4fcda880934995e9e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33915280"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a><span data-ttu-id="3f795-103">Expansor de Configurações de Máquina de Borda para Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="3f795-103">Edge Machine Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="3f795-104">Para editar as propriedades de computadores servidores de borda como um único servidor de borda ou como computador membro em um pool de borda, você deve configurar as configurações de **nome do servidor e a configuração de endereço IP** :</span><span class="sxs-lookup"><span data-stu-id="3f795-104">To edit the properties for Edge Server computers as an single Edge Server or as member computers in an Edge pool, you configure **Server name and IP address configuration** settings:</span></span>
  
- <span data-ttu-id="3f795-105">**Nome interno ou FQDN**: digite o nome do computador, pois ele é referenciado no sistema de nome de domínio (DNS).</span><span class="sxs-lookup"><span data-stu-id="3f795-105">**Internal name or FQDN**: Type the name of the computer as it is referenced in the domain name system (DNS).</span></span> 
    
- <span data-ttu-id="3f795-106">**Endereço IPv4 interno**: digite o endereço IPv4 da placa de interface de rede interna (NIC) para este computador.</span><span class="sxs-lookup"><span data-stu-id="3f795-106">**Internal IPv4 address**: Type the IPv4 address of the internal network interface card (NIC) for this computer.</span></span>
    
- <span data-ttu-id="3f795-107">Configure o **serviço de borda de acesso** de **endereço IPv4 externo** associado a esse computador</span><span class="sxs-lookup"><span data-stu-id="3f795-107">You configure the **Access Edge service** **External IPv4 address** associated with this computer</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="3f795-108">Se você optou por usar um único endereço IP para a configuração do servidor de borda, você só poderá editar o endereço IPv4 externo para o serviço de borda de acesso.</span><span class="sxs-lookup"><span data-stu-id="3f795-108">If you selected to use a single IP address for the Edge Server configuration, you will only be able to edit the external IPv4 address for the Access Edge service.</span></span> <span data-ttu-id="3f795-109">Os outros serviços de borda irá compartilhar o mesmo endereço IPv4 como o serviço de borda de acesso.</span><span class="sxs-lookup"><span data-stu-id="3f795-109">The other Edge services will share the same IPv4 address as the Access Edge service.</span></span> 
  
- <span data-ttu-id="3f795-110">Se estiver disponível para editar, configure o **serviço de webconferência** de **endereço IPv4 externo** associado a esse computador</span><span class="sxs-lookup"><span data-stu-id="3f795-110">If available to edit, you configure the **Web Conferencing service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="3f795-111">Se estiver disponível para editar, configure o **uma / serviço de borda V** **endereço IPv4 externo** associado a esse computador</span><span class="sxs-lookup"><span data-stu-id="3f795-111">If available to edit, you configure the **A/V Edge service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="3f795-112">Se estiver disponível para editar, configure o **endereço IPv4 público habilitado por NAT** associado a esse computador.</span><span class="sxs-lookup"><span data-stu-id="3f795-112">If available to edit, you configure the **NAT-enabled public IPv4 address** associated with this computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="3f795-113">A propriedade de configuração para **endereço IPv4 público habilitado por NAT** só estará disponível para editar se você escolher fornecer conversão de endereço de rede (NAT) para A / serviço de borda V</span><span class="sxs-lookup"><span data-stu-id="3f795-113">The configuration property for **NAT-enabled public IPv4 address** will only be available to edit if you chose to provide network address translation (NAT) for the A/V Edge service</span></span>
  
  <span data-ttu-id="3f795-114">**OK** Aceita e confirma as alterações na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="3f795-114">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="3f795-115">**Cancelar** Descarta as alterações e fecha a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="3f795-115">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="3f795-116">**Ajuda** Exibe essa tela de ajuda.</span><span class="sxs-lookup"><span data-stu-id="3f795-116">**Help** Displays this help screen.</span></span>
  

