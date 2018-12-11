---
title: Exibir informações de configuração de tronco no Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Definições de configuração de tronco SIP definem a relação e os recursos entre um servidor de mediação e o gateway PSTN (rede) telefônica pública comutada, uma troca de filial IP público (PBX) ou um controlador de borda de sessão (SBC) no provedor de serviços.
ms.openlocfilehash: 9d4890cd70256c6f063653a29d5d41f6e5a301cb
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222713"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a><span data-ttu-id="dde35-103">Exibir informações de configuração de tronco no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="dde35-103">View trunk configuration information in Skype for Business Server</span></span>

<span data-ttu-id="dde35-104">Definições de configuração de tronco SIP definem a relação e os recursos entre um servidor de mediação e o gateway PSTN (rede) telefônica pública comutada, uma troca de filial IP público (PBX) ou um controlador de borda de sessão (SBC) no provedor de serviços.</span><span class="sxs-lookup"><span data-stu-id="dde35-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span>

- <span data-ttu-id="dde35-105">Se o desvio de mídia deve ser ativado nos troncos.</span><span class="sxs-lookup"><span data-stu-id="dde35-105">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="dde35-106">As condições nas quais os pacotes RTCP (protocolo) de controle de transporte em tempo real são enviados.</span><span class="sxs-lookup"><span data-stu-id="dde35-106">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="dde35-107">Ou não a criptografia do protocolo em tempo real seguro (SRTP) é necessário em cada tronco.</span><span class="sxs-lookup"><span data-stu-id="dde35-107">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="dde35-108">Quando você instala o Skype para Business Server, uma coleção global de definições de configuração de tronco SIP é criada para você.</span><span class="sxs-lookup"><span data-stu-id="dde35-108">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="dde35-109">Além disso, os administradores podem criar conjuntos de configurações personalizadas no escopo local ou de serviço (apenas para o serviço de gateway PSTN).</span><span class="sxs-lookup"><span data-stu-id="dde35-109">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<span data-ttu-id="dde35-110">**Para exibir informações de configuração de tronco SIP usando Skype para o painel de controle do servidor de negócios**</span><span class="sxs-lookup"><span data-stu-id="dde35-110">**To view SIP trunk configuration information by using Skype for Business Server Control Panel**</span></span>

1. <span data-ttu-id="dde35-111">Na Skype para painel de controle do Business Server, clique em **Roteamento de voz**e clique em **Configuração de tronco**.</span><span class="sxs-lookup"><span data-stu-id="dde35-111">In the Skype for Business Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>
2. <span data-ttu-id="dde35-112">Na guia **Configuração de tronco** , você verá uma lista de todos os seus tronco coleções de configurações do; para cada conjunto de valores para as propriedades de **nome**, **escopo**, **estado**e **bypass de mídia** , juntamente com o número de **usos da PSTN**, **as regras de número de chamada**e **regras de número de chamada** associado você verá com a coleção.</span><span class="sxs-lookup"><span data-stu-id="dde35-112">On the **Trunk Configuration** tab you will see a list of all your trunk configuration settings collections; for each collection you will see values for the **Name**, **Scope**, **State**, and **Media bypass** properties, along with the number of **PSTN usages**, **Calling number rules**, and **Called number rules** associated with the collection.</span></span> <span data-ttu-id="dde35-113">Para ver detalhes adicionais sobre uma coleção de definições de configuração de tronco, clique no conjunto de interesse, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="dde35-113">To see additional details about a collection of trunk configuration settings, click the collection of interest, click **Edit**, and then click **Show details**.</span></span> <span data-ttu-id="dde35-114">Observe que você pode visualizar informações detalhadas apenas para uma coleção de definições de configuração de tronco por vez.</span><span class="sxs-lookup"><span data-stu-id="dde35-114">Note that you can view detailed information only for one collection of trunk configuration settings at a time.</span></span>

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="dde35-115">Exibindo informações de configuração de tronco SIP usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dde35-115">Viewing SIP trunk configuration information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="dde35-116">Configuração de tronco configurações podem ser exibidas usando Skype para Business Server PowerShell e o cmdlet Get-CsTrunkConfiguration de SIP.</span><span class="sxs-lookup"><span data-stu-id="dde35-116">SIP trunk configuration settings can be viewed by using Skype for Business Server PowerShell and the Get-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="dde35-117">Este cmdlet pode ser executado a partir do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dde35-117">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="dde35-118">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype para Business Server, consulte o artigo do blog do Lync Server Windows PowerShell "Rápida iniciar: Gerenciando Microsoft Lync Server 2010 Using Remote PowerShell" em http://go.microsoft.com/fwlink/p/?linkId=255876.</span><span class="sxs-lookup"><span data-stu-id="dde35-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at http://go.microsoft.com/fwlink/p/?linkId=255876.</span></span> <span data-ttu-id="dde35-119">SUBSTITUIR OU REMOVER ESTE LINK.</span><span class="sxs-lookup"><span data-stu-id="dde35-119">REPLACE OR REMOVE THIS LINK.</span></span>


<span data-ttu-id="dde35-120">**Para exibir informações de configuração de tronco SIP**</span><span class="sxs-lookup"><span data-stu-id="dde35-120">**To view SIP trunk configuration information**</span></span>

<span data-ttu-id="dde35-121">Para exibir informações sobre todas as suas definições de configuração de tronco SIP, digite o seguinte comando no Skype do Shell de gerenciamento do servidor de negócios e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="dde35-121">To view information about all your SIP trunk configuration settings, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>

`Get-CsTrunkConfiguration`

<span data-ttu-id="dde35-122">Isso retornará informações parecidas com:</span><span class="sxs-lookup"><span data-stu-id="dde35-122">That will return information similar to this:</span></span>

```
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
<span data-ttu-id="dde35-123">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunkConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="dde35-123">For more information, see the help topic for the [Get-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunkConfiguration) cmdlet.</span></span>



