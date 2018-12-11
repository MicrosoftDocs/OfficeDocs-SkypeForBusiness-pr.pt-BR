---
title: Testar configurações de tronco SIP no Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Definições de configuração de tronco SIP definem a relação e os recursos entre um servidor de mediação e o gateway PSTN (rede) telefônica pública comutada, uma troca de filial IP público (PBX) ou um controlador de borda de sessão (SBC) no provedor de serviços. '
ms.openlocfilehash: d49b76c10505a009e6eed64d60632b52b08f3866
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222699"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="b6fe9-103">Testar configurações de tronco SIP no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="b6fe9-103">Test SIP trunk configuration settings in Skype for Business Server</span></span>

<span data-ttu-id="b6fe9-104">Definições de configuração de tronco SIP definem a relação e os recursos entre um servidor de mediação e o gateway PSTN (rede) telefônica pública comutada, uma troca de filial IP público (PBX) ou um controlador de borda de sessão (SBC) no provedor de serviços.</span><span class="sxs-lookup"><span data-stu-id="b6fe9-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="b6fe9-105">Essas configurações realizam atividades como especificar:</span><span class="sxs-lookup"><span data-stu-id="b6fe9-105">These settings do such things as specify:</span></span>

- <span data-ttu-id="b6fe9-106">Se o desvio de mídia deve ser ativado nos troncos.</span><span class="sxs-lookup"><span data-stu-id="b6fe9-106">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="b6fe9-107">As condições nas quais os pacotes RTCP (protocolo) de controle de transporte em tempo real são enviados.</span><span class="sxs-lookup"><span data-stu-id="b6fe9-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="b6fe9-108">Ou não a criptografia do protocolo em tempo real seguro (SRTP) é necessário em cada tronco.</span><span class="sxs-lookup"><span data-stu-id="b6fe9-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="b6fe9-109">Quando você instala o Skype para Business Server, uma coleção global de definições de configuração de tronco SIP é criada para você.</span><span class="sxs-lookup"><span data-stu-id="b6fe9-109">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="b6fe9-110">Além disso, os administradores podem criar conjuntos de configurações personalizadas no escopo local ou de serviço (apenas para o serviço de gateway PSTN).</span><span class="sxs-lookup"><span data-stu-id="b6fe9-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="b6fe9-111">Os administradores também podem usar o cmdlet [Test-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTrunkConfiguration) para verificar se um tronco pode converter um número como discado por um usuário para um número que pode ser manipulado pelo gateway.</span><span class="sxs-lookup"><span data-stu-id="b6fe9-111">Administrators can also use the [Test-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTrunkConfiguration) cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>

<span data-ttu-id="b6fe9-112">As definições de configuração de tronco podem ser testadas apenas usando o Windows PowerShell e o cmdlet  Test-CsTrunkConfiguration.</span><span class="sxs-lookup"><span data-stu-id="b6fe9-112">Trunk configuration settings can only be tested by using Windows PowerShell and the Test-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="b6fe9-113">Este cmdlet pode ser executado a partir do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b6fe9-113">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

<span data-ttu-id="b6fe9-114">**Testar as definições da configuração do Tronco SIP**</span><span class="sxs-lookup"><span data-stu-id="b6fe9-114">**To test SIP trunk configuration settings**</span></span>

<span data-ttu-id="b6fe9-115">Este comando verifica se as definições de configuração para o local Redmond podem converter corretamente o número discado 4255551212.</span><span class="sxs-lookup"><span data-stu-id="b6fe9-115">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>

```
$trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
```