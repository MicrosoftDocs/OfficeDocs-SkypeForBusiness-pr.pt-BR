---
title: Exibir informações de configuração de tronco no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: As definições de configuração de tronco SIP definem o relacionamento e as capacidades entre um Servidor de Mediação e gateway PSTN, um PBX-IP ou um SBC no provedor de serviços.
ms.openlocfilehash: c473c3fc19138ac91b44dff8552555418d36533f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826161"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a><span data-ttu-id="0c529-103">Exibir informações de configuração de tronco no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0c529-103">View trunk configuration information in Skype for Business Server</span></span>

<span data-ttu-id="0c529-104">As definições de configuração de tronco SIP definem o relacionamento e as capacidades entre um Servidor de Mediação e gateway PSTN, um PBX-IP ou um SBC no provedor de serviços.</span><span class="sxs-lookup"><span data-stu-id="0c529-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span>

- <span data-ttu-id="0c529-105">Se o bypass de mídia deve ser habilitado nos troncos.</span><span class="sxs-lookup"><span data-stu-id="0c529-105">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="0c529-106">As condições nas quais os pacotes RTCP são enviados.</span><span class="sxs-lookup"><span data-stu-id="0c529-106">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="0c529-107">Se a criptografia SRTP é obrigatória em cada tronco.</span><span class="sxs-lookup"><span data-stu-id="0c529-107">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="0c529-108">Quando você instala o Skype for Business Server, um conjunto global de definições de configuração de tronco SIP é criado para você.</span><span class="sxs-lookup"><span data-stu-id="0c529-108">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="0c529-109">Além disso, os administradores podem criar conjuntos de configurações personalizadas no escopo local ou de serviço (apenas para o serviço de gateway PSTN).</span><span class="sxs-lookup"><span data-stu-id="0c529-109">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<span data-ttu-id="0c529-110">**Para exibir informações de configuração do tronco SIP usando o Painel de Controle do Skype for Business Server**</span><span class="sxs-lookup"><span data-stu-id="0c529-110">**To view SIP trunk configuration information by using Skype for Business Server Control Panel**</span></span>

1. <span data-ttu-id="0c529-111">No Painel de Controle do Skype for Business Server, clique em **Roteamento** de Voz e em **Configuração de Tronco.**</span><span class="sxs-lookup"><span data-stu-id="0c529-111">In the Skype for Business Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>
2. <span data-ttu-id="0c529-112">Na guia **Configuração do** Tronco, você verá uma lista de todas as suas coleções de definições de configuração de tronco; para cada coleção, você verá valores para as propriedades **Name**, **Scope**, **State** e **Media bypass,** juntamente com o número de usos de **PSTN** **,** regras de número de chamada e regras de número **chamado** associadas à coleção.</span><span class="sxs-lookup"><span data-stu-id="0c529-112">On the **Trunk Configuration** tab you will see a list of all your trunk configuration settings collections; for each collection you will see values for the **Name**, **Scope**, **State**, and **Media bypass** properties, along with the number of **PSTN usages**, **Calling number rules**, and **Called number rules** associated with the collection.</span></span> <span data-ttu-id="0c529-113">Para exibir informações adicionais sobre um coleção de configurações de tronco, clique na coleção de interesse, clique em **Editar** e depois clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="0c529-113">To see additional details about a collection of trunk configuration settings, click the collection of interest, click **Edit**, and then click **Show details**.</span></span> <span data-ttu-id="0c529-114">Observe que você pode exibir informações detalhadas somente de uma coleção de configurações de tronco por vez.</span><span class="sxs-lookup"><span data-stu-id="0c529-114">Note that you can view detailed information only for one collection of trunk configuration settings at a time.</span></span>

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="0c529-115">Exibindo informações de configuração do tronco SIP usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c529-115">Viewing SIP trunk configuration information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="0c529-116">As definições de configuração do tronco SIP podem ser visualizadas usando o PowerShell do Skype for Business Server e o Get-CsTrunkConfiguration cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0c529-116">SIP trunk configuration settings can be viewed by using Skype for Business Server PowerShell and the Get-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="0c529-117">Esse cmdlet pode ser executado a partir do Shell de Gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c529-117">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="0c529-118">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo do blog do Lync Server Windows PowerShell "Início Rápido: Gerenciando o Microsoft Lync Server 2010 usando o PowerShell Remoto" em https://go.microsoft.com/fwlink/p/?linkId=255876 .</span><span class="sxs-lookup"><span data-stu-id="0c529-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at https://go.microsoft.com/fwlink/p/?linkId=255876.</span></span> <span data-ttu-id="0c529-119">SUBSTITUA OU REMOVA ESTE LINK.</span><span class="sxs-lookup"><span data-stu-id="0c529-119">REPLACE OR REMOVE THIS LINK.</span></span>


<span data-ttu-id="0c529-120">**Para exibir informações de configuração do tronco SIP**</span><span class="sxs-lookup"><span data-stu-id="0c529-120">**To view SIP trunk configuration information**</span></span>

<span data-ttu-id="0c529-121">Para exibir informações sobre todas as suas definições de configuração de tronco SIP, digite o seguinte comando no Shell de Gerenciamento do Skype for Business Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="0c529-121">To view information about all your SIP trunk configuration settings, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>

```powershell
Get-CsTrunkConfiguration
```

<span data-ttu-id="0c529-122">Isto retorna informações semelhantes à seguinte:</span><span class="sxs-lookup"><span data-stu-id="0c529-122">That will return information similar to this:</span></span>

```console
Identity                                  : Global
OutboundTranslationRulesList              : {}
SipResponseCodeTranslationRulesList       : {}
OutboundCallingNumberTranslationRulesList : {}
PstnUsages                                : {}
Description                               :
ConcentratedTopology                      : True
EnableBypass                              : False
EnableMobileTrunkSupport                  : False
EnableReferSupport                        : True
EnableSessionTimer                        : False
EnableSignalBoost                         : False
MaxEarlyDialogs                           : 20
RemovePlusFromUri                         : False
RTCPActiveCalls                           : True
RTCPCallsOnHold                           : True
SRTPMode                                  : Required
EnablePIDFLOSupport                       : False
EnableRTPLatching                         : False
EnableOnlineVoice                         : False
ForwardCallHistory                        : False
Enable3pccRefer                           : False
ForwardPAI                                : False
EnableFastFailoverTimer                   : True
```
<span data-ttu-id="0c529-123">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsTrunkConfiguration.](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration)</span><span class="sxs-lookup"><span data-stu-id="0c529-123">For more information, see the help topic for the [Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) cmdlet.</span></span>



