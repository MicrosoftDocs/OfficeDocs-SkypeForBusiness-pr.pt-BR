---
title: Expansor de Configurações FQDN de Servidor de Borda para Lync Server 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 'Para definir as propriedades em Configurações externas, configure o seguinte:'
ms.openlocfilehash: 6075fab9dbc820b725beec8be4a674a828b4c7d1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807091"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a><span data-ttu-id="92c39-103">Expansor de Configurações FQDN de Servidor de Borda para Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="92c39-103">Edge Server FQDN Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="92c39-104">Para definir as propriedades em **Configurações externas**, configure o seguinte:</span><span class="sxs-lookup"><span data-stu-id="92c39-104">To define the properties under **External settings**, configure the following:</span></span>
  
<span data-ttu-id="92c39-105">Marque a caixa de seleção **Habilitar FQDN e endereço IP separados para webconferência e A/V** se quiser definir FQDN de Pool e endereços IP distintos para webconferência e áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="92c39-105">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to define distinct Pool FQDN and IP addresses for web conferencing and audio/video.</span></span>
  
> [!NOTE]
> <span data-ttu-id="92c39-106">Se você optar por não marcar a caixa de seleção para FQDN e endereços IP separados, deverá fornecer portas distintas para cada um dos três serviços fornecidos pelo Servidor de Borda.</span><span class="sxs-lookup"><span data-stu-id="92c39-106">If you choose to not select the check box for separate FQDN and IP addresses, you must provide distinct ports for each of the three services provided by the Edge Server.</span></span> <span data-ttu-id="92c39-107">O único nome de domínio totalmente qualificado que deve ser configurada é o FQDN associado ao serviço de Borda de Acesso.</span><span class="sxs-lookup"><span data-stu-id="92c39-107">The only fully qualified domain name that is to configure is the FQDN associated with the Access Edge service.</span></span> 
  
<span data-ttu-id="92c39-108">Marque a caixa de seleção serviço de Borda **A/V** é habilitada para NAT se você quiser que o serviço de Borda A/V use um endereço IP nat (conversão de endereço de rede) e configuração.</span><span class="sxs-lookup"><span data-stu-id="92c39-108">Select the **A/V Edge service is NAT enabled** check box if you want the A/V Edge service to use a network address translation (NAT) IP address and configuration.</span></span>
  
<span data-ttu-id="92c39-109">Para os serviços de Borda habilitados, digite um **FQDN de Pool** e uma porta em **Portas**</span><span class="sxs-lookup"><span data-stu-id="92c39-109">For the enabled Edge services, you type a **Pool FQDN** and a port under **Ports**</span></span>
  
- <span data-ttu-id="92c39-110">Defina o FQDN do Pool dos **Serviços de Borda de Acesso** e uma porta que identifique exclusivamente o serviço.</span><span class="sxs-lookup"><span data-stu-id="92c39-110">Define the **Access Edge service** Pool FQDN and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="92c39-111">Defina o FQDN do Pool do **Serviço de Borda de Webconferência** (se Habilitar FQDN e endereço IP separados para webconferência e A/V não estiver selecionado) e uma porta que identifique exclusivamente o serviço</span><span class="sxs-lookup"><span data-stu-id="92c39-111">Define the **Web Conferencing Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="92c39-112">Defina o FQDN do Pool do **Serviço de Borda de A/V** (se Habilitar FQDN e endereço IP separados para webconferência e A/V não estiver selecionado) e uma porta que identifique exclusivamente o serviço</span><span class="sxs-lookup"><span data-stu-id="92c39-112">Define the **A/V Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
  <span data-ttu-id="92c39-113">**OK** aceita e confirma as alterações na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="92c39-113">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="92c39-114">**Cancelar** descarta as alterações e fecha a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="92c39-114">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="92c39-115">**Ajuda** exibe essa tela de ajuda.</span><span class="sxs-lookup"><span data-stu-id="92c39-115">**Help** Displays this help screen.</span></span>
  

