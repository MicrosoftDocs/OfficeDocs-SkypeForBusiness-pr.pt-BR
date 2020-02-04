---
title: Expansor de Configurações de Máquina de Borda
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para editar as propriedades de um servidor em um pool de servidores de borda, faça o seguinte:'
ms.openlocfilehash: 22f1e46481ce2392a806eadd6029ab51292d5585
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41702283"
---
# <a name="edge-machine-settings-expander"></a><span data-ttu-id="e0d48-103">Expansor de Configurações de Máquina de Borda</span><span class="sxs-lookup"><span data-stu-id="e0d48-103">Edge Machine Settings Expander</span></span>
 
<span data-ttu-id="e0d48-104">Para editar as propriedades de um servidor em um pool de servidores de borda, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e0d48-104">To edit the properties for a server in a pool of Edge Servers, do the following:</span></span>
  
<span data-ttu-id="e0d48-105">O **nome interno ou FQDN** pode ser alterado editando o nome de domínio totalmente qualificado (FQDN).</span><span class="sxs-lookup"><span data-stu-id="e0d48-105">The **Internal name or FQDN** can be changed by editing the fully qualified domain name (FQDN).</span></span> <span data-ttu-id="e0d48-106">O FQDN deve coincidir com o registro do host (A) do sistema de nomes de domínio (DNS) e o nome do requerente atribuído ao servidor para a interface de rede interna de borda.</span><span class="sxs-lookup"><span data-stu-id="e0d48-106">The FQDN must match the Domain Name System (DNS) host (A) record, and the subject name of the certificate assigned to the server for the internal Edge network interface.</span></span> <span data-ttu-id="e0d48-107">O valor do **endereço IP interno** define o endereço IP que é atribuído à interface de rede que é definida como uma rede interna, em relação ao design da rede do perímetro.</span><span class="sxs-lookup"><span data-stu-id="e0d48-107">The value of **Internal IP address** defines the IP address that is assigned the network interface that is defined as an internal network, relative to the perimeter network design.</span></span>
  
<span data-ttu-id="e0d48-108">As próximas três seções da caixa de diálogo definem os endereços IP para a configuração externa deste servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="e0d48-108">The next three sections of the dialog define the IP addresses for the external configuration of this Edge Server.</span></span> <span data-ttu-id="e0d48-109">A capacidade de alterar os endereços IP é afetada pela configuração **habilitar FQDN e endereço IP separados para Webconferência e a/V** nas configurações de propriedades no nível do pool do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="e0d48-109">The ability to change the IP addresses is affected by the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the Properties settings at the Edge Server pool level.</span></span>
  
## <a name="sip-access"></a><span data-ttu-id="e0d48-110">Acesso SIP</span><span class="sxs-lookup"><span data-stu-id="e0d48-110">SIP Access</span></span>

<span data-ttu-id="e0d48-111">Edite o endereço IP externo atribuído à interface de rede para acesso a SIP (protocolo de inicialização de sessão).</span><span class="sxs-lookup"><span data-stu-id="e0d48-111">Edit the external IP address that is assigned to the network interface for Session Initiation Protocol (SIP) access.</span></span> <span data-ttu-id="e0d48-112">Esse endereço IP pode ser um endereço IP público ou um endereço no intervalo de endereços IP privados.</span><span class="sxs-lookup"><span data-stu-id="e0d48-112">This IP address can either be a public IP address or an address in the private IP address range.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e0d48-113">Se a configuração **habilitar FQDN e endereço IP separados para Webconferência e a/V** na página de configurações do pool estiver habilitada, somente o endereço IP do acesso SIP estará disponível para edição.</span><span class="sxs-lookup"><span data-stu-id="e0d48-113">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the pool settings page is enabled, only the IP address for SIP access will be available for editing.</span></span>
  
## <a name="web-conferencing"></a><span data-ttu-id="e0d48-114">Webconferência</span><span class="sxs-lookup"><span data-stu-id="e0d48-114">Web Conferencing</span></span>

<span data-ttu-id="e0d48-115">Edite o endereço IP externo atribuído à interface de rede para conferência via Web.</span><span class="sxs-lookup"><span data-stu-id="e0d48-115">Edit the external IP address that is assigned to the network interface for web conferencing.</span></span> <span data-ttu-id="e0d48-116">Esse endereço IP pode ser um endereço IP público ou um endereço no intervalo de endereços IP privados.</span><span class="sxs-lookup"><span data-stu-id="e0d48-116">This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
## <a name="audiovideo"></a><span data-ttu-id="e0d48-117">Áudio/vídeo</span><span class="sxs-lookup"><span data-stu-id="e0d48-117">Audio/Video</span></span>

<span data-ttu-id="e0d48-118">Edite o endereço IP externo atribuído à interface de rede para áudio/vídeo (A/V).</span><span class="sxs-lookup"><span data-stu-id="e0d48-118">Edit the external IP address that is assigned to the network interface for audio/video (A/V).</span></span> <span data-ttu-id="e0d48-119">Esse endereço IP pode ser um endereço IP público ou um endereço no intervalo de endereços IP privados.</span><span class="sxs-lookup"><span data-stu-id="e0d48-119">This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
<span data-ttu-id="e0d48-120">A configuração para o **endereço IP público habilitado para NAT usado** é o endereço público usado pela interface externa para a interface de rede a/V ou o servidor de borda em geral.</span><span class="sxs-lookup"><span data-stu-id="e0d48-120">The setting for **NAT enabled public IP address used** is the public address used by the external interface for either the A/V network interface or the Edge Server in general.</span></span> <span data-ttu-id="e0d48-121">Se a configuração **habilitar FQDN e o endereço IP separados para Webconferência e A/V** estiver habilitado, o endereço IP público será usado para todas as três interfaces externas.</span><span class="sxs-lookup"><span data-stu-id="e0d48-121">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** is enabled, this public IP address is used for all three external interfaces.</span></span>
  

