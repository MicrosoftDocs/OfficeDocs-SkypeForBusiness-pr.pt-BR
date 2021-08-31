---
title: Usar a funcionalidade de unidade administrativa no Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: prasad.ghlove
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como usar a funcionalidade de unidade administrativa no Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9f1424149a3f585b30cb7a31d7742370c06cae3d
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58736120"
---
# <a name="administrative-unit-functionality-for-device-management-in-teams"></a>Funcionalidade de unidade administrativa para gerenciamento de dispositivos Teams

Tenha acesso mais granular baseado em função para gerenciamento de dispositivo usando o Microsoft Teams de administração. Implementamos o conceito de Unidade Administrativa para gerenciamento de dispositivos por meio do Teams de administração.

Com o conceito de unidade administrativa, você garantirá o acesso a um conjunto específico de recursos para um administrador dedicado. A unidade administrativa limita o acesso a todos os recursos. Você pode estender a mesma funcionalidade para o gerenciamento Teams dispositivos.

> [!NOTE]
> O conceito de unidade administrativa está disponível apenas para a função Teams Administrador de Dispositivos no momento.

Como exemplo, a Contoso tem operações em diferentes regiões geográficas. Alice é uma administradora de IT global em Londres, enquanto Prashant é um administrador de IT para a Índia. Hoje, quando Prashant entra no centro de administração Teams com a função Administrador de Dispositivos, eles podem ver dispositivos em todo o mundo. Alice deseja restringir o acesso de Prashant somente aos dispositivos que estão presentes na Índia. O conceito de unidades administrativas ajuda a resolver esse problema. Saiba mais [conceito de unidade administrativa](/azure/active-directory/roles/administrative-units).

![um diagrama que mostra cenários.](media/au-diagram.png)

## <a name="creation-of-administrative-units"></a>Criação de Unidades Administrativas

Crie unidades administrativas no portal do Azure e atribua administradores para as respectivas unidades administrativas. Saiba mais sobre a atribuição de unidades administrativas em [gerenciar unidades de administração.](/azure/active-directory/roles/admin-units-manage)

![um exemplo de unidades administrativas da empresa.](media/au-example.png)

Depois de criado, o administrador de IT global pode adicionar usuários de dispositivo que correspondam a essa unidade administrativa.

![um exemplo de empresa com visualização de usuários.](media/au-example2.png)

A atribuição da função pode ser feita por meio do PowerShell usando o cmdlet [Add-AzureADMSScopedRoleMembership.](/powershell/module/azuread/add-azureadmsscopedrolemembership?view=azureadps-2.0)

Depois que você atribuiu funções aos usuários para Unidades Administrativas, os usuários precisam entrar Teams centro de administração para começar a gerenciar dispositivos com escopo.

## <a name="experience-for-administrative-unit-admin"></a>Experiência para Administrador de Unidade Administrativa

Se os mesmos administradores são atribuídos à responsabilidade de várias unidades administrativas, eles podem alternar entre unidades administrativas sem sair do portal. Na exibição de unidade administrativa alterada, eles verão apenas o conjunto de dispositivos associados à nova unidade administrativa.
