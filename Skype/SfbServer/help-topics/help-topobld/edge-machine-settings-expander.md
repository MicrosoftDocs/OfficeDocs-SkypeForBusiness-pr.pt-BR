---
title: Expansor de Configurações de Máquina de Borda
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
description: 'Para editar as propriedades de um servidor em um pool de servidores de borda, faça o seguinte:'
ms.openlocfilehash: 997aaafdc4b2193f1f89e433a8c64e88699cecbe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33915175"
---
# <a name="edge-machine-settings-expander"></a><span data-ttu-id="e204f-103">Expansor de Configurações de Máquina de Borda</span><span class="sxs-lookup"><span data-stu-id="e204f-103">Edge Machine Settings Expander</span></span>
 
<span data-ttu-id="e204f-104">Para editar as propriedades de um servidor em um pool de servidores de borda, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e204f-104">To edit the properties for a server in a pool of Edge Servers, do the following:</span></span>
  
<span data-ttu-id="e204f-105">O **nome interno ou FQDN** pode ser alterada editando o nome de domínio totalmente qualificado (FQDN).</span><span class="sxs-lookup"><span data-stu-id="e204f-105">The **Internal name or FQDN** can be changed by editing the fully qualified domain name (FQDN).</span></span> <span data-ttu-id="e204f-106">O FQDN deve coincidir com o host (A) registro do sistema de nome de domínio (DNS) e o nome da entidade do certificado atribuído ao servidor da interface de rede de borda interna.</span><span class="sxs-lookup"><span data-stu-id="e204f-106">The FQDN must match the Domain Name System (DNS) host (A) record, and the subject name of the certificate assigned to the server for the internal Edge network interface.</span></span> <span data-ttu-id="e204f-107">O valor de **endereço IP interno** define o endereço IP atribuído a interface de rede que é definida como uma rede interna, em relação ao design da rede de perímetro.</span><span class="sxs-lookup"><span data-stu-id="e204f-107">The value of **Internal IP address** defines the IP address that is assigned the network interface that is defined as an internal network, relative to the perimeter network design.</span></span>
  
<span data-ttu-id="e204f-108">As próximas três seções da caixa de diálogo definem os endereços IP para a configuração externa do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="e204f-108">The next three sections of the dialog define the IP addresses for the external configuration of this Edge Server.</span></span> <span data-ttu-id="e204f-109">A capacidade de alterar os endereços IP é afetada pela definição **FQDN de habilitar separado e endereço IP para Webconferência e A / V** nas configurações de propriedades no servidor de Borda nível do pool.</span><span class="sxs-lookup"><span data-stu-id="e204f-109">The ability to change the IP addresses is affected by the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the Properties settings at the Edge Server pool level.</span></span>
  
## <a name="sip-access"></a><span data-ttu-id="e204f-110">Acesso SIP</span><span class="sxs-lookup"><span data-stu-id="e204f-110">SIP Access</span></span>

<span data-ttu-id="e204f-111">Edite o endereço IP externo que é atribuído à interface de rede para acesso de protocolo de iniciação de sessão (SIP).</span><span class="sxs-lookup"><span data-stu-id="e204f-111">Edit the external IP address that is assigned to the network interface for Session Initiation Protocol (SIP) access.</span></span> <span data-ttu-id="e204f-112">Esse endereço IP pode ser um endereço IP público ou um endereço no intervalo de endereços IP privado.</span><span class="sxs-lookup"><span data-stu-id="e204f-112">This IP address can either be a public IP address or an address in the private IP address range.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e204f-113">Se a configuração **FQDN de habilitar separado e endereço IP para Webconferência e A / V** no pool páginaconfigurações estiver habilitada, somente o endereço IP para acesso do SIP estará disponível para edição.</span><span class="sxs-lookup"><span data-stu-id="e204f-113">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the pool settings page is enabled, only the IP address for SIP access will be available for editing.</span></span>
  
## <a name="web-conferencing"></a><span data-ttu-id="e204f-114">Webconferência</span><span class="sxs-lookup"><span data-stu-id="e204f-114">Web Conferencing</span></span>

<span data-ttu-id="e204f-115">Edite o endereço IP externo que é atribuído à interface de rede para webconferências.</span><span class="sxs-lookup"><span data-stu-id="e204f-115">Edit the external IP address that is assigned to the network interface for web conferencing.</span></span> <span data-ttu-id="e204f-116">Esse endereço IP pode ser um endereço IP público ou um endereço no intervalo de endereços IP privado.</span><span class="sxs-lookup"><span data-stu-id="e204f-116">This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
## <a name="audiovideo"></a><span data-ttu-id="e204f-117">Áudio/vídeo</span><span class="sxs-lookup"><span data-stu-id="e204f-117">Audio/Video</span></span>

<span data-ttu-id="e204f-118">Editar o endereço IP externo que é atribuído à interface de rede para áudio/vídeo (A / V).</span><span class="sxs-lookup"><span data-stu-id="e204f-118">Edit the external IP address that is assigned to the network interface for audio/video (A/V).</span></span> <span data-ttu-id="e204f-119">Esse endereço IP pode ser um endereço IP público ou um endereço no intervalo de endereços IP privado.</span><span class="sxs-lookup"><span data-stu-id="e204f-119">This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
<span data-ttu-id="e204f-120">A configuração **endereço IP público do usado habilitado para NAT** é o endereço público usado pela interface externa para ambos os A / V rede interface ou o servidor de borda em geral.</span><span class="sxs-lookup"><span data-stu-id="e204f-120">The setting for **NAT enabled public IP address used** is the public address used by the external interface for either the A/V network interface or the Edge Server in general.</span></span> <span data-ttu-id="e204f-121">Se a configuração **FQDN de habilitar separado e endereço IP para Webconferência e A / V** é habilitada, esse endereço IP público é usado para todas as interfaces externas três.</span><span class="sxs-lookup"><span data-stu-id="e204f-121">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** is enabled, this public IP address is used for all three external interfaces.</span></span>
  

