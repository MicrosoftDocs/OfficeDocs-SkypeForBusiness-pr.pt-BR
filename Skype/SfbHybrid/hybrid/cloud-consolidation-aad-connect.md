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
description: Este apêndice inclui etapas detalhadas para atualizar o AAD Connect para incluir mais de uma floresta como parte da consolidação na nuvem para o Teams e o Skype for Business.
ms.openlocfilehash: a61a45c8a492afd761f8cc6b1020b591851645b8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049093"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a>Atualizar o AAD Connect para incluir mais de uma floresta

O Azure AD Connect dá [suporte à sincronização de várias florestas.](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-topologies) No entanto, ele dá suporte a apenas uma instância da sincronização do Azure AD Connect com o AAD. Portanto, nos casos em que o Azure AD já está instalado em uma floresta, a instância existente do AAD Connect deve ser atualizada para sincronizar a partir da floresta adicional.

 - Se todas as identidades são representadas apenas uma vez em ambas as florestas (ou seja, você não fez contatos habilitados para email), então você  pode simplesmente executar novamente o assistente do AAD Connect, escolher "Personalizar opções de sincronização" e, em seguida, na página Conectar seus Diretórios, insira o nome da floresta adicional e creds.<br><br>
 ![A página Conectar seus diretórios](../media/cloud-consolidation-connect-your-directories.png)
 - No entanto, se os usuários puderem existir em mais de um diretório e você mesclar os dados (por exemplo, se objetos de contato existirem em uma floresta correspondente aos usuários de outra floresta), você precisará desinstalar o Azure AD Connect e reinstalá-los.  Isso porque a condição de regras de junção entre florestas só pode ser configurada durante a primeira instalação. Isso é feito na página a seguir:<br><br>
 ![A página Identificando exclusivamente seus usuários](../media/cloud-consolidation-uniquely-identifying-your-users.png)


## <a name="see-also"></a>Confira também

[Consolidação na nuvem para o Teams e o Skype for Business](cloud-consolidation.md)