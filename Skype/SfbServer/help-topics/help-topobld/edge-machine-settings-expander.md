---
title: Expansor de configurações de máquina de borda
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
description: 'Para editar as propriedades de um servidor em um pool de servidores de borda, faça o seguinte:'
ms.openlocfilehash: 04b8d8efc455203e49aeb81e533604a405e37cc5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="edge-machine-settings-expander"></a><span data-ttu-id="ad2c7-103">Expansor de configurações de máquina de borda</span><span class="sxs-lookup"><span data-stu-id="ad2c7-103">Edge Machine Settings Expander</span></span>
 
<span data-ttu-id="ad2c7-104">Para editar as propriedades de um servidor em um pool de servidores de borda, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ad2c7-104">To edit the properties for a server in a pool of Edge Servers, do the following:</span></span>
  
<span data-ttu-id="ad2c7-105">O **nome interno ou FQDN** pode ser alterada editando o nome de domínio totalmente qualificado (FQDN).</span><span class="sxs-lookup"><span data-stu-id="ad2c7-105">The **Internal name or FQDN** can be changed by editing the fully qualified domain name (FQDN).</span></span> <span data-ttu-id="ad2c7-106">O FQDN deve coincidir com o host (A) registro do sistema de nome de domínio (DNS) e o nome da entidade do certificado atribuído ao servidor da interface de rede de borda interna.</span><span class="sxs-lookup"><span data-stu-id="ad2c7-106">The FQDN must match the Domain Name System (DNS) host (A) record, and the subject name of the certificate assigned to the server for the internal Edge network interface.</span></span> <span data-ttu-id="ad2c7-107">O valor de **endereço IP interno** define o endereço IP atribuído a interface de rede que é definida como uma rede interna, em relação ao design da rede de perímetro.</span><span class="sxs-lookup"><span data-stu-id="ad2c7-107">The value of **Internal IP address** defines the IP address that is assigned the network interface that is defined as an internal network, relative to the perimeter network design.</span></span>
  
<span data-ttu-id="ad2c7-108">As próximas três seções da caixa de diálogo definem os endereços IP para a configuração externa do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="ad2c7-108">The next three sections of the dialog define the IP addresses for the external configuration of this Edge Server.</span></span> <span data-ttu-id="ad2c7-109">A capacidade de alterar os endereços IP é afetada pela definição **FQDN de habilitar separado e endereço IP para Webconferência e A / V** nas configurações de propriedades no servidor de Borda nível do pool.</span><span class="sxs-lookup"><span data-stu-id="ad2c7-109">The ability to change the IP addresses is affected by the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the Properties settings at the Edge Server pool level.</span></span>
  
## <a name="sip-access"></a><span data-ttu-id="ad2c7-110">Acesso SIP</span><span class="sxs-lookup"><span data-stu-id="ad2c7-110">SIP Access</span></span>

<span data-ttu-id="ad2c7-111">Edite o endereço IP externo que é atribuído à interface de rede para acesso de protocolo de iniciação de sessão (SIP).</span><span class="sxs-lookup"><span data-stu-id="ad2c7-111">Edit the external IP address that is assigned to the network interface for Session Initiation Protocol (SIP) access.</span></span> <span data-ttu-id="ad2c7-112">Esse endereço IP pode ser um endereço IP público ou um endereço no intervalo de endereços IP privado.</span><span class="sxs-lookup"><span data-stu-id="ad2c7-112">This IP address can either be a public IP address or an address in the private IP address range.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ad2c7-113">Se a configuração **FQDN de habilitar separado e endereço IP para Webconferência e A / V** no pool páginaconfigurações estiver habilitada, somente o endereço IP para acesso do SIP estará disponível para edição.</span><span class="sxs-lookup"><span data-stu-id="ad2c7-113">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the pool settings page is enabled, only the IP address for SIP access will be available for editing.</span></span>
  
## <a name="web-conferencing"></a><span data-ttu-id="ad2c7-114">Webconferência</span><span class="sxs-lookup"><span data-stu-id="ad2c7-114">Web Conferencing</span></span>

<span data-ttu-id="ad2c7-115">Edite o endereço IP externo que é atribuído à interface de rede para webconferências.</span><span class="sxs-lookup"><span data-stu-id="ad2c7-115">Edit the external IP address that is assigned to the network interface for web conferencing.</span></span> <span data-ttu-id="ad2c7-116">Esse endereço IP pode ser um endereço IP público ou um endereço no intervalo de endereços IP privado.</span><span class="sxs-lookup"><span data-stu-id="ad2c7-116">This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
## <a name="audiovideo"></a><span data-ttu-id="ad2c7-117">Áudio/vídeo</span><span class="sxs-lookup"><span data-stu-id="ad2c7-117">Audio/Video</span></span>

<span data-ttu-id="ad2c7-118">Editar o endereço IP externo que é atribuído à interface de rede para áudio/vídeo (A / V).</span><span class="sxs-lookup"><span data-stu-id="ad2c7-118">Edit the external IP address that is assigned to the network interface for audio/video (A/V).</span></span> <span data-ttu-id="ad2c7-119">Esse endereço IP pode ser um endereço IP público ou um endereço no intervalo de endereços IP privado.</span><span class="sxs-lookup"><span data-stu-id="ad2c7-119">This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
<span data-ttu-id="ad2c7-120">A configuração **endereço IP público do usado habilitado para NAT** é o endereço público usado pela interface externa para ambos os A / V rede interface ou o servidor de borda em geral.</span><span class="sxs-lookup"><span data-stu-id="ad2c7-120">The setting for **NAT enabled public IP address used** is the public address used by the external interface for either the A/V network interface or the Edge Server in general.</span></span> <span data-ttu-id="ad2c7-121">Se a configuração **FQDN de habilitar separado e endereço IP para Webconferência e A / V** é habilitada, esse endereço IP público é usado para todas as interfaces externas três.</span><span class="sxs-lookup"><span data-stu-id="ad2c7-121">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** is enabled, this public IP address is used for all three external interfaces.</span></span>
  

