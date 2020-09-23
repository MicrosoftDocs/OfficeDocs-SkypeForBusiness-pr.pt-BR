---
title: Expansor de Configurações de Máquina de Borda para Lync Server 2010
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
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: 'Para editar as propriedades dos computadores do servidor de borda como um único servidor de borda ou como computadores membro em um pool de borda, você define o nome do servidor e as definições de configuração do endereço IP:'
ms.openlocfilehash: eb2135391791fdb915578fe9938329b56c85908c
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218922"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a><span data-ttu-id="92cc0-103">Expansor de Configurações de Máquina de Borda para Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="92cc0-103">Edge Machine Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="92cc0-104">Para editar as propriedades dos computadores do servidor de borda como um único servidor de borda ou como computadores membro em um pool de borda, você define o **nome do servidor e** as definições de configuração do endereço IP:</span><span class="sxs-lookup"><span data-stu-id="92cc0-104">To edit the properties for Edge Server computers as an single Edge Server or as member computers in an Edge pool, you configure **Server name and IP address configuration** settings:</span></span>
  
- <span data-ttu-id="92cc0-105">**Nome interno ou FQDN**: digite o nome do computador da forma como ele é chamado pelo DNS.</span><span class="sxs-lookup"><span data-stu-id="92cc0-105">**Internal name or FQDN**: Type the name of the computer as it is referenced in the domain name system (DNS).</span></span> 
    
- <span data-ttu-id="92cc0-106">**Endereço IPv4 interno**: digite o endereço IPv4 da placa de interface de rede (NIC) interna desse computador.</span><span class="sxs-lookup"><span data-stu-id="92cc0-106">**Internal IPv4 address**: Type the IPv4 address of the internal network interface card (NIC) for this computer.</span></span>
    
- <span data-ttu-id="92cc0-107">Você configura o **Access Edge service** **endereço IPv4 externo** do serviço de borda de acesso associado a este computador</span><span class="sxs-lookup"><span data-stu-id="92cc0-107">You configure the **Access Edge service** **External IPv4 address** associated with this computer</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="92cc0-108">Se você optou por usar um único endereço IP para a configuração do servidor de borda, só poderá editar o endereço IPv4 externo do serviço de borda de acesso.</span><span class="sxs-lookup"><span data-stu-id="92cc0-108">If you selected to use a single IP address for the Edge Server configuration, you will only be able to edit the external IPv4 address for the Access Edge service.</span></span> <span data-ttu-id="92cc0-109">Os outros serviços de borda compartilharão o mesmo endereço IPv4 que o serviço de borda de acesso.</span><span class="sxs-lookup"><span data-stu-id="92cc0-109">The other Edge services will share the same IPv4 address as the Access Edge service.</span></span> 
  
- <span data-ttu-id="92cc0-110">Se estiver disponível para edição, configure o **serviço de Webconferência** do **endereço IPv4 externo** associado a este computador</span><span class="sxs-lookup"><span data-stu-id="92cc0-110">If available to edit, you configure the **Web Conferencing service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="92cc0-111">Se estiver disponível para edição, configure o **endereço IPv4 externo** do **serviço de borda a/V** associado a este computador</span><span class="sxs-lookup"><span data-stu-id="92cc0-111">If available to edit, you configure the **A/V Edge service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="92cc0-112">Se estiver disponível para editar, configure o **Endereço IPv4 público habilitado por NAT** associado a esse computador.</span><span class="sxs-lookup"><span data-stu-id="92cc0-112">If available to edit, you configure the **NAT-enabled public IPv4 address** associated with this computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="92cc0-113">A propriedade de configuração para o **endereço IPv4 público habilitado para NAT** só estará disponível para edição se você optar por fornecer conversão de endereço de rede (NAT) para o serviço de borda a/V</span><span class="sxs-lookup"><span data-stu-id="92cc0-113">The configuration property for **NAT-enabled public IPv4 address** will only be available to edit if you chose to provide network address translation (NAT) for the A/V Edge service</span></span>
  
  <span data-ttu-id="92cc0-114">**OK** aceita e confirma as alterações na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="92cc0-114">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="92cc0-115">**Cancelar** descarta as alterações e fecha a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="92cc0-115">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="92cc0-116">**Ajuda** exibe essa tela de ajuda.</span><span class="sxs-lookup"><span data-stu-id="92cc0-116">**Help** Displays this help screen.</span></span>
  

