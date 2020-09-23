---
title: Expansor de Configurações de Máquina de Borda
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
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
description: 'Para editar propriedades para um servidor em um pool de Servidores de Borda, faça o seguinte:'
ms.openlocfilehash: e62cfa000379ed7318c5780bf91ac40035e6beee
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218912"
---
# <a name="edge-machine-settings-expander"></a><span data-ttu-id="0dbbf-103">Expansor de Configurações de Máquina de Borda</span><span class="sxs-lookup"><span data-stu-id="0dbbf-103">Edge Machine Settings Expander</span></span>
 
<span data-ttu-id="0dbbf-104">Para editar propriedades para um servidor em um pool de Servidores de Borda, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0dbbf-104">To edit the properties for a server in a pool of Edge Servers, do the following:</span></span>
  
<span data-ttu-id="0dbbf-p101">O  \*\*Nome interno ou FQDN \*\* pode ser alterado editando o FQDN (nome de domínio totalmente qualificado). O FQDN deve ser correspondente ao registro de hospedeiro (A) DNS (Domain Name System) e o nome de entidade do certificado atribuído ao servidor para a interface de rede de Borda interna. O valor do  \*\*Endereço IP interno \*\* define o endereço IP que está atribuído à interface de rede que está definida como rede interna, relativa ao projeto de rede de perímetro.</span><span class="sxs-lookup"><span data-stu-id="0dbbf-p101">The **Internal name or FQDN** can be changed by editing the fully qualified domain name (FQDN). The FQDN must match the Domain Name System (DNS) host (A) record, and the subject name of the certificate assigned to the server for the internal Edge network interface. The value of **Internal IP address** defines the IP address that is assigned the network interface that is defined as an internal network, relative to the perimeter network design.</span></span>
  
<span data-ttu-id="0dbbf-p102">As três próximas seções do diálogo definem os endereços IP para as configurações externas deste Servidor de Borda. A capacidade de alterar os endereços IP é afetada pela definição  \*\*Habilitar FQDN e endereço IP separados para webconferência e A/V \*\* nas configurações de Propriedades no nível de pool de Servidor de Borda.</span><span class="sxs-lookup"><span data-stu-id="0dbbf-p102">The next three sections of the dialog define the IP addresses for the external configuration of this Edge Server. The ability to change the IP addresses is affected by the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the Properties settings at the Edge Server pool level.</span></span>
  
## <a name="sip-access"></a><span data-ttu-id="0dbbf-110">Acesso SIP</span><span class="sxs-lookup"><span data-stu-id="0dbbf-110">SIP Access</span></span>

<span data-ttu-id="0dbbf-p103">Edite o endereço IP externo que foi atribuído à interface de rede para o acesso SIP (Session Initiation Protocol). Este endereço IP pode ser um endereço IP público ou um endereço em intervalo de endereço IP privado.</span><span class="sxs-lookup"><span data-stu-id="0dbbf-p103">Edit the external IP address that is assigned to the network interface for Session Initiation Protocol (SIP) access. This IP address can either be a public IP address or an address in the private IP address range.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0dbbf-113">Caso a definição **Habilitar FQDN e endereço IP separados para webconferência e A/V** na página de definições do pool esteja ativa, apenas o endereço IP para o acesso SIP estará disponível para edição.</span><span class="sxs-lookup"><span data-stu-id="0dbbf-113">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the pool settings page is enabled, only the IP address for SIP access will be available for editing.</span></span>
  
## <a name="web-conferencing"></a><span data-ttu-id="0dbbf-114">Webconferência</span><span class="sxs-lookup"><span data-stu-id="0dbbf-114">Web Conferencing</span></span>

<span data-ttu-id="0dbbf-p104">Edite o endereço IP externo que está atribuído à interface de rede para webconferência. Este endereço IP pode ser um endereço IP público ou um endereço em intervalo de endereço IP privado.</span><span class="sxs-lookup"><span data-stu-id="0dbbf-p104">Edit the external IP address that is assigned to the network interface for web conferencing. This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
## <a name="audiovideo"></a><span data-ttu-id="0dbbf-117">Áudio/vídeo</span><span class="sxs-lookup"><span data-stu-id="0dbbf-117">Audio/Video</span></span>

<span data-ttu-id="0dbbf-p105">Edite o endereço IP externo que está atribuído à interface de rede para A/V (áudio/vídeo). Este endereço IP pode ser um endereço IP público ou um endereço em intervalo de endereço IP privado.</span><span class="sxs-lookup"><span data-stu-id="0dbbf-p105">Edit the external IP address that is assigned to the network interface for audio/video (A/V). This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
<span data-ttu-id="0dbbf-p106">A definição para  \*\*Endereço IP público habilitado para NAT usado \*\* é o endereço público usado pela interface externa para a interface de rede A/V ou o Servidor de Borda em geral. Caso a definição  \*\*Habilitar FQDN e endereço IP separados para webconferência e A/V \*\* esteja ativada, este endereço IP público é usado para todas as três interfaces externas.</span><span class="sxs-lookup"><span data-stu-id="0dbbf-p106">The setting for **NAT enabled public IP address used** is the public address used by the external interface for either the A/V network interface or the Edge Server in general. If the setting **Enable separate FQDN and IP address for web conferencing and A/V** is enabled, this public IP address is used for all three external interfaces.</span></span>
  

