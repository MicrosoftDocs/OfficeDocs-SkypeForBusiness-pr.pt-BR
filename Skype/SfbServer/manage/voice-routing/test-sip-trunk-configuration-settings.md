---
title: Testar as definições de configuração do tronco SIP no Skype for Business Server
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
description: 'As definições de configuração de tronco SIP definem o relacionamento e as capacidades entre um Servidor de Mediação e gateway PSTN, um PBX-IP ou um SBC no provedor de serviços. '
ms.openlocfilehash: 1489fe1e45223bac6b62ed23a09212a569ea7838
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826181"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="28681-103">Testar as definições de configuração do tronco SIP no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="28681-103">Test SIP trunk configuration settings in Skype for Business Server</span></span>

<span data-ttu-id="28681-p101">As definições de configuração de tronco SIP definem o relacionamento e as capacidades entre um Servidor de Mediação e gateway PSTN, um PBX-IP ou um SBC no provedor de serviços. Estas configurações fazem coisas como especificar:</span><span class="sxs-lookup"><span data-stu-id="28681-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

- <span data-ttu-id="28681-106">Se o bypass de mídia deve ser habilitado nos troncos.</span><span class="sxs-lookup"><span data-stu-id="28681-106">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="28681-107">As condições nas quais os pacotes RTCP são enviados.</span><span class="sxs-lookup"><span data-stu-id="28681-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="28681-108">Se a criptografia SRTP é obrigatória em cada tronco.</span><span class="sxs-lookup"><span data-stu-id="28681-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="28681-109">Quando você instala o Skype for Business Server, um conjunto global de definições de configuração de tronco SIP é criado para você.</span><span class="sxs-lookup"><span data-stu-id="28681-109">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="28681-110">Além disso, os administradores podem criar conjuntos de configurações personalizadas no escopo local ou de serviço (apenas para o serviço de gateway PSTN).</span><span class="sxs-lookup"><span data-stu-id="28681-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="28681-111">Os administradores também podem usar o cmdlet [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration) para verificar se um tronco pode converter um número conforme discado por um usuário em um número que pode ser manipulado pelo gateway.</span><span class="sxs-lookup"><span data-stu-id="28681-111">Administrators can also use the [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration) cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>

<span data-ttu-id="28681-112">As definições de configuração de tronco podem ser testadas apenas usando o Windows PowerShell e o cmdlet Test-CsTrunkConfiguration.</span><span class="sxs-lookup"><span data-stu-id="28681-112">Trunk configuration settings can only be tested by using Windows PowerShell and the Test-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="28681-113">Esse cmdlet pode ser executado a partir do Shell de Gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28681-113">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

<span data-ttu-id="28681-114">**Para testar as definições de configuração do tronco SIP**</span><span class="sxs-lookup"><span data-stu-id="28681-114">**To test SIP trunk configuration settings**</span></span>

<span data-ttu-id="28681-115">Este comando verifica se as definições de configuração para o local Redmond podem converter corretamente o número discado 4255551212.</span><span class="sxs-lookup"><span data-stu-id="28681-115">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>

```PowerShell
$trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
```
