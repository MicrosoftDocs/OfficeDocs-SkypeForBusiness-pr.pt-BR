---
title: Criar diretórios de conferência no Skype for Business Server
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
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: 'Resumo: Saiba como criar diretórios de conferência no Skype for Business Server.'
ms.openlocfilehash: e4d73cc73a5c3c343e8a4734923cf80fb2590211
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119470"
---
# <a name="create-conference-directories-in-skype-for-business-server"></a><span data-ttu-id="26965-103">Criar diretórios de conferência no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="26965-103">Create conference directories in Skype for Business Server</span></span>
 
<span data-ttu-id="26965-104">**Resumo:** Saiba como criar diretórios de conferência no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="26965-104">**Summary:** Learn how to create conference directories in Skype for Business Server.</span></span>
  
<span data-ttu-id="26965-105">Os diretórios de conferência mantêm um mapeamento entre a ID de reunião alfanumérico que um participante usa para ingressar em uma conferência ao usar o Skype for Business e a ID de conferência somente numérica que um participante de conferência discada usa para ingressar na conferência.</span><span class="sxs-lookup"><span data-stu-id="26965-105">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Skype for Business, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> 
  
## <a name="create-a-conference-directory"></a><span data-ttu-id="26965-106">Criar um diretório de conferência</span><span class="sxs-lookup"><span data-stu-id="26965-106">Create a conference directory</span></span>

<span data-ttu-id="26965-107">A criação de vários diretórios de conferência garantirá que as IDs de conferência permaneçam curtas até que uma quantidade significativa de conferências tenha sido criada.</span><span class="sxs-lookup"><span data-stu-id="26965-107">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> 
  
<span data-ttu-id="26965-108">Em uma organização com um número típico de conferências por usuário, recomendamos que você crie um diretório de conferência para cada 999 usuários no pool.</span><span class="sxs-lookup"><span data-stu-id="26965-108">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool.</span></span> <span data-ttu-id="26965-109">Usando essa diretriz, as IDs de conferência geralmente podem ser mantidas pequenas.</span><span class="sxs-lookup"><span data-stu-id="26965-109">Using this guideline, the conference IDs can generally be kept small.</span></span> <span data-ttu-id="26965-110">No entanto, quando o número de diretórios de conferência (entre os pools) exceder 9, o tamanho da ID da Conferência aumentará para dar suporte a conferências adicionais.</span><span class="sxs-lookup"><span data-stu-id="26965-110">However, once the number of conference directories (across the pools) exceed 9, the Conference ID length will grow to support additional conferences.</span></span>
  
<span data-ttu-id="26965-111">O formato de uma ID de conferência é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="26965-111">The format of a conference ID is as follows:</span></span> 
  
```console
  <housekeeping digit (1 digit)><conference directory (usually 1-2 digits> 
  <conference number (variable number of digits><check digit (1 digit)>
```

<span data-ttu-id="26965-112">Para criar um diretório de conferência, use o cmdlet **New-CsConferenceDirectory.**</span><span class="sxs-lookup"><span data-stu-id="26965-112">To create a conference directory, use the **New-CsConferenceDirectory** cmdlet.</span></span> <span data-ttu-id="26965-113">Por exemplo, o seguinte comando cria um diretório de conferência com a identidade 42, hospedado no pool atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="26965-113">For example, the following command creates a conference directory with the identity 42, hosted on the pool atl-cs-001.litwareinc.com:</span></span>
  
```PowerShell
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"
```

<span data-ttu-id="26965-114">Para obter mais informações, [consulte New-CsConferenceDirectory](/powershell/module/skype/new-csconferencedirectory?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="26965-114">For more information, see [New-CsConferenceDirectory](/powershell/module/skype/new-csconferencedirectory?view=skype-ps).</span></span>
