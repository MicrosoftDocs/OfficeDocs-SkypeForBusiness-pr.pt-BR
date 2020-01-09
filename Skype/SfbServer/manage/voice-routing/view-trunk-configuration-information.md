---
title: Exibir informações de configuração de tronco no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: As configurações de tronco SIP definem a relação e os recursos entre um servidor de mediação e o gateway PSTN (rede telefônica pública comutada), um PBX (PBX IP-Public Branch Exchange) ou um SBC (controlador de borda de sessão) no provedor de serviços.
ms.openlocfilehash: 8fb180994fdcd8409b0776a2fcaee6316110a36d
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992548"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a><span data-ttu-id="ea0a3-103">Exibir informações de configuração de tronco no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ea0a3-103">View trunk configuration information in Skype for Business Server</span></span>

<span data-ttu-id="ea0a3-104">As configurações de tronco SIP definem a relação e os recursos entre um servidor de mediação e o gateway PSTN (rede telefônica pública comutada), um PBX (PBX IP-Public Branch Exchange) ou um SBC (controlador de borda de sessão) no provedor de serviços.</span><span class="sxs-lookup"><span data-stu-id="ea0a3-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span>

- <span data-ttu-id="ea0a3-105">Se o desvio de mídia deve ser ativado nos troncos.</span><span class="sxs-lookup"><span data-stu-id="ea0a3-105">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="ea0a3-106">As condições em que os pacotes de protocolo de controle de transporte em tempo real (RTCP) são enviados.</span><span class="sxs-lookup"><span data-stu-id="ea0a3-106">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="ea0a3-107">Se a criptografia SRTP (Secure Real-Time Protocol) é necessária ou não em cada tronco.</span><span class="sxs-lookup"><span data-stu-id="ea0a3-107">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="ea0a3-108">Quando você instala o Skype for Business Server, uma coleção global de configurações de tronco SIP é criada para você.</span><span class="sxs-lookup"><span data-stu-id="ea0a3-108">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="ea0a3-109">Além disso, os administradores podem criar coleções de configurações personalizadas no escopo do site ou no escopo do serviço (somente para o serviço de gateway PSTN).</span><span class="sxs-lookup"><span data-stu-id="ea0a3-109">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<span data-ttu-id="ea0a3-110">**Para ver as informações de configuração do tronco SIP usando o painel de controle do Skype for Business Server**</span><span class="sxs-lookup"><span data-stu-id="ea0a3-110">**To view SIP trunk configuration information by using Skype for Business Server Control Panel**</span></span>

1. <span data-ttu-id="ea0a3-111">No painel de controle do Skype for Business Server, clique em **Roteamento de voz**e, em seguida, clique em **configuração de tronco**.</span><span class="sxs-lookup"><span data-stu-id="ea0a3-111">In the Skype for Business Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>
2. <span data-ttu-id="ea0a3-112">Na guia **configuração de tronco** , você verá uma lista de todas as suas coleções de definições de configuração de tronco; para cada coleção, você verá os valores para as propriedades **nome**, **escopo**, **estado**e **ignorar mídia** , juntamente com o número de **usos de PSTN**, **as regras de número de chamada**e **as regras de número chamadas** associadas à coleção.</span><span class="sxs-lookup"><span data-stu-id="ea0a3-112">On the **Trunk Configuration** tab you will see a list of all your trunk configuration settings collections; for each collection you will see values for the **Name**, **Scope**, **State**, and **Media bypass** properties, along with the number of **PSTN usages**, **Calling number rules**, and **Called number rules** associated with the collection.</span></span> <span data-ttu-id="ea0a3-113">Para ver detalhes adicionais sobre uma coleção de definições de configuração de tronco, clique na coleção de interesse, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="ea0a3-113">To see additional details about a collection of trunk configuration settings, click the collection of interest, click **Edit**, and then click **Show details**.</span></span> <span data-ttu-id="ea0a3-114">Observe que você pode exibir informações detalhadas apenas para um conjunto de configurações de tronco de configuração de tronco de cada vez.</span><span class="sxs-lookup"><span data-stu-id="ea0a3-114">Note that you can view detailed information only for one collection of trunk configuration settings at a time.</span></span>

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ea0a3-115">Exibindo informações de configuração de tronco SIP usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ea0a3-115">Viewing SIP trunk configuration information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="ea0a3-116">As configurações de tronco SIP podem ser exibidas usando o Skype for Business Server PowerShell e o cmdlet Get-CsTrunkConfiguration.</span><span class="sxs-lookup"><span data-stu-id="ea0a3-116">SIP trunk configuration settings can be viewed by using Skype for Business Server PowerShell and the Get-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="ea0a3-117">Esse cmdlet pode ser executado do Shell de gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ea0a3-117">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="ea0a3-118">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o http://go.microsoft.com/fwlink/p/?linkId=255876Microsoft Lync Server 2010 usando o PowerShell remoto" em.</span><span class="sxs-lookup"><span data-stu-id="ea0a3-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at http://go.microsoft.com/fwlink/p/?linkId=255876.</span></span> <span data-ttu-id="ea0a3-119">SUBSTITUIR OU REMOVER ESTE LINK.</span><span class="sxs-lookup"><span data-stu-id="ea0a3-119">REPLACE OR REMOVE THIS LINK.</span></span>


<span data-ttu-id="ea0a3-120">**Para ver as informações de configuração do tronco SIP**</span><span class="sxs-lookup"><span data-stu-id="ea0a3-120">**To view SIP trunk configuration information**</span></span>

<span data-ttu-id="ea0a3-121">Para ver as informações sobre todas as suas configurações de tronco SIP, digite o seguinte comando no Shell de gerenciamento do Skype for Business Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="ea0a3-121">To view information about all your SIP trunk configuration settings, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>

`Get-CsTrunkConfiguration`

<span data-ttu-id="ea0a3-122">Isso retornará informações parecidas com:</span><span class="sxs-lookup"><span data-stu-id="ea0a3-122">That will return information similar to this:</span></span>

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
<span data-ttu-id="ea0a3-123">Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Get-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunkConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="ea0a3-123">For more information, see the help topic for the [Get-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunkConfiguration) cmdlet.</span></span>



