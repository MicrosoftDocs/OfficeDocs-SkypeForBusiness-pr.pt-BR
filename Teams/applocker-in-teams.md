---
title: AppLocker diretivas de controle de aplicativo no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
description: Aprenda a habilitar o aplicativo do cliente de desktop equipes com políticas de controle do aplicativo de AppLocker.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 04379cad0ab224915a02475b010f908d486284cc
ms.sourcegitcommit: 85b135cf622c9e9eb1857ef953bc618dc2cdb51e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34063202"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a><span data-ttu-id="8a545-103">AppLocker diretivas de controle de aplicativo no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8a545-103">AppLocker application control policies in Microsoft Teams</span></span>

<span data-ttu-id="8a545-104">Este artigo explica como habilitar o aplicativo do cliente de desktop equipes com políticas de controle do aplicativo de AppLocker.</span><span class="sxs-lookup"><span data-stu-id="8a545-104">This article explains how to enable the Teams desktop client app with AppLocker application control policies.</span></span> <span data-ttu-id="8a545-105">Uso do AppLocker foi projetado para restringir a execução do programa e script por usuários não administrativos.</span><span class="sxs-lookup"><span data-stu-id="8a545-105">Use of AppLocker is designed to restrict program and script execution by non-administrative users.</span></span> <span data-ttu-id="8a545-106">Para obter mais informações e orientações sobre AppLocker, consulte [Novidades AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).</span><span class="sxs-lookup"><span data-stu-id="8a545-106">For more information and guidance on AppLocker, see [What is AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).</span></span>

<span data-ttu-id="8a545-107">O processo para habilitar as equipes com AppLocker exige a criação de políticas de lista de exceções baseado em AppLocker.</span><span class="sxs-lookup"><span data-stu-id="8a545-107">The process for enabling Teams with AppLocker requires the creation of AppLocker-based whitelisting policies.</span></span> <span data-ttu-id="8a545-108">As diretivas são criadas com o software de gerenciamento de diretiva de grupo e/ou o uso dos cmdlets do Windows PowerShell para AppLocker (consulte a [referência técnica do AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) para obter mais informações).</span><span class="sxs-lookup"><span data-stu-id="8a545-108">Policies are created with Group Policy management software and/or the use of Windows PowerShell cmdlets for AppLocker (see the [AppLocker technical reference](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) for more information).</span></span> <span data-ttu-id="8a545-109">A política de AppLocker é salvo em formato XML e pode ser editada com qualquer editor de texto ou XML.</span><span class="sxs-lookup"><span data-stu-id="8a545-109">The AppLocker policy is saved in XML format and can be edited with any text or XML editor.</span></span>

## <a name="teams-whitelisting-with-applocker"></a><span data-ttu-id="8a545-110">Lista de exceções de equipes com AppLocker</span><span class="sxs-lookup"><span data-stu-id="8a545-110">Teams whitelisting with AppLocker</span></span>

<span data-ttu-id="8a545-111">Regras do AppLocker são organizadas em conjuntos de regras.</span><span class="sxs-lookup"><span data-stu-id="8a545-111">AppLocker rules are organized into collections of rules.</span></span> <span data-ttu-id="8a545-112">Regras de AppLocker aplicam-se para o aplicativo de destino, e são os componentes que compõem a política de AppLocker.</span><span class="sxs-lookup"><span data-stu-id="8a545-112">AppLocker rules apply to the targeted app, and they are the components that make up the AppLocker policy.</span></span>  

<span data-ttu-id="8a545-113">A lista branca equipes, recomendamos que você use as [regras de condição do publisher](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) , desde que todos os arquivos de aplicativo de equipes são assinados digitalmente.</span><span class="sxs-lookup"><span data-stu-id="8a545-113">To whitelist Teams, we recommend that you use the [publisher condition rules](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) since all Teams app files are digitally signed.</span></span>
  
<span data-ttu-id="8a545-114">Não recomendamos o uso de regras de caminho como o diretório de instalação de equipes é gravável de usuário.</span><span class="sxs-lookup"><span data-stu-id="8a545-114">We don't recommend the use of path rules because the Teams installation directory is user-writable.</span></span> <span data-ttu-id="8a545-115">Também não recomendamos o uso de regras de hash porque as regras teria que ser atualizadas toda vez que o aplicativo cliente de equipes é atualizado.</span><span class="sxs-lookup"><span data-stu-id="8a545-115">We also don't recommend the use of hash rules because the rules would have to be updated each time the Teams client app is updated.</span></span>

<span data-ttu-id="8a545-116">Desde que arquivos executáveis da área de trabalho de equipes são assinados digitalmente, a condição de editor identifica um arquivo de aplicativo com base em sua assinatura digital e os atributos de versão incorporada.</span><span class="sxs-lookup"><span data-stu-id="8a545-116">Since Teams desktop executable files are digitally signed, the publisher condition identifies an app file based on its digital signature and embedded version attributes.</span></span> <span data-ttu-id="8a545-117">A assinatura digital contém informações sobre a empresa que criou o arquivo de aplicativo (o Editor).</span><span class="sxs-lookup"><span data-stu-id="8a545-117">The digital signature contains information about the company that created the app file (the publisher).</span></span> <span data-ttu-id="8a545-118">As informações de versão, que são obtidas binário de recurso, incluem o nome do produto que o arquivo faz parte do e o número da versão do arquivo do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="8a545-118">The version information, which is obtained from the binary resource, includes the name of the product that the file is part of and the version number of the application file.</span></span>

### <a name="example-of-publisher-condition-rules"></a><span data-ttu-id="8a545-119">Exemplo de regras de condição do publisher</span><span class="sxs-lookup"><span data-stu-id="8a545-119">Example of publisher condition rules</span></span>

<span data-ttu-id="8a545-120">Para o aplicativo de cliente de equipes (todos os arquivos, todas as versões):</span><span class="sxs-lookup"><span data-stu-id="8a545-120">For the Teams client app (all files, all versions):</span></span>

```
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
```

## <a name="related-topics"></a><span data-ttu-id="8a545-121">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="8a545-121">Related topics</span></span>
<span data-ttu-id="8a545-122">[O que é AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
 [AppLocker de referência técnica](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span><span class="sxs-lookup"><span data-stu-id="8a545-122">[What is AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)
[AppLocker technical reference](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span></span>