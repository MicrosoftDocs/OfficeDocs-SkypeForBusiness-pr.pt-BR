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
ms.localizationpriority: medium
description: Este apêndice inclui etapas detalhadas para atualizar o AAD Conexão incluir mais de uma floresta como parte da consolidação de nuvem para Teams e Skype for Business.
ms.openlocfilehash: 261085c85b9b3114bce49216e7b63173cd37d55e
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731880"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a>Atualizar o AAD Connect para incluir mais de uma floresta

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

O Azure AD Conexão dá suporte à [sincronização de várias florestas.](/azure/active-directory/connect/active-directory-aadconnect-topologies) No entanto, ele dá suporte a apenas uma instância do Azure AD Conexão sincronização com o AAD. Portanto, nos casos em que o Azure AD já está instalado em uma floresta, a instância existente do AAD Conexão deve ser atualizada para sincronizar a partir da floresta adicional.

 - Se todas as identidades são representadas apenas uma vez em ambas as florestas (ou seja, você não fez nenhum contato habilitado para email), então você pode simplesmente executar novamente o assistente do AAD Conexão, escolha "Personalizar opções de sincronização", e, em seguida, na página **Conexão Seus** Diretórios, insira o nome da floresta adicional e os créditos.<br><br>
 ![A Conexão seus diretórios.](../media/cloud-consolidation-connect-your-directories.png)
 - No entanto, se os usuários puderem existir em mais de um diretório e você estiver mesclando os dados (por exemplo, se os objetos de contato existirem em uma floresta correspondente aos usuários em outra floresta), você precisará desinstalar o Azure AD Conexão e instalá-los novamente.  Isso porque a condição de regras de junção entre florestas só pode ser configurada durante a primeira instalação. Isso é feito na página a seguir:<br><br>
 ![A página Identificando seus usuários com exclusividade.](../media/cloud-consolidation-uniquely-identifying-your-users.png)


## <a name="see-also"></a>Confira também

[Consolidação de nuvem para Teams e Skype for Business](cloud-consolidation.md)