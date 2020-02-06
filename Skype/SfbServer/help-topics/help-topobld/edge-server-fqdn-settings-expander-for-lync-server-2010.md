---
title: Expansor de Configurações FQDN de Servidor de Borda para Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 'Para definir as propriedades em configurações externas, configure o seguinte:'
ms.openlocfilehash: 95e55625ec698d8762832e812a79547daf4d2bcf
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820053"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a><span data-ttu-id="adca5-103">Expansor de Configurações FQDN de Servidor de Borda para Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="adca5-103">Edge Server FQDN Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="adca5-104">Para definir as propriedades em **configurações externas**, configure o seguinte:</span><span class="sxs-lookup"><span data-stu-id="adca5-104">To define the properties under **External settings**, configure the following:</span></span>
  
<span data-ttu-id="adca5-105">Marque a caixa de seleção **habilitar FQDN e endereço IP separados para Webconferência e A/V,** se você quiser definir endereços IP e FQDN de pool distintos para Webconferência e áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="adca5-105">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to define distinct Pool FQDN and IP addresses for web conferencing and audio/video.</span></span>
  
> [!NOTE]
> <span data-ttu-id="adca5-106">Se você optar por não marcar a caixa de seleção para endereços IP e FQDN separados, será necessário fornecer portas distintas para cada um dos três serviços fornecidos pelo servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="adca5-106">If you choose to not select the check box for separate FQDN and IP addresses, you must provide distinct ports for each of the three services provided by the Edge Server.</span></span> <span data-ttu-id="adca5-107">O único nome de domínio totalmente qualificado que é configurado é o FQDN associado ao serviço de borda de acesso.</span><span class="sxs-lookup"><span data-stu-id="adca5-107">The only fully qualified domain name that is to configure is the FQDN associated with the Access Edge service.</span></span> 
  
<span data-ttu-id="adca5-108">Marque a caixa de seleção o **serviço de borda a/v está habilitado para NAT** se você quiser que o serviço de borda a/v Use um endereço IP e uma configuração de NAT (conversão de endereços de rede).</span><span class="sxs-lookup"><span data-stu-id="adca5-108">Select the **A/V Edge service is NAT enabled** check box if you want the A/V Edge service to use a network address translation (NAT) IP address and configuration.</span></span>
  
<span data-ttu-id="adca5-109">Para os serviços de borda habilitados, digite um **FQDN do pool** e uma porta em **portas**</span><span class="sxs-lookup"><span data-stu-id="adca5-109">For the enabled Edge services, you type a **Pool FQDN** and a port under **Ports**</span></span>
  
- <span data-ttu-id="adca5-110">Defina o FQDN do pool de **serviços de borda de acesso** e uma porta que identifique exclusivamente o serviço.</span><span class="sxs-lookup"><span data-stu-id="adca5-110">Define the **Access Edge service** Pool FQDN and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="adca5-111">Defina o FQDN do pool de **serviços de borda de Webconferência** (se habilitar o FQDN e o endereço IP separados para Webconferência e a/V não estiver selecionado) e uma porta que identifique exclusivamente o serviço.</span><span class="sxs-lookup"><span data-stu-id="adca5-111">Define the **Web Conferencing Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="adca5-112">Defina o FQDN do pool de **serviços de borda a/V** (se habilitar FQDN e o endereço IP separados para Webconferência e a/V não estiver selecionado) e uma porta que identifique exclusivamente o serviço.</span><span class="sxs-lookup"><span data-stu-id="adca5-112">Define the **A/V Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
  <span data-ttu-id="adca5-113">**OK** Aceita e confirma as alterações na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="adca5-113">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="adca5-114">**Cancelar** Descarta as alterações e fecha a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="adca5-114">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="adca5-115">**Ajuda** Exibe essa tela de ajuda.</span><span class="sxs-lookup"><span data-stu-id="adca5-115">**Help** Displays this help screen.</span></span>
  

