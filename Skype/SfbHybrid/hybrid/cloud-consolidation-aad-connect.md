---
title: Atualizar o AAD Connect para incluir mais de uma floresta
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Este apêndice inclui etapas detalhadas para atualizar o AAD Connect para incluir mais de uma floresta como parte da consolidação de nuvem para o Teams e o Skype for Business.
ms.openlocfilehash: 19b761f3b64caf7afad7d37a51ae391e23d6b5ef
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120370"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a>Atualizar o AAD Connect para incluir mais de uma floresta

O Azure AD Connect dá suporte [à sincronização de várias florestas.](/azure/active-directory/connect/active-directory-aadconnect-topologies) No entanto, ele dá suporte a apenas uma instância da sincronização do Azure AD Connect com o AAD. Portanto, nos casos em que o Azure AD já está instalado em uma floresta, a instância existente do AAD Connect deve ser atualizada para sincronizar a partir da floresta adicional.

 - Se todas as identidades são representadas apenas uma vez em ambas as florestas (ou seja, você não fez nenhum contato habilitado para email), então você pode simplesmente executar novamente o assistente do AAD Connect, escolha "Personalizar opções de sincronização", e, em seguida, na página **Conectar** Seus Diretórios, insira o nome da floresta adicional e os créditos.<br><br>
 ![A página Conectar seus diretórios](../media/cloud-consolidation-connect-your-directories.png)
 - No entanto, se os usuários puderem existir em mais de um diretório e você estiver mesclando os dados (por exemplo, se os objetos de contato existirem em uma floresta correspondente aos usuários em outra floresta), você precisará desinstalar o Azure AD Connect e instalá-los novamente.  Isso porque a condição de regras de junção entre florestas só pode ser configurada durante a primeira instalação. Isso é feito na página a seguir:<br><br>
 ![A página Identificando seus usuários com exclusividade](../media/cloud-consolidation-uniquely-identifying-your-users.png)


## <a name="see-also"></a>Confira também

[Consolidação de nuvem para Teams e Skype for Business](cloud-consolidation.md)