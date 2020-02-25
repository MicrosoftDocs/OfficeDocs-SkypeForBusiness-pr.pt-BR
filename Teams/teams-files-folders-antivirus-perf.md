---
title: Pastas e arquivos do Teams a serem excluídos da verificação de antivírus
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: Melhorar o desempenho do teams excluindo certos arquivos e pastas de uma verificação antivírus normal.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9c1519038cb2393687a031e9b2c1ea828f999728
ms.sourcegitcommit: bb88ac0c9489bb47957e5ef1074b5df3126b6fdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/25/2020
ms.locfileid: "42265616"
---
<a name="teams-files-and-folders-to-exclude-from-antivirus-scanning"></a><span data-ttu-id="05bb2-103">Pastas e arquivos do Teams a serem excluídos da verificação de antivírus</span><span class="sxs-lookup"><span data-stu-id="05bb2-103">Teams files and folders to exclude from antivirus scanning</span></span>
=================================

<span data-ttu-id="05bb2-104">Você pode melhorar o desempenho geral de sua implantação de equipes impedindo que seus programas antivírus examinem certos arquivos e pastas do teams.</span><span class="sxs-lookup"><span data-stu-id="05bb2-104">You can improve the overall performance of your Teams deployment by preventing your antivirus programs from scanning certain Teams files and folders.</span></span> <span data-ttu-id="05bb2-105">Isso evitará a despesa dos recursos do sistema em arquivos de digitalização e pastas que não precisam ser verificados.</span><span class="sxs-lookup"><span data-stu-id="05bb2-105">This will avoid the expenditure of system resources on scanning files and folders that don't need to be scanned.</span></span>

> [!NOTE]
> <span data-ttu-id="05bb2-106">Quando seus usuários baixarem arquivos ou compartilharem arquivos uns com os outros, esses arquivos não passarão pelos locais listados na seção a seguir.</span><span class="sxs-lookup"><span data-stu-id="05bb2-106">When your users download files or share files with each other, those files don't pass through the locations listed in the following section.</span></span> <span data-ttu-id="05bb2-107">Os locais em que os usuários carregam, baixam ou compartilham arquivos ainda serão verificados regularmente pelo seu programa antivírus.</span><span class="sxs-lookup"><span data-stu-id="05bb2-107">The locations where your users do upload, download, or share files will still be regularly scanned by your antivirus program.</span></span>

## <a name="files-and-folders-to-add-to-your-antivirus-safe-lists"></a><span data-ttu-id="05bb2-108">Arquivos e pastas para adicionar às listas de segurança do antivírus</span><span class="sxs-lookup"><span data-stu-id="05bb2-108">Files and folders to add to your antivirus safe lists</span></span>

<span data-ttu-id="05bb2-109">Use os procedimentos suportados pelo seu programa antivírus para adicionar os seguintes arquivos e pastas às suas listas de confiança.</span><span class="sxs-lookup"><span data-stu-id="05bb2-109">Use the procedures supported by your antivirus program to add the following files and folders to your safe lists.</span></span> <span data-ttu-id="05bb2-110">Ao fazer isso, os recursos do sistema serão configurados para evitar verificações antivírus nestes locais.</span><span class="sxs-lookup"><span data-stu-id="05bb2-110">Doing so will conserve system resources by avoiding antivirus scans of these locations.</span></span>

### <a name="programs"></a><span data-ttu-id="05bb2-111">Programa</span><span class="sxs-lookup"><span data-stu-id="05bb2-111">Programs</span></span>

<span data-ttu-id="05bb2-112">Adicione os programas da equipe a seguir à sua lista de segurança antivírus.</span><span class="sxs-lookup"><span data-stu-id="05bb2-112">Add the following Teams programs to your antivirus safe list.</span></span>

<span data-ttu-id="05bb2-113">**%localappdata%\Microsoft\Teams\current\Teams.exe**</span><span class="sxs-lookup"><span data-stu-id="05bb2-113">**%localappdata%\Microsoft\Teams\current\Teams.exe**</span></span>

<span data-ttu-id="05bb2-114">**%localappdata%\Microsoft\Teams\Update.exe**</span><span class="sxs-lookup"><span data-stu-id="05bb2-114">**%localappdata%\Microsoft\Teams\Update.exe**</span></span>

### <a name="folders"></a><span data-ttu-id="05bb2-115">Pasta</span><span class="sxs-lookup"><span data-stu-id="05bb2-115">Folders</span></span>

<span data-ttu-id="05bb2-116">Adicione as seguintes pastas do teams à sua lista de segurança antivírus.</span><span class="sxs-lookup"><span data-stu-id="05bb2-116">Add the following Teams folders to your antivirus safe list.</span></span>

|<span data-ttu-id="05bb2-117">Categoria</span><span class="sxs-lookup"><span data-stu-id="05bb2-117">Category</span></span>  |<span data-ttu-id="05bb2-118">Local</span><span class="sxs-lookup"><span data-stu-id="05bb2-118">Location</span></span>  |
|---------|---------|
|<span data-ttu-id="05bb2-119">Arquivos de programa</span><span class="sxs-lookup"><span data-stu-id="05bb2-119">Program files</span></span>  |<span data-ttu-id="05bb2-120">%localappdata%\Microsoft\Teams</span><span class="sxs-lookup"><span data-stu-id="05bb2-120">%localappdata%\Microsoft\Teams</span></span>|
|<span data-ttu-id="05bb2-121">Arquivos de dados</span><span class="sxs-lookup"><span data-stu-id="05bb2-121">Data files</span></span>     |<span data-ttu-id="05bb2-122">%appdata%\Microsoft\Teams</span><span class="sxs-lookup"><span data-stu-id="05bb2-122">%appdata%\Microsoft\Teams</span></span>\ |
