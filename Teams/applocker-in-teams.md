---
title: Políticas de controle do AppLocker
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
f1.keywords:
- NOCSH
description: Saiba como habilitar o aplicativo cliente da equipe de trabalho com políticas de controle de aplicativo do AppLocker.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: cbccede3ca2d114b7bffa81b669a06a519f6b4e6
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121661"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a><span data-ttu-id="7d5ee-103">Políticas de controle de aplicativo do AppLocker no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7d5ee-103">AppLocker application control policies in Microsoft Teams</span></span>

<span data-ttu-id="7d5ee-104">Este artigo explica como habilitar o aplicativo cliente da área de trabalho do teams com as políticas de controle de aplicativo do AppLocker.</span><span class="sxs-lookup"><span data-stu-id="7d5ee-104">This article explains how to enable the Teams desktop client app with AppLocker application control policies.</span></span> <span data-ttu-id="7d5ee-105">O uso do AppLocker foi projetado para restringir a execução do programa e do script por usuários não administrativos.</span><span class="sxs-lookup"><span data-stu-id="7d5ee-105">Use of AppLocker is designed to restrict program and script execution by non-administrative users.</span></span> <span data-ttu-id="7d5ee-106">Para obter mais informações e diretrizes sobre o AppLocker, consulte [o que é o AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).</span><span class="sxs-lookup"><span data-stu-id="7d5ee-106">For more information and guidance on AppLocker, see [What is AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).</span></span>

<span data-ttu-id="7d5ee-107">O processo para habilitar o Teams com AppLocker requer a criação de políticas de lista branca baseadas em AppLocker.</span><span class="sxs-lookup"><span data-stu-id="7d5ee-107">The process for enabling Teams with AppLocker requires the creation of AppLocker-based whitelisting policies.</span></span> <span data-ttu-id="7d5ee-108">As políticas são criadas com o software de gerenciamento de política de grupo e/ou o uso de cmdlets do Windows PowerShell para AppLocker (consulte a [referência técnica do AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) para obter mais informações).</span><span class="sxs-lookup"><span data-stu-id="7d5ee-108">Policies are created with Group Policy management software and/or the use of Windows PowerShell cmdlets for AppLocker (see the [AppLocker technical reference](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) for more information).</span></span> <span data-ttu-id="7d5ee-109">A política AppLocker é salva no formato XML e pode ser editada com qualquer editor de texto ou XML.</span><span class="sxs-lookup"><span data-stu-id="7d5ee-109">The AppLocker policy is saved in XML format and can be edited with any text or XML editor.</span></span>

## <a name="teams-whitelisting-with-applocker"></a><span data-ttu-id="7d5ee-110">Lista negra do teams com AppLocker</span><span class="sxs-lookup"><span data-stu-id="7d5ee-110">Teams whitelisting with AppLocker</span></span>

<span data-ttu-id="7d5ee-111">As regras do AppLocker são organizadas em conjuntos de regras.</span><span class="sxs-lookup"><span data-stu-id="7d5ee-111">AppLocker rules are organized into collections of rules.</span></span> <span data-ttu-id="7d5ee-112">As regras do AppLocker se aplicam ao aplicativo de destino e são os componentes que compõem a política do AppLocker.</span><span class="sxs-lookup"><span data-stu-id="7d5ee-112">AppLocker rules apply to the targeted app, and they are the components that make up the AppLocker policy.</span></span>  

<span data-ttu-id="7d5ee-113">Para as equipes da lista branca, recomendamos que você use as [regras de condição do fornecedor](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) , pois todos os arquivos de aplicativo do teams são assinados digitalmente.</span><span class="sxs-lookup"><span data-stu-id="7d5ee-113">To whitelist Teams, we recommend that you use the [publisher condition rules](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) since all Teams app files are digitally signed.</span></span>
  
<span data-ttu-id="7d5ee-114">Não recomendamos o uso de regras de caminho porque o diretório de instalação do teams é gravável pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="7d5ee-114">We don't recommend the use of path rules because the Teams installation directory is user-writable.</span></span> <span data-ttu-id="7d5ee-115">Também não recomendamos o uso de regras de hash porque as regras precisariam ser atualizadas toda vez que o aplicativo cliente do teams for atualizado.</span><span class="sxs-lookup"><span data-stu-id="7d5ee-115">We also don't recommend the use of hash rules because the rules would have to be updated each time the Teams client app is updated.</span></span>

<span data-ttu-id="7d5ee-116">Como os arquivos executáveis da área de trabalho do teams são assinados digitalmente, a condição de fornecedor identifica um arquivo de aplicativo com base em seus atributos de assinatura digital e versão inserida.</span><span class="sxs-lookup"><span data-stu-id="7d5ee-116">Since Teams desktop executable files are digitally signed, the publisher condition identifies an app file based on its digital signature and embedded version attributes.</span></span> <span data-ttu-id="7d5ee-117">A assinatura digital contém informações sobre a empresa que criou o arquivo de aplicativo (o editor).</span><span class="sxs-lookup"><span data-stu-id="7d5ee-117">The digital signature contains information about the company that created the app file (the publisher).</span></span> <span data-ttu-id="7d5ee-118">As informações de versão, que são obtidas do recurso binário, incluem o nome do produto do qual o arquivo é parte e o número da versão do arquivo do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="7d5ee-118">The version information, which is obtained from the binary resource, includes the name of the product that the file is part of and the version number of the application file.</span></span>

### <a name="example-of-publisher-condition-rules"></a><span data-ttu-id="7d5ee-119">Exemplo de regras de condição do Publisher</span><span class="sxs-lookup"><span data-stu-id="7d5ee-119">Example of publisher condition rules</span></span>

<span data-ttu-id="7d5ee-120">Para o aplicativo cliente do Teams (todos os arquivos, todas as versões) adicione o seguinte às regras executáveis & regras de DLL:</span><span class="sxs-lookup"><span data-stu-id="7d5ee-120">For the Teams client app (all files, all versions) add the following to the Executable Rules & DLL Rules:</span></span>

```console
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
Product name: MICROSOFT TEAMS UPDATE
```

## <a name="related-topics"></a><span data-ttu-id="7d5ee-121">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="7d5ee-121">Related topics</span></span>
<span data-ttu-id="7d5ee-122">[O que é o AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
 [Referência técnica do AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span><span class="sxs-lookup"><span data-stu-id="7d5ee-122">[What is AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)
[AppLocker technical reference](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span></span>
