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
ms.openlocfilehash: 03b2ea63df8135edfdb3d63d9010aaace9266fd1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102987"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a><span data-ttu-id="af627-103">Exibir informações de configuração de tronco no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="af627-103">View trunk configuration information in Skype for Business Server</span></span>

<span data-ttu-id="af627-104">As definições de configuração de tronco SIP definem o relacionamento e as capacidades entre um Servidor de Mediação e gateway PSTN, um PBX-IP ou um SBC no provedor de serviços.</span><span class="sxs-lookup"><span data-stu-id="af627-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span>

- <span data-ttu-id="af627-105">Se o bypass de mídia deve ser habilitado nos troncos.</span><span class="sxs-lookup"><span data-stu-id="af627-105">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="af627-106">As condições nas quais os pacotes RTCP são enviados.</span><span class="sxs-lookup"><span data-stu-id="af627-106">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="af627-107">Se a criptografia SRTP é obrigatória em cada tronco.</span><span class="sxs-lookup"><span data-stu-id="af627-107">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="af627-108">Quando você instala o Skype for Business Server, uma coleção global de configurações de tronco SIP é criada para você.</span><span class="sxs-lookup"><span data-stu-id="af627-108">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="af627-109">Além disso, os administradores podem criar conjuntos de configurações personalizadas no escopo local ou de serviço (apenas para o serviço de gateway PSTN).</span><span class="sxs-lookup"><span data-stu-id="af627-109">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<span data-ttu-id="af627-110">**Para exibir informações de configuração de tronco SIP usando o Painel de Controle do Skype for Business Server**</span><span class="sxs-lookup"><span data-stu-id="af627-110">**To view SIP trunk configuration information by using Skype for Business Server Control Panel**</span></span>

1. <span data-ttu-id="af627-111">No Painel de Controle do Skype for Business Server, clique em **Roteamento** de Voz e clique em **Configuração de Tronco.**</span><span class="sxs-lookup"><span data-stu-id="af627-111">In the Skype for Business Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>
2. <span data-ttu-id="af627-112">Na guia **Configuração do** Tronco, você verá uma lista de todas as suas coleções de configurações de tronco; para cada coleção, você verá valores para as propriedades  **Name**, **Scope**, **State** e Media **bypass,** juntamente com o número de **usos de PSTN,** regras de número de chamada e regras de número chamado associadas à coleção. </span><span class="sxs-lookup"><span data-stu-id="af627-112">On the **Trunk Configuration** tab you will see a list of all your trunk configuration settings collections; for each collection you will see values for the **Name**, **Scope**, **State**, and **Media bypass** properties, along with the number of **PSTN usages**, **Calling number rules**, and **Called number rules** associated with the collection.</span></span> <span data-ttu-id="af627-113">Para exibir informações adicionais sobre um coleção de configurações de tronco, clique na coleção de interesse, clique em **Editar** e depois clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="af627-113">To see additional details about a collection of trunk configuration settings, click the collection of interest, click **Edit**, and then click **Show details**.</span></span> <span data-ttu-id="af627-114">Observe que você pode exibir informações detalhadas somente de uma coleção de configurações de tronco por vez.</span><span class="sxs-lookup"><span data-stu-id="af627-114">Note that you can view detailed information only for one collection of trunk configuration settings at a time.</span></span>

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="af627-115">Exibindo informações de configuração de tronco SIP usando Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="af627-115">Viewing SIP trunk configuration information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="af627-116">As configurações de tronco SIP podem ser visualizadas usando o Skype for Business Server PowerShell e o cmdlet Get-CsTrunkConfiguration de usuário.</span><span class="sxs-lookup"><span data-stu-id="af627-116">SIP trunk configuration settings can be viewed by using Skype for Business Server PowerShell and the Get-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="af627-117">Esse cmdlet pode ser executado no Shell de Gerenciamento do Skype for Business Server ou em uma sessão remota Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="af627-117">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="af627-118">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo do blog do Lync Server Windows PowerShell "Início Rápido: Gerenciamento do Microsoft Lync Server 2010 Usando o PowerShell Remoto" em https://go.microsoft.com/fwlink/p/?linkId=255876 .</span><span class="sxs-lookup"><span data-stu-id="af627-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at https://go.microsoft.com/fwlink/p/?linkId=255876.</span></span> <span data-ttu-id="af627-119">SUBSTITUA OU REMOVA ESSE LINK.</span><span class="sxs-lookup"><span data-stu-id="af627-119">REPLACE OR REMOVE THIS LINK.</span></span>


<span data-ttu-id="af627-120">**Para exibir informações de configuração de tronco SIP**</span><span class="sxs-lookup"><span data-stu-id="af627-120">**To view SIP trunk configuration information**</span></span>

<span data-ttu-id="af627-121">Para exibir informações sobre todas as configurações de tronco SIP, digite o seguinte comando no Shell de Gerenciamento do Skype for Business Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="af627-121">To view information about all your SIP trunk configuration settings, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>

```powershell
Get-CsTrunkConfiguration
```

<span data-ttu-id="af627-122">Isto retorna informações semelhantes à seguinte:</span><span class="sxs-lookup"><span data-stu-id="af627-122">That will return information similar to this:</span></span>

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
<span data-ttu-id="af627-123">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsTrunkConfiguration.](/powershell/module/skype/Get-CsTrunkConfiguration)</span><span class="sxs-lookup"><span data-stu-id="af627-123">For more information, see the help topic for the [Get-CsTrunkConfiguration](/powershell/module/skype/Get-CsTrunkConfiguration) cmdlet.</span></span>