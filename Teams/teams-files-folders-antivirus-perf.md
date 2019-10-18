---
title: Arquivos e pastas do teams para excluir da verificação de antivírus
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
ms.collection:
- Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4b4a4591bf25d7ef1a5b6efb9ab83c4508e26110
ms.sourcegitcommit: bcebe833d5ff4fcd3d6246fc5ed80980c6f31d0c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37578803"
---
<a name="teams-files-and-folders-to-exclude-from-antivirus-scanning"></a>Arquivos e pastas do teams para excluir da verificação de antivírus
=================================

Você pode melhorar o desempenho geral de sua implantação de equipes impedindo que seus programas antivírus examinem certos arquivos e pastas do teams. Isso evitará a despesa dos recursos do sistema em arquivos de digitalização e pastas que não precisam ser verificados.

> [!NOTE]
> Quando seus usuários baixarem arquivos ou compartilharem arquivos uns com os outros, esses arquivos não passarão pelos locais listados na seção a seguir. Os locais em que os usuários carregam, baixam ou compartilham arquivos ainda serão verificados regularmente pelo seu programa antivírus.

## <a name="files-and-folders-to-add-to-your-antivirus-safe-lists"></a>Arquivos e pastas para adicionar às listas de segurança do antivírus

Use os procedimentos suportados pelo seu programa antivírus para adicionar os seguintes arquivos e pastas às suas listas de confiança. Ao fazer isso, os recursos do sistema serão configurados para evitar verificações antivírus nestes locais.

### <a name="programs"></a>Programa

Adicione os programas da equipe a seguir à sua lista de segurança antivírus.

**%localappdata%\Microsoft\Teams\current\Teams.exe**

**%localappdata%\Microsoft\Teams\Update.exe**

### <a name="folders"></a>Pasta

Adicione as seguintes pastas do teams à sua lista de segurança antivírus.

|Categoria  |Local  |
|---------|---------|
|Arquivos de programa  |%localappdata%\Microsoft\Teams|
|Arquivos de dados     |%appdata%\Microsoft\Teams\|