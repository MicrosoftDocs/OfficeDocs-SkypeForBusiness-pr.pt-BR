---
title: Exibir informações sobre troncos SIP individuais no Skype for Business Server
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
description: No Skype for Business Server, vários troncos podem ser atribuídos a um único gateway PSTN; Isso significa que os gateways e troncos não são iguais e os administradores devem usar o cmdlet Get-CsTrunk para exibir informações sobre um tronco SIP individual.
ms.openlocfilehash: b49846ed7244dec2f51f51f262becc440662026c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826171"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a><span data-ttu-id="b3ed7-103">Exibir informações sobre troncos SIP individuais no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b3ed7-103">View information about individual SIP trunks in Skype for Business Server</span></span>

<span data-ttu-id="b3ed7-104">No Skype for Business Server, vários troncos podem ser atribuídos a um único gateway PSTN; Isso significa que gateways e troncos não são iguais e devem usar o cmdlet [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) para exibir informações sobre um tronco SIP individual.</span><span class="sxs-lookup"><span data-stu-id="b3ed7-104">In Skype for Business Server, multiple trunks can be assigned to a single PSTN gateway; this means that gateways and trunks are not one and the same, and that administrators must use the [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) cmdlet to view information about an individual SIP trunk.</span></span>

<span data-ttu-id="b3ed7-105">O Get-CsTrunk cmdlet pode ser executado a partir do Shell de Gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b3ed7-105">The Get-CsTrunk cmdlet can be run either from the  Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span>

<span data-ttu-id="b3ed7-106">**Para exibir informações de todos os troncos SIP**</span><span class="sxs-lookup"><span data-stu-id="b3ed7-106">**To view information for all your SIP trunks**</span></span>

<span data-ttu-id="b3ed7-107">O comando a seguir retorna informações sobre todos os troncos SIP em uso na organização:</span><span class="sxs-lookup"><span data-stu-id="b3ed7-107">The following command returns information about all the SIP trunks in use in your organization:</span></span>

`Get-CsTrunk`

<span data-ttu-id="b3ed7-108">**Para exibir informações de um tronco SIP específico**</span><span class="sxs-lookup"><span data-stu-id="b3ed7-108">**To view information for a specific SIP trunk**</span></span>

<span data-ttu-id="b3ed7-109">Este comando retorna informações apenas para o tronco SIP com a Identidade PstnGateway:192.168.0.240:</span><span class="sxs-lookup"><span data-stu-id="b3ed7-109">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

<span data-ttu-id="b3ed7-110">**Exibindo informações de todos os troncos SIP atribuídos a um pool**</span><span class="sxs-lookup"><span data-stu-id="b3ed7-110">**Viewing Information for All the SIP Trunks Assigned to a Pool**</span></span>

<span data-ttu-id="b3ed7-111">Neste exemplo, as informações são retornadas para todos os troncos SIP atribuídos ao pool atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="b3ed7-111">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
