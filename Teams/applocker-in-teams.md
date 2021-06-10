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
description: Saiba como habilitar o aplicativo cliente Teams área de trabalho com políticas de controle de aplicativo AppLocker.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d6e6040956ba5e5469076b4fbbab337f58268c68
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120843"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a><span data-ttu-id="9e3e7-103">Políticas de controle do aplicativo AppLocker em Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9e3e7-103">AppLocker application control policies in Microsoft Teams</span></span>

<span data-ttu-id="9e3e7-104">Este artigo explica como habilitar o aplicativo cliente Teams área de trabalho com as políticas de controle do aplicativo AppLocker.</span><span class="sxs-lookup"><span data-stu-id="9e3e7-104">This article explains how to enable the Teams desktop client app with AppLocker application control policies.</span></span> <span data-ttu-id="9e3e7-105">O uso do AppLocker foi projetado para restringir a execução de programas e scripts por usuários não administrativos.</span><span class="sxs-lookup"><span data-stu-id="9e3e7-105">Use of AppLocker is designed to restrict program and script execution by non-administrative users.</span></span> <span data-ttu-id="9e3e7-106">Para obter mais informações e orientações sobre o AppLocker, consulte [O que é AppLocker?](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).</span><span class="sxs-lookup"><span data-stu-id="9e3e7-106">For more information and guidance on AppLocker, see [What is AppLocker?](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).</span></span>

<span data-ttu-id="9e3e7-107">O processo para habil Teams com o AppLocker requer a criação de políticas de listagem de permitir baseadas em AppLocker.</span><span class="sxs-lookup"><span data-stu-id="9e3e7-107">The process for enabling Teams with AppLocker requires the creation of AppLocker-based allow listing policies.</span></span> <span data-ttu-id="9e3e7-108">As políticas são criadas com software de gerenciamento de Política de Grupo e/ou o uso de cmdlets Windows PowerShell para AppLocker (consulte a referência técnica do [AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) para obter mais informações).</span><span class="sxs-lookup"><span data-stu-id="9e3e7-108">Policies are created with Group Policy management software and/or the use of Windows PowerShell cmdlets for AppLocker (see the [AppLocker technical reference](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) for more information).</span></span> <span data-ttu-id="9e3e7-109">A política AppLocker é salva no formato XML e pode ser editada com qualquer texto ou editor XML.</span><span class="sxs-lookup"><span data-stu-id="9e3e7-109">The AppLocker policy is saved in XML format and can be edited with any text or XML editor.</span></span>

## <a name="teams-allow-list-with-applocker"></a><span data-ttu-id="9e3e7-110">Teams lista de permitir com o AppLocker</span><span class="sxs-lookup"><span data-stu-id="9e3e7-110">Teams allow list with AppLocker</span></span>

<span data-ttu-id="9e3e7-111">As regras do AppLocker são organizadas em coleções de regras.</span><span class="sxs-lookup"><span data-stu-id="9e3e7-111">AppLocker rules are organized into collections of rules.</span></span> <span data-ttu-id="9e3e7-112">As regras do AppLocker se aplicam ao aplicativo direcionado e são os componentes que comem a política do AppLocker.</span><span class="sxs-lookup"><span data-stu-id="9e3e7-112">AppLocker rules apply to the targeted app, and they are the components that make up the AppLocker policy.</span></span>  

<span data-ttu-id="9e3e7-113">Para permitir Teams, recomendamos que você [](/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) use as regras de condição do editor, já que todos os Teams de aplicativos são assinados digitalmente.</span><span class="sxs-lookup"><span data-stu-id="9e3e7-113">To allow Teams, we recommend that you use the [publisher condition rules](/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) since all Teams app files are digitally signed.</span></span>
  
<span data-ttu-id="9e3e7-114">Não recomendamos o uso de regras de caminho porque o diretório Teams de instalação é writable pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="9e3e7-114">We don't recommend the use of path rules because the Teams installation directory is user-writable.</span></span> <span data-ttu-id="9e3e7-115">Também não recomendamos o uso de regras de hash porque as regras teriam que ser atualizadas sempre que o aplicativo cliente Teams é atualizado.</span><span class="sxs-lookup"><span data-stu-id="9e3e7-115">We also don't recommend the use of hash rules because the rules would have to be updated each time the Teams client app is updated.</span></span>

<span data-ttu-id="9e3e7-116">Como Teams arquivos executáveis da área de trabalho são assinados digitalmente, a condição do editor identifica um arquivo de aplicativo com base em sua assinatura digital e atributos de versão incorporada.</span><span class="sxs-lookup"><span data-stu-id="9e3e7-116">Since Teams desktop executable files are digitally signed, the publisher condition identifies an app file based on its digital signature and embedded version attributes.</span></span> <span data-ttu-id="9e3e7-117">A assinatura digital contém informações sobre a empresa que criou o arquivo de aplicativo (o editor).</span><span class="sxs-lookup"><span data-stu-id="9e3e7-117">The digital signature contains information about the company that created the app file (the publisher).</span></span> <span data-ttu-id="9e3e7-118">As informações de versão, que são obtidas do recurso binário, incluem o nome do produto do qual o arquivo faz parte e o número de versão do arquivo de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="9e3e7-118">The version information, which is obtained from the binary resource, includes the name of the product that the file is part of and the version number of the application file.</span></span>

### <a name="example-of-publisher-condition-rules"></a><span data-ttu-id="9e3e7-119">Exemplo de regras de condição do editor</span><span class="sxs-lookup"><span data-stu-id="9e3e7-119">Example of publisher condition rules</span></span>

<span data-ttu-id="9e3e7-120">Para o Teams cliente (todos os arquivos, todas as versões) adicione o seguinte às Regras Executáveis & Regras DLL:</span><span class="sxs-lookup"><span data-stu-id="9e3e7-120">For the Teams client app (all files, all versions) add the following to the Executable Rules & DLL Rules:</span></span>

```console
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
Product name: MICROSOFT TEAMS UPDATE
```

## <a name="related-topics"></a><span data-ttu-id="9e3e7-121">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="9e3e7-121">Related topics</span></span>
<span data-ttu-id="9e3e7-122">[O que é AppLocker?](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
 [Referência técnica do AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span><span class="sxs-lookup"><span data-stu-id="9e3e7-122">[What is AppLocker?](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)
[AppLocker technical reference](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span></span>