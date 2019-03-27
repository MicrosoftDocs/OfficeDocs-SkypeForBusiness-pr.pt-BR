---
title: Exibir informações sobre individuais troncos SIP no Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: No Skype para Business Server, os vários troncos podem ser atribuídos a um único gateway PSTN; Isso significa que não são da mesma gateways e troncos, e os administradores devem usar o cmdlet Get-CsTrunk para exibir informações sobre um tronco SIP individual.
ms.openlocfilehash: 4c57bdfb8671c8aee3f0bb3dbc48fdc5cb920b07
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885174"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a><span data-ttu-id="5fa23-103">Exibir informações sobre individuais troncos SIP no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="5fa23-103">View information about individual SIP trunks in Skype for Business Server</span></span>

<span data-ttu-id="5fa23-104">No Skype para Business Server, os vários troncos podem ser atribuídos a um único gateway PSTN; Isso significa que os gateways e troncos não são da mesma e que os administradores devem usar o cmdlet [Get-CsTrunk](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk) para exibir informações sobre um tronco SIP individual.</span><span class="sxs-lookup"><span data-stu-id="5fa23-104">In Skype for Business Server, multiple trunks can be assigned to a single PSTN gateway; this means that gateways and trunks are not one and the same, and that administrators must use the [Get-CsTrunk](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk) cmdlet to view information about an individual SIP trunk.</span></span>

<span data-ttu-id="5fa23-105">O cmdlet Get-CsTrunk pode ser executado a partir do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5fa23-105">The Get-CsTrunk cmdlet can be run either from the  Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span>

<span data-ttu-id="5fa23-106">**Para visualizar as informações de todos os seus troncos SIP**</span><span class="sxs-lookup"><span data-stu-id="5fa23-106">**To view information for all your SIP trunks**</span></span>

<span data-ttu-id="5fa23-107">O seguinte comando retorna informações sobre todos os troncos SIP usados em sua organização:</span><span class="sxs-lookup"><span data-stu-id="5fa23-107">The following command returns information about all the SIP trunks in use in your organization:</span></span>

`Get-CsTrunk`

<span data-ttu-id="5fa23-108">**Para visualizar as informações de um tronco SIP específico**</span><span class="sxs-lookup"><span data-stu-id="5fa23-108">**To view information for a specific SIP trunk**</span></span>

<span data-ttu-id="5fa23-109">Este comando retorna informações somente para o tronco SIP com a Identidade PstnGateway:192.168.0.240:</span><span class="sxs-lookup"><span data-stu-id="5fa23-109">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

<span data-ttu-id="5fa23-110">**Exibindo informações para todos os troncos SIP atribuídos a um Pool**</span><span class="sxs-lookup"><span data-stu-id="5fa23-110">**Viewing Information for All the SIP Trunks Assigned to a Pool**</span></span>

<span data-ttu-id="5fa23-111">Neste exemplo, as informações são retornadas para todos os troncos SIP atribuídos ao pool atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="5fa23-111">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
